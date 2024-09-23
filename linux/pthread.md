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
### Condition Variable
### Barrier
### Semaphore

