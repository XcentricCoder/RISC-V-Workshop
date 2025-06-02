# RISC-V-Workshop

The “RISC-V based MYTH (Microprocessor for You in Thirty Hours)” workshop provides a structured introduction to RISC-V architecture, covering software-to-hardware concepts through hands-on labs. Participants begin with C programming, GCC compilation, and Spike simulation before progressing to number systems and assembly programming. The workshop delves into combinational and sequential logic, pipeline implementation, and microarchitecture of a single-cycle RISC-V CPU. Labs include instruction decoding, register file operations, ALU implementation, and control flow hazards. The final stages focus on load-store instructions, memory management, and CPU testbench development, offering comprehensive learning experience in microprocessor design and verification. This course is divided into 5 days, the summary of these days are given 

🧠 Learning Objectives

    🌐 Fundamentals of the RISC-V Instruction Set Architecture (ISA)
    💻 Writing and simulating RISC-V assembly programs
    🧩 Understanding how a basic RISC-V processor functions
    ⚙️ Practical experience with hardware simulators for RISC-V

# RISC-V CPU Core

This project implements a basic RISC-V (RV32I) CPU core, based on the open standard instruction set architecture (ISA) developed by the RISC-V Foundation. RISC-V is designed to be simple, modular, and extensible, making it ideal for research, education, and custom hardware development.

This implementation supports the 32-bit base integer instruction set (RV32I), featuring:

    Instruction fetch, decode, execute, and write-back stages
    Register file with 32 general-purpose registers
    Support for arithmetic, logical, control flow, and memory instructions
    Clean and modular Verilog codebase for easy extension

Ideal for learning CPU architecture, digital design, or integrating into larger SoC projects.

> ℹ️ **Note**  
> 1. Before moving on, you should know that all the tools like Linux, Spike, GNU compiler etc. are given separately to the student by the facilitator after buying this course.  
> 2. All the projects in Makerchip are made using the RISC-V/Calculator starter code, which is present in the [RISC-V_MYTH_Workshop](https://github.com/stevehoover/RISC-V_MYTH_Workshop). You can click the RISC-V/Calculator starter link present in the repository and make projects from there only.


# License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/LICENSE) file for details.



# Acknowledgements
I would thank to Kunal Ghosh sir who guided us over this workshop and also taught us the first two days of this workshop. I will also express my gratitude to Steve Hoover sir who taught us in the last 3 days. And also thank to VSD and Redwood EDA for organizing this workshop.


