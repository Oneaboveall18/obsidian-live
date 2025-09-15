---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/c-programming/preprocessor-directive/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/c"],"noteIcon":""}
---

# Definition

Preprocessor directives in C are special instructions that are processed before the actual compilation of the code begins. They are recognized by the C preprocessor and always start with the `#` symbol as the first non-whitespace character on a line. These directives are not C statements, so they do not require a semicolon at the end and are not included in the compiled object code.

---
# **Purpose and Function**

- Preprocessor directives manage code before it reaches the compiler.
- They can include files, define macros, control conditional compilation, and provide instructions to the compiler.
- The preprocessor scans the source code for these directives and processes them, transforming the code as needed before handing it off to the compiler.

---
# **Types of Preprocessor Directives**

There are several main categories of preprocessor directives in C:

## **1. Macro Substitution Directives**

- #define: Used to define macros, which are symbolic names for code or constants. When the macro name appears in the code, it is replaced by its value or code snippet before compilation.
    - Example: `#define PI 3.14159`
    - Macros can also have arguments: `#define SQUARE(x) ((x)*(x))`[2](https://pwskills.com/blog/what-are-preprocessor-directives-in-c/)[3](https://www.simplilearn.com/tutorials/c-tutorial/c-preprocessor-directives)[5](https://www.tutorialspoint.com/explain-the-pre-processor-directives-in-c-language).
        
- #undef: Used to undefine a previously defined macro.
    - Example: `#undef PI.

## **2. File Inclusion Directives**

- **include**: Inserts the contents of another file into the current file. This is commonly used for including standard library headers or user-defined header files.
    - Syntax: `#include <stdio.h>` (for standard headers), `#include "myheader.h"` (for user headers).
    - Angle brackets `< >` are used for standard library files, while double quotes `" "` are for user-defined files.

---
# **How Preprocessor Directives Work**

1. The preprocessor scans the source code for lines starting with `#`.
2. It processes these directives, modifying the code as instructed (e.g., replacing macros, including files, or removing/excluding code sections).
3. The output is a "preprocessed" source file, which is then sent to the compiler for actual compilation.

---
# **Key Points About Preprocessor Directives**

- They do not end with a semicolon.
- They can appear anywhere in the program, though they are often placed at the top.
- They are not part of the C language syntax, but instructions to the preprocessor.
- Preprocessing is always the first phase of compilation.

---
# **Summary Table**

| Directive | Purpose        | Example            |
| --------- | -------------- | ------------------ |
| #define   | Define macro   | #define MAX 100    |
| #undef    | Undefine macro | #undef MAX         |
| #include  | Include file   | #include <stdio.h> |

