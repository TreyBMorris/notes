# POSIX Threads (pthread) Programming

## What is PThread?
### Thread Model
- Process: For resource grouping and execution
- Thread: A finger-granularity entity for execution and parallelism
- Because threads within the same process share resources
    - Changes made by one thread to shared system resoures will be seen by all other threads
    - Two pointers having the same value point to the same data
    - Reading and writing to the same memory location is possible, and therefore requires explicit synchronization by the programmer
- Performance is better with multi-threads for things like servers. Ex. Apache web server can drop by 20x the amount of response time when having multiple threads
- 
### Pthread overview
- What are Pthreads?
    - An IEEE standardized thread programming interface (IEEE POSIX 1003.1c)
    - POSIX (Portable Operating System interface) Threads
- Pthreads are defined as a set of C language programming types and procedure calls, that are implemented with a pthread.h header and a thread library
- Why Pthreads?
    - Performance, lightweight, communication, easy to use

## PThread management
### Creation and termination
- When creating a pthread application, to compile you'll want to use 
```bash
gcc hello-world.c -o hello-world.o -pthread
```
- pthread_create(thread,attr,thread_function,arg)
    - 1st parameter: pthread in the array
    - 3rd parameter: the function for the thread to run
    - 4th parameter: arg is passed by reference as a pointer cast of type void
```C
pthread_t threads[NUM_THREADS];
int t;
for(t = 0; t<NUM_THREADS; t++){
    rc = pthread_create(&threads[t], NULL, thread_function, (void *)t);
}
```
- This function will create a new thread.
### Identification
- pthread_self(void)
    -returns the id of thre thread in which it is invoked.
### Join and detach
- pthread_join(threadid, status)
    -Joining is one way to accomplish synchronization between threads: The pthread_join() subroutine blocks the calling thread until the specified threadid thread terminates.
- The main thread will be blocked here to wait for the child thread to finish.

## PThread data sharing
### Mutex
- Mutex is a simplified version of the semaphores. A variable that can be in one of two states: locked or unlocked
- Supports synchronization by controlling access to shared data.
- pthread_mutex_init(mutex,attr)
- pthread_mutex_destroy(mutex)
1. Mutex variables must be declared with type pthread_mutex_t and must be initialized before can be used. The mutex is initially not locked. 
- Statically: pthread_mutex_t mymutex = PTHREAD_MUTEX_INITIALIZER 
- Dynamically, with pthread_mutex_init(mutex, attr)
2. The attr object must be declared with type pthread_mutexattr_t
3. Programmers should free a mutex object that is no longer used.
#### Locking and Unlocking Mutexes
1. pthread_mutex_lock(mutex) is a blocking call.
2. pthread_mutex_trylock(mutex) is a non-blocking call, useful in preventing the deadlock conditions (priority-inversion problem)
3. If you use multiple mutexes, the order is important;
### Condition Variable
- Mutexes: Support synchronization by controlling thread access to data(without conditions)
- Condition Variables: Another way for threads to synchronize (with conditions)
- Example:
    - T1: Increase x every time;
    - T2: when x is larger than 99, then set x to 0;
- pthread_cond_wait(condition, mutex)
- pthread_cond_signal(condition)
- pthread_cond_broadcast(condition)
1. wait() blocks the calling thread until the specified condition is signaled. It should be called while mutex is locked.
2. signal() is used to signal or wake up another thread which is waiting on the condition variable. It should be called after mutex is locked, and programmers must unlock mutex in order for wait() routine to be complete.
3. broadcast() is useful when multiple threads are in blocked waiting.
4. wait() should come before signal() - conditions are not counters, signal would be lost if not waiting.

### Barrier
- Use of a barrier(for programs operate in phases, neither enters the next phase until all are finished with the current phase) for groups of processes to do synchronization.
    - processes approaching a barrier
    - all processes but one blocked at barrier
    - last process arrives, all are let through
- pthread_barrier_init(barrier, attr, count)
- pthread_barrier_wait(barrier)
- pthread_barrier_destroy(barrier)
- init() function shall allocate any resources required to use the barrier referenced by barrier and shall initialize the barrier with attr. If attr is NULL, default settings will be applied. The count argument specifies the number of threads that must call wait() before any of them successfully return from the call.
- wait() function shall synchronize participating threads at the barrier
- destroy() function shall destroy the barrier and release any resources used by the barrier.

### Semaphore
- Semaphores are counters for resources shared between threads. The basic operations on semaphores are: increment the counter atomically, and wait until the counter is non-null and decrement is automatically.
- int_sem_init(sem_t*sem, int pshared, unsigned int value)
    - Init a sem. The pshared argument indicates whether this semaphore is to be shared between the threads of a process or between processes. The value argument specifies the initial value for the semaphore.
- int_sem_destroy(sem_t* sem)
    - Destroy a sem
- int sem_wait(sem_t* sem)
    - Request one unit resource, blocking call. If successfully, sem--.
- int sem_trywait(sem_t*sem)
    - Request one unit resource, non-blocking call If successfully, sem--;
- int sem_post(sem_t*sem)
    - Release one unit resource. If successful, sem++


