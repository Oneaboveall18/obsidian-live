---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/introduction-to-computers/05-system-calls/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/intro-to-computers"],"noteIcon":""}
---

# **Introduction**

A **system call** is a **programmatic way** for a **user-level program** to **request services from the operating system's kernel**. It acts as a **bridge between user space and kernel space**, allowing a program to **interact with hardware and resources** (like files, memory, and processes) **safely** and **in a controlled way**.

---
## **Why System Calls Are Needed**

User programs **cannot directly access** hardware (like CPU registers, memory, files) for security and stability. So they ask the OS to do it on their behalf via **system calls**.

---
## **Real-life Analogy**

Imagine a customer (user program) at a bank (OS). The customer **fills a form (system call)** and **hands it to the teller (kernel)** to request a service like depositing money (writing to disk).

---
## **Types of System Calls**

|Category|Examples|Description|
|---|---|---|
|1. **Process Control**|`fork()`, `exec()`, `exit()`, `wait()`|Create, execute, and manage processes|
|2. **File Management**|`open()`, `read()`, `write()`, `close()`, `delete()`|Operate on files and directories|
|3. **Device Management**|`ioctl()`, `read()`, `write()`|Access and control hardware devices|
|4. **Information Maintenance**|`getpid()`, `alarm()`, `sleep()`|Get process info, system time, etc.|
|5. **Communication**|`pipe()`, `shmget()`, `send()`, `recv()`|Inter-process communication (IPC), networking|

---
## **How a System Call Works**

1. **User program calls a library function** (e.g., `printf()`).
2. The library internally makes a **system call** (e.g., `write()`).
3. Control switches from **user mode to kernel mode**.
4. The **OS executes** the request (e.g., writing to file).
5. **Control returns** to user mode with result.

---

## **Example (in Linux C Code):**

```c
#include <unistd.h>
#include <stdio.h>

int main() {
    write(1, "Hello, There!\n", 13);  // system call to write to stdout (fd 1)
    return 0;
}
```

Here, `write()` is a **system call** that prints text to the screen.

---

## **User Mode vs Kernel Mode:**

|Mode|Access Level|
|---|---|
|User Mode|Limited access – can’t touch hardware directly|
|Kernel Mode|Full access – can interact with hardware, memory, I/O|

System calls **switch** from user mode → kernel mode → back.