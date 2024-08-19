# OS Notes
This is a collection of some notes from my Operating Systems class, CS 3502 with Kevin Suo

## What is an OS?
- An operating system is a layer of software between the hardware and the application programs that provides a virtualization interface.
- A resource manager that allows concurrent programs and users to share the hardware resources.
- The operating system also ensures information stored persistently in the computer.
- The three themes of operating systems: virtualization, concurrency, and persistence. 

#### Virtualization
- Making a physical resource look like something else
- Examples
  - Make one physical CPU look like multiple virtual CPUs.
  - Make physical memory (RAM) and look like multiple virtual memory spaces.
  - Make physical disk look like a file system
#### Concurrency
- Virtualization allows multiple concurrent programs to share the virtualized hardware resources, which brings out another class of topics
- Examples
  - One physical CPU runs many processes
  - One process runs many threads
  - One OS juggles process execution, system calls, interrupts, exceptions, CPU scheduling, memory management, etc.
- There is a LOT of concurrency in modern computer systems.

#### Persistence
- Storing data "forever"
- But its not enough to just store raw bytes, users will want to...
  - Organize data (file systems)
  - Share data (network or cloud)
  - Access data easily
  - Protect data from being stolen


## History of Operating Systems 
- 1950s and 60s, early operating systems were simple batch processing systems. 1960s and 70s, UNIX was introduced which pioneered file systems, shell, pipes and the C language. 
- In the 1980s, MacOS, IBM DOS, and Windows was introduced. Many big companies had their own version of an operating system.
- 1990s introduces Linux which was open source, this lead the way for modern operating systems and cloud platforms.
- 2000s introduced mobile devices and hypervisors. iOS, Android, Linux, etc.
- Many operating systems are majorly updated or created for things like hardware upgrades, new types of hardware, new services, and fixes. 


#### User vs Kernel Mode:
- What is the difference?
  - Most modern CPUs provide two modes of execution, kernel mode and user mode. 
  - The CPU can execute every instruction in its instruction set and use every feature of the hardware when in kernel mode.
  - However, in user mode this is limited to a subset of the instructions and only use a subset of the features. 
- Why do we have these two modes?
  - The purpose is mainly for protection of critical resources. We do not want our system crashing due to being misused by user programs.

#### Types of Kernels
- Monolithic Kernels
  - Linux, Android
  - Large code base with many features
- Hybrid Kernels
  - iOS, Windows
  - Large code base with some delegated features
- Microkernels
  - Google fuchsia, research Kernels
  - Small code base with few features

