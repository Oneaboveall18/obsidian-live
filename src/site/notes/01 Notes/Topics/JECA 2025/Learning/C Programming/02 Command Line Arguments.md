---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/c-programming/02-command-line-arguments/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/c"],"noteIcon":""}
---

# **Command-Line Arguments in C**

**Command-line arguments** allow users to pass values (like file names, numbers, etc.) **from the terminal** to a C program **at the time of execution**.

# **Syntax of main() with arguments**

```c
int main(int argc, char *argv[])
```

| Parameter                  | Meaning                                             |
| -------------------------- | --------------------------------------------------- |
| `argc` (argument count)    | Number of arguments passed (including program name) |
| `argv[]` (argument vector) | Array of strings holding each argument              |

# **Important Points**

- `argv[0]` is always the **program name**
- `argc` ≥ 1
- All arguments are of type **string (`char*`)**
- You need to convert strings to int/float using `atoi()`, `atof()` if needed

---
# **Simple Example:**

```c
#include <stdio.h>

int main(int argc, char *argv[]) {
    printf("Total arguments: %d\n", argc);
    
    for (int i = 0; i < argc; i++) {
        printf("Argument %d: %s\n", i, argv[i]);
    }

    return 0;
}
```

## **If run like this:**

```bash
./program Hello World 123
```

## **Output:**

```
Total arguments: 4
Argument 0: ./program
Argument 1: Hello
Argument 2: World
Argument 3: 123
```

---

# **Why are CLI arguments useful?**

- To automate inputs (like filenames, flags, config).
- For utilities like `grep`, `cp`, `ls` that work from the shell.
- Reduces dependency on interactive `scanf()` inputs.

---

# Summary Table

|Element|Description|
|---|---|
|`argc`|Number of arguments|
|`argv[]`|Array of arguments|
|`argv[0]`|Name of executable|
|`argv[1..n]`|Actual user inputs|
|`atoi()`|Converts `char*` to `int`|
|`atof()`|Converts `char*` to `float`|
