# Hello World in MIPS64 Assembly (Linux)

A simple Hello World implementation in MIPS64 assembly language for Linux systems. MIPS64 represents an evolution of the classic MIPS architecture, which has been widely used in embedded systems, gaming consoles, and networking equipment.

## Installation

On a MIPS64 Linux system, you'll need the standard GNU toolchain:

```bash
sudo apt-get update
sudo apt-get install binutils gcc
```

## Running

Assemble and link:
```bash
as -o main.o main.s
ld -o hello main.o
./hello
```

## Code Explanation

Our MIPS64 implementation demonstrates several key aspects of the architecture. MIPS64 is a 64-bit RISC architecture that maintains many design principles from its 32-bit predecessor while adding support for 64-bit operations.

The program uses MIPS64's register conventions:
- $v0: System call number
- $a0-$a2: Function arguments and system call parameters
- All registers in MIPS64 are 64 bits wide

Several MIPS64-specific features are demonstrated:
- The .rodata section for read-only data
- The .ent and .end directives that mark function boundaries
- The use of 64-bit load instructions (dli, dla) for addresses and constants

The implementation uses two system calls:
1. write (5001): Outputs our message to stdout
2. exit (5058): Terminates the program

Instructions used:
- dli (Double Load Immediate): Loads a 64-bit immediate value into a register
- dla (Double Load Address): Loads a 64-bit address into a register
- li (Load Immediate): Loads a 32-bit immediate value
- syscall: Makes a system call

The .align directives ensure proper alignment for both code and data, which is important for performance on MIPS64 processors.
