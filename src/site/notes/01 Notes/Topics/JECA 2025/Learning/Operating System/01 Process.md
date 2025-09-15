---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/operating-system/01-process/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/os"],"noteIcon":""}
---

# Introduction

A process is a program in execution. For example, when we write a program in C or C++ and compile it, the compiler creates binary code. The original code and binary code are both programs. When we actually run the binary code, it becomes a process.

- A process is an 'active' entity instead of a program, which is considered a *passive* entity.
- A single program can create many processes when run multiple times; for example, when we open a .exe or binary file multiple times, multiple instances begin (multiple processes are created)

# **How Does a Process Look Like in Memory?**

A process in memory is divided into several distinct sections, each serving a different purpose. Here's how a process typically looks in memory:
![[process.png\|process.png]]

- ****Text Section****: A text or code segment contains executable instructions. It is typically a read only section
- ****Stack****: The stack contains temporary data, such as function parameters, returns addresses, and local variables. 
- ****Data Section****: Contains the global variable. 
- **Heap Section**: ***Dynamically memory allocated*** to process during its run time.