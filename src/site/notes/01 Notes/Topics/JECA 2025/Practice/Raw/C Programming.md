---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/practice/raw/c-programming/","noteIcon":""}
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

   - (a) int
   - (b) 9data
   - (c) _value
   - (d) a-b


2. The `sizeof(char)` in C is always:

   - (a) 1 byte
   - (b) 2 bytes
   - (c) 4 bytes
   - (d) Depends on system
  

3. Which function is used to read a character from the keyboard (without echo)?

   - (a) getchar()
   - (b) getch()
   - (c) getche()
   - (d) scanf()


4. What will `10 % 3` evaluate to?

   - (a) 1
   - (b) 3
   - (c) 0
   - (d) 2
  

5. Which of the following is not a relational operator?

   - (a) ==
   - (b) !=
   - (c) &&
   - (d) <=
  

6. The ternary operator in C is:

   - (a) ?:
   - (b) ::
   - (c) ??
   - (d) if-else
  

7. Which loop is guaranteed to execute at least once?

   - (a) for
   - (b) while
   - (c) do-while
   - (d) switch


8. What is the output of:

   ```c
   int x = 5;
   printf("%d", x++);
   ```

    - (a) 6
    - (b) 5
    - (c) Error
    - (d) Undefined
  

9. Which keyword is used to return control from a function?

   - (a) continue
   - (b) exit
   - (c) break
   - (d) return
  

10. Which is the correct syntax to declare an array of 10 integers?

    - (a) int arr\[10];
    - (b) int arr(10);
    - (c) array int arr\[10];
    - (d) int\[10] arr;
  

11. Array indexing in C starts from:

    - (a) –1
    - (b) 0
    - (c) 1
    - (d) Depends on compiler
  

12. Which format specifier is correct for `double`?

    - (a) %d
    - (b) %f
    - (c) %lf
    - (d) %c
  

13. Which function is used to copy one string into another?

    - (a) strcpy
    - (b) strcat
    - (c) strcmp
    - (d) strlen


14. Which operator is used to access members of a structure through a pointer?

    - (a) .
    - (b) ->
    - (c) \*
    - (d) &
  

15. Which of the following is not a valid storage class in C?

    - (a) auto
    - (b) static
    - (c) dynamic
    - (d) register
  

16. Which of the following is not a valid string function?

    - (a) strlen
    - (b) strrev
    - (c) strcat
    - (d) strcopy


17. Which of the following is the default return type of a function in C (if not specified)?

    - (a) void
    - (b) int
    - (c) float
    - (d) char
  

18. Which of the following operators is right-associative?

    - (a) =
    - (b) \*
    - (c) +
    - (d) %
  

19. Which of the following cannot be checked in a `switch` statement?

    - (a) int
    - (b) char
    - (c) enum
    - (d) float
  

20. What does `fseek(fp, 0, SEEK_END)` do?

    - (a) Goes to beginning of file
    - (b) Goes to end of file
    - (c) Goes to middle of file
    - (d) Closes file
  

21. In C, a pointer is:

    - (a) A keyword
    - (b) A variable storing an address
    - (c) A function
    - (d) An operator
  

22. Which is true about arrays in C?

    - (a) Array size can be changed at runtime
    - (b) Array index starts from 0
    - (c) Array elements are not stored contiguously
    - (d) Array is a primitive data type
  

23. Which keyword is used to prevent modification of a variable?

    - (a) static
    - (b) final
    - (c) const
    - (d) immutable
  

24. Which function is used to open a file in C?

    - (a) fopen
    - (b) open
    - (c) create
    - (d) fileopen
  

25. Which escape sequence is used for newline?

    - (a) \n
    - (b) \t
    - (c) \r
    - (d) \0
  

26. The base address of an array is:

    - (a) Address of last element
    - (b) Address of array name
    - (c) Address of first element
    - (d) Size of array
  

27. What is the output of:

    ```c
    int a=5, b=2;
    printf("%d", a/b);
    ```

    - (a) 2.5
    - (b) 2
    - (c) 3
    - (d) Error
  

28. Which function is used to allocate memory dynamically in C?

    - (a) malloc
    - (b) calloc
    - (c) realloc
    - (d) free
  

29. The `#include` directive is processed by:

    - (a) Compiler
    - (b) Preprocessor
    - (c) Linker
    - (d) Loader
  

30. Which of the following is the correct prototype of `main()` with command-line arguments?

    - (a) int main(int argc, char \*argv\[])
    - (b) void main(char argc, int argv\[])
    - (c) int main(char argc, char argv\[])
    - (d) main(int argc, char argv)

---
# Category 2
*(Carry 2 marks each. One or more options are correct. No negative marks)*

31. Which of the following are keywords in C?

    - (a) if
    - (b) goto
    - (c) switch
    - (d) include


32. Which of the following are valid arithmetic operators in C?

    - (a) +
    - (b) –
    - (c) /
    - (d) &&


33. Which of the following are valid loop constructs?

    - (a) for
    - (b) while
    - (c) foreach
    - (d) do-while
  

34. Which of the following functions are valid string functions?

    - (a) strcmp
    - (b) strcat
    - (c) strset
    - (d) strcpy
  

35. Which of the following operators are increment/decrement operators?
  
    - (a) ++
    - (b) ––
    - (c) +=
    - (d) --
  

36. Which are valid properties of `struct` in C?

    - (a) Members are stored in contiguous memory
    - (b) Members can be of different data types
    - (c) Size of struct = sum of member sizes (with possible padding)
    - (d) Only one member can hold value at a time
  

37. Which are valid properties of a union?

    - (a) All members share the same memory location
    - (b) Union size = size of largest member
    - (c) More than one member can hold values at once
    - (d) Only one member’s value is valid at a time
  

38. Which of the following statements about pointers are true?

    - (a) A pointer stores an address
    - (b) \* is the dereference operator
    - (c) & is the address-of operator
    - (d) Pointer arithmetic allows addition/subtraction
  

39. Which of the following are valid file handling functions?

    - (a) fopen
    - (b) fclose
    - (c) fprintf
    - (d) fscan
  

40. Which of the following are valid storage classes in C?

    - (a) auto
    - (b) register
    - (c) static
    - (d) constant
  

41. Which of the following are conditional constructs in C?

    - (a) if-else
    - (b) switch
    - (c) ?:
    - (d) repeat-until


42. Which of the following about arrays are true?

    - (a) Array elements are stored in contiguous memory
    - (b) Array name represents base address
    - (c) Array indices start from 0
    - (d) Array size must be constant
  

43. Which escape sequences are valid in C?

    - (a) \n
    - (b) \t
    - (c) \p
    - (d) \r


44. Which of the following are preprocessor directives?

    - (a) #include
    - (b) #define
    - (c) #pragma
    - (d) #typedef
  

45. Which statements about dynamic memory allocation are true?

    - (a) malloc allocates memory
    - (b) calloc allocates and initializes memory
    - (c) realloc resizes memory
    - (d) free releases memory
  

46. Which of the following can be used as `switch` case expressions?

    - (a) int constants
    - (b) char constants
    - (c) float constants
    - (d) enum constants
  

47. Which of the following are correct about command line arguments?

    - (a) argc counts arguments
    - (b) argv is an array of char pointers
    - (c) argv\[0] is program name
    - (d) argv\[argc] is NULL
  

48. Which of the following are true about recursion in C?

    - (a) Function calls itself
    - (b) Requires base condition
    - (c) Uses stack internally
    - (d) Cannot be used with functions
  

49. Which are valid ways to declare a pointer?

    - (a) int \*p;
    - (b) float \*p;
    - (c) char p\*;
    - (d) double \*ptr;
  

50. Which are true about macros in C?

    - (a) Defined using #define
    - (b) No type checking is done
    - (c) They are evaluated at compile time
    - (d) They consume memory at runtime
