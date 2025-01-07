# Memory Management
## Why do we need memory management?
- Ideally user/programmers want memory that is...
    - Large in size
    - Fast
    - Durability, non volatile
- Reality
    - Small amount of fast, expensive memory like the register or cache
    - Some medium-speed medium price main memory lots of slow cheap disk storage
    - Volatile (top hierarchy)
## Memory hierarchy?
- Registers, Cache, Main memory, Magnetic disk, Magnetic tape
- On the register, since it is so small, usually 1kb or less, the read write speed is fast 
## What will memory management do?
- Allocate and de-allocate memory for processes (performed by OS and improve the programming efficiency)
- Address translation (between physcial address and virtual address)
## What will happen when memory is not enough?
- Overlapping
    - Memory is small and cannot hold all program data
    - User space is dividd to one fixed space and several overlapping space
    - Fixed space: hold most frequent data
    - Overlapping space: the data will overlap those which never be used (after overlapping data is gone)
- Swapping
    - Leave memory and are swapped to disk
    - Re-enter memory by getting swapped in from disk
## How to organize memory?
- Page number and offset

