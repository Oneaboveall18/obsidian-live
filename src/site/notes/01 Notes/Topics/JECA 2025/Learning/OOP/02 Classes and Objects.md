---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/oop/02-classes-and-objects/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/oop"],"noteIcon":""}
---

# **Class**

A **class** is like a **blueprint** or **template** for creating objects. It defines **what data** (attributes) and **what operations** (methods) the objects will have.

**Syntax (C++ Example):**
```cpp
class Car {
	public:
	    string brand;
	    int year;
	
	    void start() {
	        cout << "Car started\n";
	    }
};
```

- `brand` and `year` are **attributes**
- `start()` is a **method**
- No memory is allocated until you create an object.

---

### **Object**

An **object** is an **instance of a class**. It has its own **copy of the class's attributes and methods**.

**Example:**
```cpp
int main() {
    Car myCar;               // Creating object
    myCar.brand = "Toyota";  // Setting attributes
    myCar.year = 2020;
    myCar.start();           // Calling method
}
```

- `myCar` is an **object** of class `Car`
- It has its **own values** for `brand` and `year`