# System-Call

## What is system call?


### Kernel Space vs User Space
- Kernel Space is strictly reserved for running a privileged operating system kernel, kernel extensions, and most device drivers.
- User space is the area where application software and some drivers execute.
  - Windowing, libraries, graphics, programs like bash, Firefox, etc.


#### User Mode vs Kernel Mode
- The CPU can execute every instruction in the instruction set and use every feature of the hardware when executing in kernel mode, but 
can only access a subset of instructions and features when executing in user mode.
- The purpose of having these two modes is mainly for the protection of critical resources from being misused by user programs.

#### Interacting between user and kernel space 
- For applications, in order to perform privileged operations, we must use well defined interfaces in the OS called system calls to make these operations.

### System calls
- System calls are a type of special protected procedure calls allowing user-level processes request services from the kernel. They provide an abstraction layer between processes and hardware, allowing the kernel to provide access control.
  - Also provides a virtualization of the underlying system and a well-defined interface for system services. 

#### System calls vs library function
- Both appear to be APIs that can be called by programs to obtain a given service.
- The main difference is that library functions are executed in the user space and system calls are executed in the kernel space.
- Many system calls have a corresponding standard C library wrapper routines which hide the details of a system call entry/exit.
  - Ex. write() and sys_write() are system calls wrapped in the C library.


|             | System call                                               | Library Function                                      |
| ----------- | ---------------                                           | -------------------------------                       |
| Position    | The functions which are a part of kernel                  | The functions which are a part of standard C library  |
| Space       | Get executed in kernel mode.                              | Get executed in user mode                             |
| Privilege   | Runs in the supervisory mode so have every priviledge     | Doesn't have much priviledge                          |
| Performance | System calls are slow as there is context switch involved | Faster execution as it doesn't involve context switch |


#### Services provided by System calls
- Process creation and management
  - Fork (makes two processes which run the same program after instruction)
- Main memory management
- File access, directory and file system management
  - Create file, delete, write, etc.
- Device handling (I/O)
- Protection, encryption
- Networking

#### Examples of System calls

| Process Control        | File Manipulation              | Device Manipulation    | Information Maintenance   | Communication & Protection | 
| ---------------        | ---------------                | ---------------        | ---------------           | --------------- |
| fork(), exit(), wait() | open(), read(), write(), close | ioctl(),read(),write() | getpid(), alarm(), time() | pipe, send, recv, mmap, chmod, umask, chown |


## Syscall interface
- Important to keep interface small and stable and make sure that every syscall does one thing. 
- Early UNIX had about 60 system calls, Linux 2.6 has about 300. 
- Windows does not publicly document system calls and only documents library wrapper routines. 
- Syscall numbers cannot be reused.
- Three most common APIs in OS are,
  - Win32 API for Windows, POSIX API for virtually all versions of UNIX, Linux, and Mac OS X, and Java API for JVM



#### Syscall return values
- Library calls return -1 on error. System calls return specific negative values to indicate an error. 

