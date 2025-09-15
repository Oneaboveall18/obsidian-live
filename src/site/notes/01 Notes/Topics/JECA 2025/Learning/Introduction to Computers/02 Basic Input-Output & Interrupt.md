---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/introduction-to-computers/02-basic-input-output-and-interrupt/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/intro-to-computers"],"noteIcon":""}
---

![[Pasted image 20250627184819.png\|Pasted image 20250627184819.png]]

**Basic Input/Output (I/O)** in computer architecture refers to the mechanisms and structures that enable communication between the computer’s central components (CPU and memory) and external devices (peripherals) such as keyboards, monitors, printers, and storage devices.

# **The Role of I/O in Computer Architecture**

- **I/O Organization** is essential for data exchange between the CPU/memory and external peripherals. The I/O subsystem acts as a bridge, managing data flow and synchronization so that signals between the CPU and devices are correctly interpreted and processed
- **Peripheral Devices** are hardware components (input, output, or both) that communicate with the CPU and memory. Examples include keyboards (input), monitors (output), and touchscreens (input/output)

# Interface

![[Pasted image 20250627185302.png\|Pasted image 20250627185302.png]]

**I/O Interface Units** are special hardware components that connect the CPU to peripherals. They handle differences in signal types, data rates, and data formats between the CPU (which is electronic and fast) and peripherals (which may be electromechanical and slower).

## **Functions of I/O Interfaces:**
- Signal conversion (e.g., serial to parallel)        
- Synchronization (managing speed differences)
- Handshaking (using signals like BUSY, READY, WAIT)
- Address decoding (identifying which device to communicate with)

---

## **Why an Interpreter is Used in I/O Systems**

1. **Speed Mismatch**: CPU is much faster than input/output devices. An interpreter helps manage the timing difference.
2. **Data Format Difference**: CPU and devices use different data formats (e.g., CPU uses binary, printer might use ASCII or Unicode). Interpreter converts between them.
3. **Different Device Design**: Devices are built differently (keyboard, mouse, printer). Interpreter helps make them work together.
4. **Signal Conversion**: Devices use different electrical signals. Interpreter translates them so the CPU can understand.

---

# Interrupt

An **interrupt** is a signal sent to the CPU that **temporarily stops** its current task to handle something urgent.

## Why Use Interrupts?

To handle **important or time-sensitive events**, like    
- A key press on the keyboard
- A mouse click
- A printer being ready
- A network packet arriving

This is more efficient than constantly checking (polling) for every device.

## Types of Interrupts

### 1. **Polled Interrupt**

- The CPU **checks each device one by one** to see who raised the interrupt.
- Slower, as CPU wastes time checking every device.

🧠 Analogy: Like asking each friend in a group, “Did you call me?” one by one.

#### ✅ Pros:
- Simple to implement
#### ❌ Cons:
- Slow when many devices are connected

### 2. **Vectored Interrupt**

- The device **directly tells the CPU** where to find the **Interrupt Service Routine (ISR)** — the code to handle the interrupt.
- CPU jumps straight to the correct service code.

🧠 Analogy: A friend calls you and also tells you exactly why — so you go directly to solve the problem.

#### ✅ Pros:
- Fast and efficient
- No need to search who interrupted

#### ❌ Cons:
- Slightly more complex to implement

---

## Steps of handling interrupt

1. Interrupt Recognition:
2. Status Saving:
3. Interrupt Masking:
4. Interrupt Acknowledgement:
5. Interrupt Service Routine:
6. Restoration and Return:
### 1. 🧠 **Interrupt Recognition**

- The CPU detects that an interrupt signal has been received from a device (like a keyboard, disk, etc.).
- It **pauses the current execution**.

🧩 Example: CPU is doing a calculation, but a mouse click happens. CPU recognizes this event.

### 2. 💾 **Status Saving**

- The CPU saves the **current state** of the program (like register values, program counter, etc.)    
- This ensures that it can **resume exactly where it left off** after handling the interrupt.

🧠 Think of it like putting a bookmark in a book before handling something urgent.

### 3. 🚫 **Interrupt Masking**

- The CPU **disables other interrupts** (temporarily) to avoid being disturbed while it's handling the current one.    
- This avoids confusion or interrupt conflicts.

💡 In some systems, higher-priority interrupts may still be allowed.

### 4. ✅ **Interrupt Acknowledgement**

- The CPU **sends a signal back** to the device to confirm:
    > "Yes, I received your interrupt. I'm handling it now."

🖥️ This ensures the device doesn't keep sending the same interrupt repeatedly.

### 5. 🔧 **Interrupt Service Routine (ISR)**

- The CPU **executes a specific function** or routine (called ISR) to deal with the interrupt.
- Each device has its own ISR.

🧠 For example: Keyboard ISR may read the pressed key and store it in memory.

### 6. 🔙 **Restoration and Return**

- After finishing the ISR, the CPU **restores the saved state** (from step 2).
- It **resumes normal execution** of the program as if nothing happened.

🧩 Like closing the emergency tab and going back to your bookmarked page.

---

# **Isolated I/O (also called Port-Mapped I/O) – In Short**

**Isolated I/O** is a method where **input/output devices** are assigned **separate address space** from main memory.

## 🧠 Key Points:

- **I/O devices have their own unique addresses**, called **I/O ports** (like port 0x20, 0x21, etc.).
- CPU uses special instructions like `IN` and `OUT` to communicate with I/O devices.
- **Memory and I/O are accessed separately** — the same address (e.g., 0x1000) in memory and I/O refers to different things.
- Prevents confusion between memory and I/O operations.

### ✅ Advantages:

- Easy to manage I/O devices separately from RAM.
- Reduces risk of data conflict with memory.

### ❌ Disadvantages:

- Needs special CPU instructions (not usable in regular programs).
- Slightly slower than memory-mapped I/O for some cases.

---

# **I/O Processor**

![[Pasted image 20250627191854.png\|Pasted image 20250627191854.png]]

An **I/O Processor** is a **specialized processor** dedicated to handling **input/output operations**, relieving the **main CPU** from managing these slower tasks. Memory communicate with both the CPU and IOP through a memory bus.

---

# **Synchronous vs Asynchronous Data Transfer**

## **Synchronous Data Transfer**

In **synchronous transfer**, both the **sender and receiver share a common clock** signal. Data is transferred at fixed time intervals based on this clock.

### How it works:

- Sender and receiver are **synchronized**.
- Data is sent in regular intervals (clock pulses).
- Receiver knows **when to expect data**.

### Characteristics:

- Fast and efficient
- Requires **clock signal** or timing agreement
- Used in **memory-to-CPU** transfers

## **Asynchronous Data Transfer**

### Definition:

In **asynchronous transfer**, the sender and receiver **do not share a clock**. Instead, they use **control signals** (like start/stop bits or handshaking) to coordinate.

### How it works:

- Sender sends a **start signal** with data.
- Receiver waits for data, then sends an **acknowledgment**.
- Timing is **not fixed** — depends on when each device is ready.

### Characteristics:

- Slower than synchronous
- No need for a shared clock
- More **flexible** — used with **I/O devices** like keyboards, printers

---

# Programmed I/O

![[Data-Transfer-IO-to-Processor.png\|Data-Transfer-IO-to-Processor.png]]

**Programmed I/O** is a data transfer method where the CPU is fully responsible for controlling all I/O operations. It continuously checks (or "polls") the I/O device to see if it is ready for data transfer, and once it is, the CPU performs the data transfer by reading from or writing to the device. This method keeps the CPU busy during the entire I/O process, making it simple but inefficient, especially when dealing with slow devices.

![[Pasted image 20250627193106.png\|Pasted image 20250627193106.png]]

---

# Interrupt Initiated I/O

**Interrupt-initiated I/O** is a data transfer method where the CPU does not constantly check the I/O device. Instead, the I/O device sends an **interrupt signal** to the CPU **only when it is ready** for data transfer. The CPU then pauses its current task, handles the I/O operation through an **Interrupt Service Routine (ISR)**, and resumes its previous task. This method is more efficient than programmed I/O because it allows the CPU to perform other tasks while waiting for the I/O device, reducing CPU idle time.

- Non-Vectored Interrupt: There is a mutual understanding between CPU and device that where this routine is stored in memory (high priority device)
- Vectored Interrupt: Some interrupts may be vectored where the interrupting device will also tell the address that where this routine is stored in the memory.

---

