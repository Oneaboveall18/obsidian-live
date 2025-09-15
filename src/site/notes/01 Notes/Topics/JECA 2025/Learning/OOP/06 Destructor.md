---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/oop/06-destructor/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/oop"],"noteIcon":""}
---

# Destructor in C++

A **destructor** is a **special member function** that is **automatically called** when an object goes **out of scope** or is **deleted**.  
Its main job is to **release resources** (like memory, file handles, network connections, etc.) used by the object.

---

# Key Features of Destructor

- Same name as the class but **with a `~` (tilde)** prefix
- **No return type** and **no parameters**
- **Only one destructor per class** (no overloading)
- Called **automatically** when the object is destroyed

---

# Basic Example

```cpp
#include <iostream>
using namespace std;

class Car {
public:
    Car() {
        cout << "Constructor called\n";
    }

    ~Car() {
        cout << "Destructor called\n";
    }
};

int main() {
    Car myCar;  // Constructor runs here
}               // Destructor runs here when myCar goes out of scope
```

**Output:**

```
Constructor called  
Destructor called
```

---

# Why Use Destructors?

To **clean up**:

- Dynamic memory (e.g., using `new`)
- File handles
- Database/network connections
- Custom resource management

---

# Important Notes

- **You don’t need to manually call** a destructor — it's handled by C++ automatically.
- If you're using **`new`**, make sure to use **`delete`**, and let the destructor handle cleanup inside.

---

# Real-World Analogy:

Imagine an object is a **party**:

- The **constructor** sets everything up (invites guests, decorates).
- The **destructor** cleans everything when the party is over (removes decorations, throws out trash).

---

# Summary:

|Feature|Destructor|
|---|---|
|Name|Same as class, with `~`|
|Return Type|None|
|Parameters|None|
|Overloadable|❌ No|
|Called when|Object is destroyed|
|Purpose|Free resources / clean up|
