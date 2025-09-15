---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/unix/04-shell-utilities-and-environment/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/unix"],"noteIcon":""}
---

# **Purpose** 

> Useful for scripting, searching, editing files, manipulating environment variables, and writing automation scripts.

---
# cut

**Definition:** Extracts specific sections (columns/fields) from each line of input.

|command|info|
|---|---|
|cut -c1-5 file.txt|**Cuts characters** 1 to 5 from each line of `file.txt`.|
|cut -d',' -f2 file.csv|**Cuts the 2nd field** from CSV using comma delimiter.|
|cut -f1,3 -d':' /etc/passwd|**Displays 1st and 3rd field** using colon as delimiter.|

---
# paste

**Definition:** Merges lines of files horizontally (side-by-side).

|command|info|
|---|---|
|paste file1.txt file2.txt|**Merges lines** from both files side-by-side.|
|paste -d',' file1 file2|**Uses comma** as delimiter instead of tab.|
|paste -s file.txt|**Serial merging**, joins all lines of file one after another.|

---
# grep

**Definition:** Searches for patterns in files using regular expressions.

|command|info|
|---|---|
|grep "error" log.txt|**Searches for 'error'** in `log.txt`.|
|grep -i "error" log.txt|**Case-insensitive search**.|
|grep -r "main" ./code/|**Recursively searches** inside a directory.|
|grep -v "DEBUG" app.log|**Inverts match**: shows lines not containing "DEBUG".|
|grep -n "hello" file.txt|**Displays line numbers** with matches.|

---
# env

**Definition:** Displays or sets environment variables.

|command|info|
|---|---|
|env|**Lists all environment variables**.|
|env VAR=val command|**Runs a command** with a temporary environment variable.|

---
# PATH

**Definition:** Environment variable that stores directories to search for executables.

|usage|info|
|---|---|
|echo $PATH|**Shows current search path** for executables.|
|export PATH=$PATH:/new/dir|**Adds `/new/dir`** to the current path.|

---
# CLASSPATH

**Definition:** Java environment variable that tells JVM where to find user-defined classes and packages.

|usage|info|
|---|---|
|echo $CLASSPATH|**Displays CLASSPATH**.|
|export CLASSPATH=.:/app/classes|**Sets CLASSPATH**, including current directory (`.`).|

---
# find

**Definition:** Searches for files and directories in a directory hierarchy.

|command|info|
|---|---|
|find . -name "*.txt"|**Finds all `.txt` files** recursively in current directory.|
|find / -type d -name "bin"|**Finds directories** named `bin`.|
|find . -size +1M|**Finds files larger** than 1 MB.|
|find . -mtime -7|**Files modified in the last 7 days**.|
|find . -exec rm {} ;|**Executes command** on found files (e.g., delete them).|

---
# vi editor

**Definition:** Text editor in UNIX systems, also known as `vim`.

| mode                | key usage / command | info                                           |
| ------------------- | ------------------- | ---------------------------------------------- |
| Normal mode         | `Esc`               | **Default mode**, navigate and issue commands. |
| Insert mode         | `i`, `a`, `o`       | **Type text** (press `Esc` to exit).           |
| Save                | `:w`                | **Writes file** (saves changes).               |
| Quit                | `:q`                | **Quits** vi (without saving if unchanged).    |
| Save & Quit         | `:wq` or `ZZ`       | **Saves and exits**.                           |
| Quit without saving | `:q!`               | **Forces exit**, discarding changes.           |
| Normal Mode         | `h`, `j`, `k`, `l`  | Move left, down, up, right.                    |
|                     | `0` or `^`          | Move to beginning of line.                     |
|                     | `$`                 | Move to end of line.                           |
|                     | `gg`, `G`           | First line, last line.                         |
|                     | `dd`                | Delete current line.                           |
|                     | `yy` or `Y`         | Yank (copy) current line.                      |
|                     | `u`                 | Undo last change.                              |
|                     | `Ctrl+r`            | Redo undone change.                            |
|                     | `/pattern`          | Search forward.                                |
|                     | `?pattern`          | Search backward.                               |

---
# shell

**Definition:** A command-line interface (e.g., bash, sh, zsh) to interact with the OS.

|usage|info|
|---|---|
|bash|**Starts the Bash shell**.|
|echo $SHELL|**Shows current shell** in use.|
|chsh -s /bin/zsh|**Changes the default shell** to `zsh`.|

---
# wildcard

**Definition:** Special characters used for pattern matching in filenames.

|wildcard|usage example|info|
|---|---|---|
|`*`|`*.txt`|**Matches all files** ending in `.txt`.|
|`?`|`file?.txt`|**Matches any single character** in file name.|
|`[]`|`file[1-3].txt`|**Matches character range**, e.g., file1.txt to file3.txt.|

---
# shell script

**Definition:** A file containing shell commands to be executed together.

|example|info|
|---|---|
|`#!/bin/bash`|**Shebang**: tells system which shell to use.|
|`echo "Hello"`|**Simple print statement** in shell.|
|`chmod +x script.sh`|**Makes shell script executable.**|
|`./script.sh`|**Runs the script** from current directory.|
