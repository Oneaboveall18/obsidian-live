---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/introduction-to-computers/04-pipelines/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/intro-to-computers"],"noteIcon":""}
---

# Uniprocessing

If the system has only one processor then at most one instruction can be executed at a time.

![[Pasted image 20250629170750.png\|Pasted image 20250629170750.png]]

## Uniprocessing vs Multiprocessing

![[Pasted image 20250629171145.png\|Pasted image 20250629171145.png]]

---

# Introduction

Pipelining is an arrangement of the CPU's hardware components to raise the CPU's general performance. In a pipelined processor, procedures called 'stages’ are accomplished in parallel, and the execution of more than one line of instruction occurs.
## **Real-Life Analogy:**

Think of a **car wash**:

- Stage 1: Soaping
- Stage 2: Scrubbing
- Stage 3: Rinsing
- Stage 4: Drying

If you wait for one car to finish all stages before starting another, it’s slow. Instead, a **pipeline** starts a new car at each stage as the previous car moves forward — increasing overall speed.

---

### 🧠 **Explanation of the Formula:**

#### **Without Pipelining:**

$$
 (\text{sum of clocks for each phase of one instruction}) \times (\text{number of instructions}) \times (\text{time of one clock})  

$$

 If each phase takes **1 clock cycle**, then:

$$
\text{Time}_{\text{wp}} = (\text{no. of phases} \times \text{no. of instructions}) \times (\text{clock time})
$$

#### **With Pipelining:**

$$
(\text{No. of Phases} + \text{No. of Instructions} − 1 ) \times \text{Clock Time}
$$

If each phase takes **1 clock cycle**, then:

$$
	{ T_p = (\text{No. of Phases} + \text{Number of Instructions} - 1) \times \text{Clock Time} }

$$

#### **Speed Up:**

$$
	\text{Speedup} = \frac{\text{Time Without Pipelining}}{\text{Time With Pipelining}} = \frac{T_{\text{wp}}}{T_{\text{p}}}
$$

---

# **Hazards in Pipelining**

In **pipelining**, a **hazard** is any situation that **prevents the next instruction from executing in its designated pipeline stage**, potentially causing **delays** or **wrong results**.

## 🔥 3 Types of Pipeline Hazards:

### 1. **Data Hazard (RAW, WAR, WAW)**

Occurs when **instructions depend on the results** of previous instructions.

#### 🧠 Example:

```c
Instruction 1: A = B + C   // result stored in A
Instruction 2: D = A + 1   // needs A from previous line
```

- Instruction 2 depends on the result of Instruction 1 → causes **Read After Write (RAW)** hazard.

#### ✅ Solution:

- **Forwarding/Bypassing**: Pass result directly from one stage to the next
- **Stalling**: Delay instruction until data is ready

---

### 2. **Control Hazard (Branch Hazard)**

Happens when the pipeline **does not know the outcome of a branch** (e.g., `if`, `goto`, `while`).

#### 🧠 Example:

```c
if (A == B)
   doSomething();
```

- CPU can’t know whether to fetch the next instruction or jump.

#### ✅ Solution:

- **Branch Prediction**: Guess which way the branch goes
- **Delayed Branch**: Reorder instructions to reduce waiting
- **Stall** the pipeline until the branch is resolved

---

### 3. **Structural Hazard**

Occurs when **hardware resources are insufficient** to handle multiple instructions at once.

#### 🧠 Example:

- If both the **Fetch** and **Memory** stages need access to main memory at the same time but the CPU has only one memory module.

#### ✅ Solution:

- **Duplicate resources** (e.g., separate instruction and data memory)
- **Stall one instruction** until resource is free

## 📝 Summary Table:

|Hazard Type|Cause|Solution|
|---|---|---|
|Data Hazard|Instruction depends on result of previous|Forwarding, Stall|
|Control Hazard|Branching affects next instruction fetch|Branch Prediction, Stall|
|Structural Hazard|Resource conflict|Add hardware or stall|

---
