# Interrupt
## What is interrupt?
### Interrupt vs Polling
#### What is polling?
- How can the processor work with hardware without impacting the machine's overall performance?
    - Polling: Repeatedly check whether the hardware is ready or not
- Increasing system overhead. Whether it is task polling or timer polling, it needs to consume the corresponding system resources.
- Unable to sense device status changes in a timely manner. Device state changes during the polling interval can only be discovered on the next poll, which will not be able to meet real-time sensitive applications.
- Waste CPU resources. Polling is always in progress regardless of whether the device has changed state. In the real world, the state change of most devices is usually not so frequent, and polling idle will waste CPU time slices.

#### What is interrupt?
- Lightweight and save CPU resources.
- Handle in time.
- Interrupt sends hardware signals to the kernel when attention is needed. 
- Interrupt problem
    - Too many interrupts means less resources for IRQ handler and that some data may be missing from interrupt.
#### Combine interrupt and polling
- Benefits:
    - Avoid frequent interruptions when receiving large amounts of data or requests.
    - No need to spend a lot of CPU resources for polling.
#### Exceptions
- An Exception indicates that code running on the CPU has created a situation that the processor needs help to address. Like divide by zero and etc.
#### Interrupt vs Exceptions
- Interrupts are voluntary
- Exceptions are non-voluntary
### Advanced programmable interrupt controller
- Responsible for telling the CPU when a specific external device wishes to interrupt. 
- APIC translates IRQ to interrupt number. This raises the interrupt to the CPU and the interrupt # is available in register.
- Interrupts can have varying priorities. APIC also needs to prioritize multiple requests. 
- It is possible to "mask" (disable) interrupts at PIC or CPU
### Interrupt processinig
- Interrupt descriptor table (IDT) is in memory and initialized by OS at boot. IDT associates with each interrupt vector and stores the entry address of the corresponding interrupt handler. 
## Interrupt types and affinity
### Hardware and software interrupt
- Hardware interrupts are used to signal that a particular device needs attention. 
- Software interrupts are raised by software or execution. 
### Interrupt affinity
- IRQ affinity determines the CPU cores that are allowed to execute the processing for that IRQ.
- IRQ affinity can be used to improve application performance.
- Read the IRQ affinity of specific hardIRQ
- Set the IRQ affinity to specific hardIRQ
- SoftIRQ will execute on the core which it is raised and cannot be set with affinity. 
