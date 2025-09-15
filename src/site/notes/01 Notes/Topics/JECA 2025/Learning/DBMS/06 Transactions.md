---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/06-transactions/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

A **transaction** in DBMS refers to a sequence of operations performed as a single unit of work. These operations may involve reading or writing data to the database. To maintain data integrity, DBMS ensures that each transaction adheres to the ACID properties. Think of a transaction like an ATM withdrawal. When we withdraw money from our account, the transaction involves several steps:

- Checking your balance.
- Deducting the money from your account.
- Adding the money to the bank's record.

For the transaction to be successful, all steps must be completed. If any part of this process fails (e.g., if there’s a system crash), the entire transaction should fail, and no data should be altered. This ensures the database remains in a **consistent** state.

# **The Four ACID Properties**

![[ACID-Properties.jpg\|ACID-Properties.jpg]]

## **1. Atomicity: "All or Nothing"**

**Atomicity** ensures that a transaction is atomic, it means that either the entire transaction completes fully or doesn't execute at all. There is no in-between state i.e. transactions do not occur partially. If a transaction has multiple operations, and one of them fails, the whole transaction is rolled back, leaving the database unchanged. This avoids partial updates that can lead to inconsistency.

- **Commit**: If the transaction is successful, the changes are permanently applied.
- **Abort/Rollback**: If the transaction fails, any changes made during the transaction are discarded.

## **2. Consistency: Maintaining Valid Data States**

Consistency ensures that a database remains in a valid state before and after a transaction. It guarantees that any transaction will take the database from one consistent state to another, maintaining the rules and constraints defined for the data. In simple terms, a transaction should only take the database from one valid state to another. If a transaction violates any database rules or constraints, it should be rejected, ensuring that only consistent data exists after the transaction.

## **3. Isolation: Ensuring Concurrent Transactions Don't Interfere**

This property ensures that ***multiple transactions*** can occur concurrently without leading to the ***inconsistency*** of the database state. Transactions occur independently without interference. Changes occurring in a particular transaction will not be visible to any other transaction until that particular change in that transaction is written to memory or has been committed.
This property ensures that when multiple transactions run at the same time, the result will be the same as if they were run one after another in a specific order. This property prevents issues such as ***dirty reads*** (reading uncommitted data), ***non-repeatable reads*** (data changing between two reads in a transaction), and ***phantom reads*** (new rows appearing in a result set after the transaction starts).

## **4. Durability: Persisting Changes**

This property ensures that once the transaction has completed execution, the updates and modifications to the database are stored in and written to disk and they persist even if a system failure occurs. These updates now become permanent and are stored in ***non-volatile memory***. In the event of a failure, the DBMS can recover the database to the state it was in after the last committed transaction, ensuring that no data is lost.

| Property        | What It Ensures           | In Bank Example                               |
| --------------- | ------------------------- | --------------------------------------------- |
| **Atomicity**   | No partial transfer       | Money deducted but not received = rolled back |
| **Consistency** | Valid state maintained    | Total balance remains consistent              |
| **Isolation**   | Transactions are separate | No interference between users                 |
| **Durability**  | Once done = permanent     | Server crash after success = still saved      |

# Transaction States

A **transaction** passes through several **states** during its execution to ensure that it behaves according to **ACID properties**.
## **List of Transaction States:**

### 1. **Active State**

- The transaction has **started executing**.
- It is performing operations like `READ`, `WRITE`, or `UPDATE`.

📌 **Example**:  
You're transferring money:  
`UPDATE AccountA SET balance = balance - 1000;`  
— this step happens in the active state.

### 2. **Partially Committed State**

- All operations are done.
- The transaction is ready to **commit** but not yet made permanent.

📌 **Example**:  
Both debit and credit operations are completed, but the system hasn’t saved them permanently.

### 3. **Committed State**

- All changes made by the transaction are **permanently saved** in the database.
- If the system crashes now, changes will **not be lost**.

📌 **Example**:  
You get a “Transaction Successful” message after transferring money. The database now reflects the final balances.

### 4. **Failed State**

- Something went **wrong during execution**, like:
    - Power failure
    - Integrity constraint violation
    - Disk crash

📌 Result: The transaction **cannot proceed** and enters a failed state.

### 5. **Aborted State**

- After failure, the system **rolls back** all the changes.
- The database is restored to the **original state** before the transaction started.
- Optionally, the system may restart the transaction.

📌 **Example**:  
Server crashes mid-transfer. DB rolls back, so no money is debited.

## **Transaction State Diagram**

```
       +----------+
       |  Active  |
       +----------+
            |
            v
+----------------------+
| Partially Committed |
+----------------------+
     |         |
     v         v
+---------+  +--------+
|Committed|  | Failed |
+---------+  +--------+
                 |
                 v
             +--------+
             |Aborted |
             +--------+
```

## Summary Table

|State|Description|
|---|---|
|**Active**|Transaction is executing|
|**Partially Committed**|Execution done, waiting to save|
|**Committed**|Changes saved permanently|
|**Failed**|Error occurred, can't proceed|
|**Aborted**|Rolled back to original state|

---

# **Concurrency Control**

## **Why is it needed?**

To manage **multiple transactions** running **simultaneously**, ensuring:

- **Data consistency**
- **No anomalies**
- **ACID properties (especially Isolation)**

## **1. Problems Without Concurrency Control**

| Problem               | Meaning                                                   |
| --------------------- | --------------------------------------------------------- |
| **Dirty Read**        | One transaction reads uncommitted data of another         |
| **Lost Update**       | One update overwrites another                             |
| **Unrepeatable Read** | Same query gives different results within one transaction |
| **Phantom Read**      | New rows appear when the same query is run again          |

## **2. Lock-Based Protocols**

### **Types of Locks**

| Lock Type              | Meaning                        |
| ---------------------- | ------------------------------ |
| **Shared Lock (S)**    | For reading (multiple allowed) |
| **Exclusive Lock (X)** | For writing (only one allowed) |

### **Two-Phase Locking (2PL)**

Ensures **conflict-serializability**  
**Phases**:
- **Growing phase**: Only acquiring locks
- **Shrinking phase**: Only releasing locks

**Rule**: Once a lock is released, **no new locks can be acquired**

## **3. Scheduling**
### **Serial Schedule**

- Transactions run **one after another**
- Always safe, but **slow**

### **Concurrent Schedule**

- Interleaved execution
- Faster, but **must be serializable**

### **Conflict Serializable Schedule**

- A schedule that is **equivalent** to a serial schedule using **precedence graph**
- If there is **no cycle**, it is **conflict serializable**

## **4. Deadlock and Starvation**

### **Deadlock**

- Two or more transactions **wait forever** for each other’s resources
- **Prevention Techniques**:
    - **Wait-Die**: Older waits, younger dies
    - **Wound-Wait**: Older wounds (forces rollback), younger waits

### **Starvation**

- A transaction **waits forever** due to unfair scheduling
