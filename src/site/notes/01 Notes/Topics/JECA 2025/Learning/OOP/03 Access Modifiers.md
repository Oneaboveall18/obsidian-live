---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/oop/03-access-modifiers/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/oop"],"noteIcon":""}
---

# Access Modifiers in Object-Oriented Programming

**Access modifiers** define **who can access** the members (variables and methods) of a class.  
They are used to implement **encapsulation** — one of the pillars of OOP.

---

# Three Main Access Modifiers (C++, Java, etc.)

| Modifier    | Description         | Accessible From                                   |
| ----------- | ------------------- | ------------------------------------------------- |
| `public`    | Open to all         | Anywhere                                          |
| `private`   | Hidden from outside | Inside the same class only                        |
| `protected` | Partially hidden    | Inside the same class and derived (child) classes |

---

# Example in C++:

```cpp
class Car {
	private:
	    int speed; // only accessible inside Car
	
	protected:
	    string engineType; // accessible in Car and its derived classes
	
	public:
	    string brand; // accessible from anywhere
	
	    void setSpeed(int s) {
	        speed = s;  // private member accessed via public method
	    }
	
	    int getSpeed() {
	        return speed;
	    }
};
```

**Usage:**
```cpp
int main() {
    Car myCar;
    myCar.brand = "BMW";     // ✅ allowed (public)
    // myCar.speed = 100;    ❌ error (private)
    myCar.setSpeed(100);     // ✅ allowed (through public method)
    cout << myCar.getSpeed(); // ✅ 100
}
```

---

# Summary Table:

| Modifier    | Same Class | Subclass | Outside Class |
| ----------- | ---------- | -------- | ------------- |
| `public`    | ✅          | ✅        | ✅             |
| `protected` | ✅          | ✅        | ❌             |
| `private`   | ✅          | ❌        | ❌             |
