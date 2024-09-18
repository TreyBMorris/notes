# Lock

## Concurrency and Synchronization
### Race Condition
- A race condition occurs when two or more threads access shared data and they try to change it at the same time.
- The order in which the threads attempt to access the shared data makes the results unpredictable.
- Like in a counter where the threads run the same counter function, the counter can give weird results that are unpredictable.
### Critical Section
- A critical section is a section of code in a concurrent task that modifies of accesses a resource shared with another task.
- Examples
    - A piece of code that reads from or writes to a shared memory region
    - Or a code that modifies or traverses a shared linked list.
- Critical section is where the race condition happens
- When multiple threads visit the critical section, race condition problems appear.

### Avoiding Race Condition
- Prinicples:
1. No two processes are simultaneously in the critical region.
2. No assumptions are made about speeds or numbers of CPUs.
3. No process running outside its critical region may block another process running in the critical region.
4. No process must wait forever to enter its critical region
    - Waiting forever indicates a Deadlock

- Principles 1 and 2 are enforced by the operating system's implementation of locks. 
    - As programmers we assume that locks satisfy 1 and 2.
- 3 and 4 must be ensured by the programmer using the locks. OS cannot enforce these.

 

## Mutual Exclusion
- A lock is a synchronization mechanism for enforcing limits on access to a resource in an environment where there are many threads of execution
    - Types of mutual mechanism, busy-waiting, e.g., spinlock. Sleep and wakeup
### Spinlock
- Spinlock: A busy-waiting lock implementation.
- Don't block. Instead, constantly poll the lock for availability. 
    - Usage: Small critical region
- Advantages:
    - Very efficient with short critical sections, if you expect a lock to be released quickly.
- Disadvantages: 
    - Doesn't yield the CPU and burns CPU cycles. Bad if critical sections are long.
    - Efficient only if machine has multiple CPUs. Counterproductive on uniprocessor machines.
- You can declare the lock and unlock in your C code.
```C
pthread_spin_lock(&splock);
while(i< 10000){
    counter = counter + 1;
    i++
}
printf("Counter value: %d\n", counter);
pthread_spin_unlock(&splock);
```
- Other mutual exclusion similar as busy waiting(spinlock)
    - Disabling interrupts:
        - OS technique, not users'
    - Lock variables:
        - Test and set lock (TSL) is a two-setp process, not atomic
    - Peterson's algorithm
        - Does not need atomic operation and mainly used in user space application.
### Mutex Lock
- A variable that can be in one of two states: locked or unlocked.
- Mutex is used as a lock around critical sections
- Mutex is an implementation of a sleep and wakeup lock
- Mutex lock with conditions
    - Mutex locks solve the competition problem of multiple threads accessing the same global variable under the shared memory space. 
    - We can use conditions to unlock or lock a thread.

### Semaphore
- A system of sending messages by holding the arms or two flags in certain positions.
- Semaphore is a variable used to control access to shared resourced by multiple processes/threads.
- Instead of being 0 or 1 it can be 0/1/2/3 
- A semaphore "sem" is a special integer on which only two operations can be performed. Up or Down
- Down operation(P; request). Checks is a semaphore is >0 sem--
- Up operation (V; release) sem++ 
### Deadlock and priority inversion
- When two or more threads stop making progress indefinitely because they are all waiting for each other to do something.
    - If process A waits for process B to release a resource, and 
    - Process B is waiting for process A to release another resource at the same time.
    - In this case, neither A nor B can proceed because both are waiting for the other to proceed.

