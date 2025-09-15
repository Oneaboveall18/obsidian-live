---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/oop/01-introduction/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/oop"],"noteIcon":""}
---

**Object-Oriented Programming (OOP)** is a programming paradigm based on the concept of **"objects"**, which are instances of **classes**. These objects contain **data** (called attributes or properties) and **behavior** (called methods or functions).

---

# Key Concepts of OOP

1. **Class**: A blueprint or template for creating objects.  
    Example: `Car` is a class.
    
2. **Object**: An instance of a class.  
    Example: `myCar` is an object of class `Car`.
    
3. **Encapsulation**: Bundling data and methods that operate on that data into a single unit (class), and restricting direct access to some of the object's components.  
    → Achieved using access modifiers like `private`, `public`, etc.
    
4. **Abstraction**: Hiding complex implementation details and showing only the essential features.  
    → Focus on _what_ an object does instead of _how_ it does it.
    
5. **Inheritance**: A mechanism where a new class (child) derives properties and behavior from an existing class (parent).  
    → Promotes code reuse.
    
6. **Polymorphism**: Ability of different objects to respond to the same method in different ways.  
    → Types: Compile-time (method overloading) and Run-time (method overriding).

---
# Procedure-Oriented Programming

![[unnamed 1.png\|unnamed 1.png]]

In high level language like **COBOL**, **FORTRAN** and **C** the programming in it is known as procedure-oriented programming (POP). In it, the problem is viewed as a sequence of things to accomplish such as reading, calculating and printing. For this a number of functions are written and the primary focus is on functions to achieve the tasks.

Some of the stinking features of object-oriented programming are: 

- Emphasis is on **functions and procedures** rather than data.
- The program is divided into **functions** or **procedures**, which perform specific tasks.
- Data is typically **shared globally** and passed between functions.
- Functions are written to **perform operations on data**, but data and functions are kept separate.
- **Little or no data hiding** — data can be accessed and modified by any function.
- Focus is on **sequence of actions** to be performed (algorithm-centric approach).
- **Code reuse is limited**, and changes in data structures may require changes in many functions.

# Object Oriented Programming Paradigm

![[1_mXs_vkZeHdfNQWYkyxzvTQ.png\|1_mXs_vkZeHdfNQWYkyxzvTQ.png]]

The major motivating factor in the invention of object-oriented approach is to remove some of the flows encountered in the procedural approach. 00P treats data on a critical element in the program development and does not allow it to flow freely around the system. It ties data more closely to the functions that operate on it, and protects it from accidental modification from outside functions.

Some of the stinking features of object-oriented programming are: 

- Emphasis is on data rather than procedure. 
- Programs are divided into what are known as objects 
- Data structures are designed such that they characterize the objects. 
- Functions that operate on the data of an object are tied together in the data structure. 
- Data is hidden and cannot be accessed by external functions.
- Objects may communicate with each other through functions.
- New data and functions can be easily added whenever necessary.