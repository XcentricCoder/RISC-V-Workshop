# Introduction to ABI and basic verification flow


## 🧠 What is an ABI?

An **ABI (Application Binary Interface)** is a low-level contract between a compiled program and its runtime environment. It defines:

- How **functions receive parameters and return values**
- Which **registers** are used and preserved
- How the **stack** is managed
- How **system calls** are made
- Memory layout for data types (alignment, size)

This allows compiled programs, even from different compilers or languages, to interoperate correctly.


![Pic](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-2/Screenshot%20from%202025-06-03%2022-51-15.png)


1. simulating the 1 to n adder but using ABI

Run the following steps in the terminal:

  Open the terminal and make a file names 1to9_custom.c

   and type this in it

  
     #include <stdio.h>
    
     extern int load(int x, int y); 
    
     int main() {
         int result = 0;
    	        int count = 2;
             result = load(0x0, count+1);
             printf("Sum of number from 1 to %d is %d\n", count, result); 
     }

2. Also make another file named load.S. And type this in it


       .section .text
       .global load
       .type load, @function
      
       load:
           add 	a4, a0, zero //Initialize sum register a4 with 0x0
           add 	a2, a0, a1   // store count of 10 in register a2. Register a1 is loaded with 0xa (decimal 10) from main program
           add	a3, a0, zero // initialize intermediate sum register a3 by 0
       loop:	add 	a4, a3, a4   // Incremental addition
           addi 	a3, a3, 1    // Increment intermediate register by 1	
           blt 	a3, a2, loop // If a3 is less than a2, branch to label named <loop>
           add	a0, a4, zero // Store final result to register a0 so that it can be read by main program
           ret


  3. Then open the terminal and type this after going to the folder in which you have made the two files

         riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o 1to9_custom.o 1to9_custom.c load.S


  4. Then type

           spike pk 1to9_custom.o

     
          
