---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/oop/04-encapsulation/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/oop"],"noteIcon":""}
---

# Encapsulation in Object-Oriented Programming

**Encapsulation** is the process of **hiding the internal details** of how an object works and only exposing a controlled interface.  
It’s one of the **four core principles** of OOP (along with Abstraction, Inheritance, and Polymorphism).

---

# Key Idea

> **"Bind data and the functions that operate on that data into a single unit (class), and restrict direct access to some of the object's components."**

---

# Why Encapsulation?

- Protects object’s data from unwanted changes
- Makes the code modular and maintainable
- Allows validation logic (e.g., prevent setting negative age)
- Hides complexity and only shows what's necessary

---

# How Encapsulation is Achieved

1. **Make data members `private`**
2. **Provide `public` getter and setter methods** to access or modify the data

---

# C++ Example

```cpp
class Teacher
{
private:
    double salary;

public:
    string name;
    string dept;
    string subject;

    void changeDept(string newDept)
    {
        dept = newDept;
    }

    void setSalary(double salary)
    {
        this->salary = salary;
    }

    double getSalary()
    {
        return salary;
    }
};
```

---

# Real-Life Analogy

Think of a **vending machine**:

- You **can't access** the internal parts.
- You only interact with **buttons and money slot** — a **controlled interface**.

---

# Summary

| Concept       | Description                                                                 |
| ------------- | --------------------------------------------------------------------------- |
| Encapsulation | Binding data and methods together, and hiding the internal state of objects |
| How to do it  | Use `private` data + `public` getter/setter methods                         |
| Benefit       | Data protection, control, and clean interfaces                              |
