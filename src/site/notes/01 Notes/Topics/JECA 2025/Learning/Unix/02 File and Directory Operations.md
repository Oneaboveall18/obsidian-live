---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/unix/02-file-and-directory-operations/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/unix"],"noteIcon":""}
---

# **Purpose** 

> These commands are used for listing files, navigating directories, copying/moving files, comparing files, and checking file info.

---

# ls

**Definition:** Lists files and directories in the current directory.

| command | info                                                                              |
| ------- | --------------------------------------------------------------------------------- |
| ls      | **List information** about the FILEs (the current directory by default)           |
| ls -l   | **Long listing format** with permissions, ownership, size, and modification date. |
| ls -a   | **Lists all files**, including hidden files (those starting with `.`).            |
| ls -la  | **Combines** long format and shows all files, including hidden ones.              |
| ls -S   | **Sorts files by size**, largest first.                                           |
| ls -t   | **Sorts files by modification time**, newest first.                               |
| ls -i   | **Displays the inode number** of each file or folders.                            |

---
# pwd

**Definition:** Prints the current working directory path.

|command|info|
|---|---|
|pwd|**Prints** the full pathname of the current directory.|

---
# mv

**Definition:** Moves or renames files and directories.

|command|info|
|---|---|
|mv file1 file2|**Renames** `file1` to `file2`.|
|mv file.txt dir/|**Moves** `file.txt` into the directory `dir/`.|
|mv -i file1 file2|**Interactive mode**: asks before overwriting the destination.|
|mv -v file1 file2|**Verbose mode**: shows what is being moved or renamed.|

---
# cp

**Definition:** Copies files and directories.

|command|info|
|---|---|
|cp file1 file2|**Copies** `file1` to `file2`.|
|cp file.txt dir/|**Copies** `file.txt` into the directory `dir/`.|
|cp -i file1 file2|**Interactive**: prompts before overwrite.|
|cp -r dir1 dir2|**Recursively copies** directory and all contents.|
|cp -v file1 file2|**Verbose**: displays what is being copied.|

---

# touch

**Definition:** Creates an empty file or updates the timestamp.

| command           | info                                                    |
| ----------------- | ------------------------------------------------------- |
| touch file.txt    | **Creates** an empty file `file.txt`.                   |
| touch -c file.txt | **Does not create** a file if it doesn't already exist. |
| touch -a file.txt | Change **access time** only                             |
| touch -m file.txt | Change **modification time** only                       |

---
# cat

**Definition:** Displays contents of files.

|command|info|
|---|---|
|cat file.txt|**Displays** contents of `file.txt`.|
|cat -n file.txt|**Numbers** each output line.|
|cat file1 file2 > merged.txt|**Concatenates** multiple files into one.|

---
# time

**Definition:** Measures execution time of a command.

|command|info|
|---|---|
|time ls|**Measures** how long the `ls` command takes.|
|time -p ls|**POSIX format** time output (real, user, sys).|

---
# cal

**Definition:** Displays a calendar.

|command|info|
|---|---|
|cal|**Displays** the current month's calendar.|
|cal 12 2025|**Displays** calendar for December 2025.|

---
# bc

**Definition:** A command-line calculator.

|command|info|
|---|---|
|echo "2+3" \| bc|**Evaluates** and returns `5`.|
|bc -l|**Loads math library** for functions like `s()`, `l()`, `sqrt()`.|

---
# sort

**Definition:** Sorts lines in a file or input.

|command|info|
|---|---|
|sort file.txt|**Sorts** the lines of the file alphabetically.|
|sort -r file.txt|**Sorts in reverse** order.|
|sort -n numbers.txt|**Sorts numerically** rather than alphabetically.|

---
# diff

**Definition:** Compares two files line by line.

|command|info|
|---|---|
|diff file1.txt file2.txt|**Displays line differences** between files.|
|diff -y file1 file2|**Shows** differences side-by-side.|

---

# cmp

**Definition:** Compares two files byte by byte.

|command|info|
|---|---|
|cmp file1.txt file2.txt|**Shows** first difference (byte/line number).|
|cmp -l file1 file2|**Lists all differing bytes**.|

---
# file

**Definition:** Tells the file type.

|command|info|
|---|---|
|file myfile|**Shows** the type of file (`ASCII text`, etc.).|

---
# whereis

**Definition:** Locates binary, source, and man page for a command.

|command|info|
|---|---|
|whereis ls|**Shows** binary and man page locations for `ls`.|
|whereis gcc|**Locates** compiler binaries and documentation.|

---
# which

**Definition:** Shows the path of the executable found in your `PATH`.

|command|info|
|---|---|
|which python|**Displays** the path to the `python` binary.|
|which gcc|**Tells** where `gcc` is located in the system.|

---
# echo

**Definition:** Displays a line of text.

|command|info|
|---|---|
|echo "Hello"|**Prints** Hello to the terminal.|
|echo -n "No newline"|**Suppresses** trailing newline character.|
|echo $HOME|**Prints** the value of the environment variable `HOME`.|