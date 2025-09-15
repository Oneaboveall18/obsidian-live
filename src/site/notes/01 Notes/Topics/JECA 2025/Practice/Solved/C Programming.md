---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/practice/solved/c-programming/","noteIcon":""}
---

# JECA Mock Exam – C Programming (Full 50 Questions)

> [!info] Instructions
> - Category 1: 30 questions, 1 mark each, negative marking –0.25 for wrong answers.
> - Category 2: 20 questions, 2 marks each, multiple correct possible, no negative marks.
> - Total Marks = 30 + 40 = **70**.

---
# Category 1

*(Carry 1 mark each. Only one option is correct. Negative marks: –¼)*

1. Which of the following is a valid C identifier?
   - [x] (a) int
   - [ ] (b) 9data
   - [ ] (c) _value
   - [ ] (d) a-b


2. The `sizeof(char)` in C is always:

   - [ ] (a) 1 byte
   - [ ] (b) 2 bytes
   - [ ] (c) 4 bytes
   - [x] (d) Depends on system
  

3. Which function is used to read a character from the keyboard (without echo)?

   - [ ] (a) getchar()
   - [ ] (b) getch()
   - [ ] (c) getche()
   - [x] (d) scanf()


4. What will `10 % 3` evaluate to?

   - [x] (a) 1
   - [ ] (b) 3
   - [ ] (c) 0
   - [ ] (d) 2
  

5. Which of the following is not a relational operator?

   - [ ] (a) ==
   - [ ] (b) !=
   - [x] (c) &&
   - [ ] (d) <=
  

6. The ternary operator in C is:

   - [x] (a) ?:
   - [ ] (b) ::
   - [ ] (c) ??
   - [ ] (d) if-else
  

7. Which loop is guaranteed to execute at least once?

   - [ ] (a) for
   - [ ] (b) while
   - [x] (c) do-while
   - [ ] (d) switch


8. What is the output of:

   ```c
   int x = 5;
   printf("%d", x++);
   ```

    - [x] (a) 6
    - [ ] (b) 5
    - [ ] (c) Error
    - [ ] (d) Undefined
  

9. Which keyword is used to return control from a function?

   - [ ] (a) continue
   - [ ] (b) exit
   - [ ] (c) break
   - [x] (d) return
  

10. Which is the correct syntax to declare an array of 10 integers?

    - [x] (a) int arr\[10];
    - [ ] (b) int arr(10);
    - [ ] (c) array int arr\[10];
    - [ ] (d) int\[10] arr;
  

11. Array indexing in C starts from:

    - [ ] (a) –1
    - [x] (b) 0
    - [ ] (c) 1
    - [ ] (d) Depends on compiler
  

12. Which format specifier is correct for `double`?

    - [ ] (a) %d
    - [x] (b) %f
    - [ ] (c) %lf
    - [ ] (d) %c
  

13. Which function is used to copy one string into another?

    - [x] (a) strcpy
    - [ ] (b) strcat
    - [ ] (c) strcmp
    - [ ] (d) strlen


14. Which operator is used to access members of a structure through a pointer?

    - [ ] (a) .
    - [x] (b) ->
    - [ ] (c) \*
    - [ ] (d) &
  

15. Which of the following is not a valid storage class in C?

    - [ ] (a) auto
    - [x] (b) static
    - [ ] (c) dynamic
    - [ ] (d) register
  

16. Which of the following is not a valid string function?

    - [ ] (a) strlen
    - [x] (b) strrev
    - [ ] (c) strcat
    - [ ] (d) strcopy


17. Which of the following is the default return type of a function in C (if not specified)?

    - [x] (a) void
    - [ ] (b) int
    - [ ] (c) float
    - [ ] (d) char
  

18. Which of the following operators is right-associative?

    - [x] (a) =
    - [ ] (b) \*
    - [ ] (c) +
    - [ ] (d) %
  

19. Which of the following cannot be checked in a `switch` statement?

    - [ ] (a) int
    - [ ] (b) char
    - [ ] (c) enum
    - [x] (d) float
  

20. What does `fseek(fp, 0, SEEK_END)` do?

    - [ ] (a) Goes to beginning of file
    - [x] (b) Goes to end of file
    - [ ] (c) Goes to middle of file
    - [ ] (d) Closes file
  

21. In C, a pointer is:

    - [ ] (a) A keyword
    - [x] (b) A variable storing an address
    - [ ] (c) A function
    - [ ] (d) An operator
  

22. Which is true about arrays in C?

    - [ ] (a) Array size can be changed at runtime
    - [x] (b) Array index starts from 0
    - [ ] (c) Array elements are not stored contiguously
    - [ ] (d) Array is a primitive data type
  

23. Which keyword is used to prevent modification of a variable?

    - [ ] (a) static
    - [x] (b) final
    - [ ] (c) const
    - [ ] (d) immutable
  

24. Which function is used to open a file in C?

    - [x] (a) fopen
    - [ ] (b) open
    - [ ] (c) create
    - [ ] (d) fileopen
  

25. Which escape sequence is used for newline?

    - [x] (a) \n
    - [ ] (b) \t
    - [ ] (c) \r
    - [ ] (d) \0
  

26. The base address of an array is:

    - [ ] (a) Address of last element
    - [ ] (b) Address of array name
    - [x] (c) Address of first element
    - [ ] (d) Size of array
  

27. What is the output of:

    ```c
    int a=5, b=2;
    printf("%d", a/b);
    ```

    - [ ] (a) 2.5
    - [x] (b) 2
    - [ ] (c) 3
    - [ ] (d) Error
  

28. Which function is used to allocate memory dynamically in C?

    - [x] (a) malloc
    - [ ] (b) calloc
    - [ ] (c) realloc
    - [ ] (d) free
  

29. The `#include` directive is processed by:

    - [ ] (a) Compiler
    - [x] (b) Preprocessor
    - [ ] (c) Linker
    - [ ] (d) Loader
  

30. Which of the following is the correct prototype of `main()` with command-line arguments?

    - [ ] (a) int main(int argc, char \*argv\[])
    - [ ] (b) void main(char argc, int argv\[])
    - [ ] (c) int main(char argc, char argv\[])
    - [ ] (d) main(int argc, char argv)

---
# Category 2
*(Carry 2 marks each. One or more options are correct. No negative marks)*

31. Which of the following are keywords in C?

    - [x] (a) if
    - [x] (b) goto
    - [x] (c) switch
    - [ ] (d) include


32. Which of the following are valid arithmetic operators in C?

    - [x] (a) +
    - [x] (b) –
    - [x] (c) /
    - [ ] (d) &&


33. Which of the following are valid loop constructs?

    - [x] (a) for
    - [x] (b) while
    - [x] (c) foreach
    - [x] (d) do-while
  

34. Which of the following functions are valid string functions?

    - [ ] (a) strcmp
    - [x] (b) strcat
    - [x] (c) strset
    - [x] (d) strcpy
  

35. Which of the following operators are increment/decrement operators?
  
    - [x] (a) ++
    - [ ] (b) ––
    - [ ] (c) +=
    - [x] (d) --
  

36. Which are valid properties of `struct` in C?

    - [x] (a) Members are stored in contiguous memory
    - [x] (b) Members can be of different data types
    - [x] (c) Size of struct = sum of member sizes (with possible padding)
    - [ ] (d) Only one member can hold value at a time
  

37. Which are valid properties of a union?

    - [ ] (a) All members share the same memory location
    - [ ] (b) Union size = size of largest member
    - [ ] (c) More than one member can hold values at once
    - [ ] (d) Only one member’s value is valid at a time
  

38. Which of the following statements about pointers are true?

    - [x] (a) A pointer stores an address
    - [x] (b) \* is the dereference operator
    - [x] (c) & is the address-of operator
    - [ ] (d) Pointer arithmetic allows addition/subtraction
  

39. Which of the following are valid file handling functions?

    - [x] (a) fopen
    - [x] (b) fclose
    - [x] (c) fprintf
    - [ ] (d) fscan
  

40. Which of the following are valid storage classes in C?

    - [ ] (a) auto
    - [x] (b) register
    - [x] (c) static
    - [ ] (d) constant
  

41. Which of the following are conditional constructs in C?

    - [x] (a) if-else
    - [x] (b) switch
    - [x] (c) ?:
    - [ ] (d) repeat-until


42. Which of the following about arrays are true?

    - [ ] (a) Array elements are stored in contiguous memory
    - [x] (b) Array name represents base address
    - [x] (c) Array indices start from 0
    - [ ] (d) Array size must be constant
  

43. Which escape sequences are valid in C?

    - [x] (a) \n
    - [x] (b) \t
    - [ ] (c) \p
    - [ ] (d) \r


44. Which of the following are preprocessor directives?

    - [x] (a) #include
    - [x] (b) #define
    - [ ] (c) #pragma
    - [x] (d) #typedef
  

45. Which statements about dynamic memory allocation are true?

    - [x] (a) malloc allocates memory
    - [x] (b) calloc allocates and initializes memory
    - [x] (c) realloc resizes memory
    - [x] (d) free releases memory
  

46. Which of the following can be used as `switch` case expressions?

    - [x] (a) int constants
    - [x] (b) char constants
    - [ ] (c) float constants
    - [x] (d) enum constants
  

47. Which of the following are correct about command line arguments?

    - [ ] (a) argc counts arguments
    - [ ] (b) argv is an array of char pointers
    - [ ] (c) argv\[0] is program name
    - [ ] (d) argv\[argc] is NULL
  

48. Which of the following are true about recursion in C?

    - [x] (a) Function calls itself
    - [x] (b) Requires base condition
    - [x] (c) Uses stack internally
    - [ ] (d) Cannot be used with functions
  

49. Which are valid ways to declare a pointer?

    - [x] (a) int \*p;
    - [x] (b) float \*p;
    - [x] (c) char p\*;
    - [x] (d) double \*ptr;
  

50. Which are true about macros in C?

    - [x] (a) Defined using #define
    - [ ] (b) No type checking is done
    - [x] (c) They are evaluated at compile time
    - [x] (d) They consume memory at runtime