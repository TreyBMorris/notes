# Thread

## What is thread?
- Thread refers to a finer-granularity entity for execution and parallelism
- A lightweight process
    - Occupy more memory, complex switching, and low CPU utilization
- A program in execution without dedicated address space
- Programs can use multiple threads for a process
    - For example: A word process can have three threads. One for handling keyboard input, one for screen display, and one for saving documents to the disk.
- Web servers like Apache and Nginx have multiple threads with a single master process.

## Why multiple threads?
- Having multiple threads is like having a single process while each individual thread does something different.
    - Example: A kitchen where multiple cooks are trying to prepare the same meal tgether. Each one is doing one thing and they are all probably doing different things, but they all share the same recipe and must coordinate to make the process.

## Threads and Processes in Linux
- Linux calls a process a thread state. It has multiple states.
    - Running, executing instructions
    - Ready, not executing instructions but capabe of being restarted
    - Waiting, Blocked or Sleeping, not executing instructions and not able to be restarted until some even occurs
    - New/Terminated
- To create a new thread inn linux, we use clone() to create threads instead of using fork(). 
    - Fork vs clone
        - Fork, all resources are copied from parent process to child process
        - Clone, the resources are partly copied from one thread to another thread


