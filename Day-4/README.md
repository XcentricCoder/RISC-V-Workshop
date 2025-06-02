# Basic RISC-V CPU micro-architecture

  ![CPU Microarchitecture](https://github.com/XcentricCoder/RISC-V-Workshop/blob/main/Day-4/Screenshot%20from%202025-06-02%2022-28-36.png)


 # 🔍 CPU Block Diagram Explanation

# 📦 Component Descriptions
  | Component                               | Description                                                                                                                                |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **PC (Program Counter)**                | Holds the address of the current instruction. Updated every cycle to point to the next instruction or a branch target.                     |
| **+1 Adder**                            | Increments the PC by 1 (or 4 depending on instruction width). Used to move to the next sequential instruction.                             |
| **IMem Rd (Instruction Memory Read)**   | Fetches the instruction located at the address in the PC.                                                                                  |
| **Dec (Decoder)**                       | Decodes the fetched instruction to determine the control signals and extract fields like opcode, register addresses, and immediate values. |
| **RF Rd (Register File Read)**          | Reads source operands from the register file based on instruction fields.                                                                  |
| **ALU (Arithmetic Logic Unit)**         | Performs arithmetic and logic operations (add, sub, and, or, etc.) on the operands from the register file or immediate.                    |
| **+ (ALU input adder)**                 | Used for computing effective addresses in load/store instructions.                                                                         |
| **DMem Rd/Wr (Data Memory Read/Write)** | Performs memory access operations. Reads data for `lw` or writes data for `sw`.                                                            |
| **RF Wr (Register File Write)**         | Writes data back into the register file after execution or memory load.                                                                    |
| **Multiplexers (MUX)**                  | Used to select between values — for example, between ALU result and loaded data for writing back to the register file.                     |
| **Branch Target Logic**                 | Determines the target address for branch instructions, using the ALU or an adder and selecting via a MUX.                                  |


