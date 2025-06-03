# Introduction to RISC-V ISA and GNU Compiler Toolchain

RV_D1SK1_L1_Introduction

    Overview of the RISC-V Instruction Set Architecture (ISA).
    RISC-V Architecture (C) → Implementation (RTL, e.g., PicoRV32 core) → Layout (qflow for hardware).
    Layer mapping: Application layer → System software → Hardware layer.

RV_D1SK1_L2_From Apps To Hardware

    Software stack:
        Applications → System Software → OS → High-level languages (C, C++, Java, VB) → Compiler → ISA → Assembler
    Hardware flow:
        RTL snippet (understands instructions like add x6, x10, ...) → Synthesized netlist → Physical design implementation.


## Compute sum from 1 to n
      #include <stdio.h>
        int main() {
        int i, sum = 0, n = 100;
        for (i=1; i <= n; ++i) {
        sum += i; }
        printf("Sum of numbers from 1 to %d is %d\n", n, sum);
        return 0;
      }
This is the c code for adding numbers, make a file named 1ton.c and paste this in that file.

Steps to run this
                 
   1.       gcc 1ton.c

   2.       ./a.out

![gcc_pic1](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-1/Screenshot%20from%202025-06-03%2021-27-05.png)




2. Simulation of the same 1ton program but with Spike

Run the following steps in terminal:

   Open the terminal and type

   1.     riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o 1ton.o 1ton.c        


   2.     spike pk 1ton.o

Similar output should be seen!!!
    
