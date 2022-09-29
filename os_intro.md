# Hardware

- CPU
- Memory
    1. **RAM**
        1. related to running time
        2. accessing is faster than harddisk
    2. **Harddisk(permanent)**
    3. Cache
    4. Registers
- Running Programs
    - Harddisk —(copied and pasted)→ RAM(software, data) → CPU runs line by line(execution)

# How hardware devices work together

cpu only understands `binary code(machine code)`

high level language —(compiler)→machine code

CPU can’t access hd directly

CPU

CPU is set to run program P1

CPU searches program P1 inside RAM

if P1 is not present in RAM, then P1 inside hd is copied and pasted in RAM

# Operating system

- Resource Manager
    - Resource allocation
    - resource: CPU, RAM, HD, …
- RAM holds programs frm HD that CPU most likely to refer
    - controled by OS algorithm
        - ex) decide which process should access CPU first
        - Short Term Scheduler
        - Long Term Scheduler

# CPU

- CU
- ALU
    - do all the mathematical operation

# RAM

- OS space
    - Operating System’s programs are loaded inside RAM
- User space
    - once done the space occupied by the program is cleared(released)

# Devices

- keyboards, monitor …(i/o)
- every device has buffer(memory, register)
    - keeps data as a binary format that is to come from / go to cpu or ram

# HD

- input / output(read / write) device

- Execution
- I/O event
- waiting (for some event to happen)

# Turn around time

- Waiting time + Burst time(execution time) + I/O time
- on RAM ~ Cleared from RAM