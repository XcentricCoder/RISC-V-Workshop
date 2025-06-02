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
