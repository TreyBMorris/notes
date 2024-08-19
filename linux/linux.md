# Linux Main
[Back to main](https://github.com/TreyBMorris/notes)
#### 
- [Cheatsheet of Useful Linux Commands](/linux/linux-commands.md)

#### Jump to a Section
- [What is Linux?](#what-is-linux)
- [Kernel and Shell](#kernel-and-shell)
- [Linux Distributions](#linux-distributions)
- [How do I install Software on Linux?](#how-do-i-install-software-on-linux)
- [How do I update my operating system?](#how-do-i-update-my-operating-system)


# What is Linux?

Linux is an open source operating system, first developed by Linus Torvalds.
In the world of Computer Science, Software Engineering, and Information Technology, Linux is something that is important to understand the concepts of. 

## Kernel and Shell
The kernel is the absolute most basic component of the operating system, which acts as the communicator between the hardware and the software of your computer. Any commands entered by the user are processed by the kernel through the shell and are returned back to the user. The shell is a program where a user inputs commands or instructions into the operating system. This acts as an interface that reads and processes comands from the user, and returns them back to the user. One of the most popular and notable shells in Linux is the Bourne Again Shell, or most commonly referred to as Bash. For those who are Windows users, a common comparison to Bash would be the PowerShell. In macOS, we also commonly use Bash.


## Linux Distributions
A linux distribution is an operating system that provides a bundle of software that is based on the Linux kernel and libraries that support the kernel. There are hundreds of different distributions for Linux that provide different purposes and are available for a wide variety of different devices.
<br />
Here is a list of some popular distributions
- [Ubuntu](https://ubuntu.com/) Probably the most popular distribution
- [Arch Linux](https://archlinux.org/) 
- [Debian](https://www.debian.org/) 
- [Linux Mint](https://linuxmint.com/)
- [Fedora](https://fedoraproject.org/) What I am currently using. With KDE plasma.


## How do I install software on Linux?
Installing software on Linux depends on the package manager specific to your linux distribution. For our example, we will be using the Debian and Ubuntu package manager "apt". To install vim, a popular text editor for linux, we would use the following command.
```bash
sudo apt install vim
```

## How do I update my operating system?
We can use the following commands to update our packages. Again, for this example we will use "apt" to update the packages.
```bash
sudo apt update
sudo apt upgrade
```
For an explnation of what sudo is, please see the useful linux commands cheatsheet link at the top.


Resources
https://www.geeksforgeeks.org/introduction-to-linux-operating-system/
