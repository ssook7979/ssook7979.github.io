# How programs run on machine

1. CPU looks for a specific program on RAM
2. if the program doesn’t exist on RAM then CPU looks for it on HD.
3. if the program is found, it is copies on HD and the copied file is called `process`.
- multiple processes can be created for one single program
- once the source of the program is translated into machine code by compiler and copied to RAM, then the copied program goes into one of these stages
    - executed by CPU
    - wait for I/O, event
    - wait to be executed

# Process

## States of a process

- new state
    - when a new process is created from the program
- ready state
    - when a process is copied to RAM and wait
- running state
    - when a process is being executed by CPU
- I/O state(block state)
    - when a process is undergoing I/O
- terminated state
    - once the process terminated itself
- suspend ready state
- suspend wait state

## Degree of Multiprogramming

- max number of processes that RAM can have

# Types of Operating Systems

## Batch Operating Systems

- can have only one process inside RAM
- single CPU
- concurrent processing

## Multi-programming OS

- can have more than one process
- single CPU
- concurrent processing

## Multi-processing OS

- more than one CPU
- parallel processing
- higher cost

# Process Attributes

- process Id
- program counter

section4 후반

# Terms

## CPU efficiency

= useful time of CPU / total time of CPU

## Units

1KB = 2^10 Bytes

1MB=2^20 Bytes

1GB = 2^30Bytes

1TB = 2^40Bytes

1Byte = 8bits

## Process

### passive entity

- process copied from program, like by user’s clicking it

### active entity

- process created by a program

## dynamic memory allocation

- memory allocation during an execution of process

### melloc()

### calloc()

## Process Control block