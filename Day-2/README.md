# Introduction to ABI and basic verification flow


## 🧠 What is an ABI?

An **ABI (Application Binary Interface)** is a low-level contract between a compiled program and its runtime environment. It defines:

- How **functions receive parameters and return values**
- Which **registers** are used and preserved
- How the **stack** is managed
- How **system calls** are made
- Memory layout for data types (alignment, size)

This allows compiled programs, even from different compilers or languages, to interoperate correctly.

---
