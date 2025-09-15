---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/oop/05-constructor/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/oop"],"noteIcon":""}
---

# Constructor in C++

A **constructor** is a **special function** in a class that is **automatically called** when an object is **created**. It is used to **initialize objects**.

---

# Key Features of a Constructor

- Has **the same name** as the class
- **No return type** (not even `void`)
- Called **automatically** when an object is created
- Can be **overloaded** (multiple constructors with different parameters)

---

# Basic Example

```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string brand;

    // Constructor
    Car() {
        brand = "Unknown";
        cout << "Constructor called\n";
    }
};

int main() {
    Car myCar;         // Constructor is called automatically
    cout << myCar.brand;
}
```

**Output:**

```
Constructor called  
Unknown
```

---

# Parameterized Constructor

Allows passing values when creating the object.

```cpp
class Car {
public:
    string brand;

    // Constructor with parameter
    Car(string b) {
        brand = b;
    }
};

int main() {
    Car myCar("Toyota");
    cout << myCar.brand;
}
```

---

# Constructor Overloading

```cpp
class Car {
public:
    string brand;
    int year;

    Car() {
        brand = "Default";
        year = 2000;
    }

    Car(string b, int y) {
        brand = b;
        year = y;
    }
};
```

---

# Default Constructor

If you don’t define any constructor, C++ provides a **default constructor** automatically.
