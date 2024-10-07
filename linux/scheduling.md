# Scheduling
## Introduction to CPU Scheduling
- Selects from among the processes/threads that are ready to execute, and allocates the CPU to it.
### What is CPU Scheduling
- In support of multiprogramming
    - uniprocessor systems
        - time sharing processor
    - multiprocessor systems
        - efficiently distributing tasks
    - Real time systems
        - Reliably guaranteeing deadlines

### Why we need CPU Scheduling
- All systems
    - Fairness - giving each process a fair share of the CPU
    - Policy enforcement - seeing that stated policy is carried out
    - Balance - keeping all parts of the system busy
- Batch systems
    - Throughput-maximize jobs per hour
    - Turnaround time - minimize time between submission and termination
    - CPU utilization - keep the CPU busy all the time 
- Interactive systems
    - Response time - responds to requests quickly
    - Proportionality - meets users' expectations
- Real time systems
    - Meeting deadlines - avoid losing data
    - Predicability - avoid quality degradation in multimedia systems
### When scheduling happens
- Non-preemptive 
    - Scheduling only when current process terminates or gives up control 
- Preemptive 
    - Processes can be forced to give up control
- CPU scheduling may take place at
    - Clock and I/O interrupts, I/O completion, or termination

## Scheduling Policies
### FCFS, SJF, RR, Priority
- Batch systems follow First-Come First-Serve (FCFS), which focuses on the shortest job first 
- Interactive systems do a round robin with priority scheduling
### Scheduling on multiple CPUs

### Calculate the Turnaround time and response time for scheduling
- Step 1. Draw the timeline based on the scheduling policy
- Step 2. Calculate turnaround time and response time for each task 
- Response time = start time - arrival time 
- Turnaround time = Endtime - arrival time 


