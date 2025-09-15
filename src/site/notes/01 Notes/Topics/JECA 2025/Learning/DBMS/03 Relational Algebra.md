---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/03-relational-algebra/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

# Introduction

**Relational Algebra** is a **procedural query language** or **formal query language** used to query relational databases. It takes **one or more relations (tables)** as input and **produces a new relation** as output.
It forms the theoretical foundation for SQL and relational database operations.
# Why Learn Relational Algebra?

- It's the **foundation of SQL**.
- Helps understand **query processing**.
- Models **data retrieval** using math-like expressions.

# **Basic Operations (Set-based)**

| Operation             | Symbol    | Description                                               | Example                                                  |
| --------------------- | --------- | --------------------------------------------------------- | -------------------------------------------------------- |
| **Selection**         | σ (sigma) | Selects rows (tuples) based on condition                  | `σ Age > 18 (Student)`                                   |
| **Projection**        | π (pi)    | Selects specific columns (attributes)                     | `π Name, Age (Student)`                                  |
| **Union**             | ∪         | Combines rows from two relations (removes duplicates)     | `Student ∪ Teacher`                                      |
| **Set Difference**    | –         | Rows in one relation but not in another                   | `Student – Alumni`                                       |
| **Cartesian Product** | ×         | Pairs every row of one relation with every row of another | `Student × Course`                                       |
| **Rename**            | ρ         | Renames the relation or its attributes                    | `ρ Temp(Student)` or `ρ (NewName(Name, Marks))(Student)` |

# **Derived Operations (Can be built using basic ops)**

|Operation|Symbol|Description|
|---|---|---|
|**Intersection**|∩|Rows common in both relations|
|**Join**|⨝|Combines related tuples from two relations based on a condition|
|**Natural Join**|⨝|Auto-joins based on common attributes|
|**Theta Join**|⨝condition|Join with a condition like `A.id = B.id`|
|**Division**|÷|Returns tuples in one relation that are associated with _all_ tuples in another|

# **Examples**

## 1. **Selection** (σ):

Get all students aged over 18
$$
σ_{Age > 18}(Student)
$$
## 2. **Projection** (π):

List only names of students
$$
π_{Name}(Student)
$$
## 3. **Cartesian Product** (×):

All combinations of Students and Courses
$$
Student × Course
$$
## 4. **Join** (⨝):

Get students with their enrolled course names
$$
Student ⨝_{Student.CourseID = Course.ID} Course
$$
## 5. **Division** (÷):

Find students who have taken **all courses**
$$
StudentCourse ÷ Course
$$
# Important Notes:

- All operations **return new relations** (tables).
- Union, difference, and intersection require **compatible relations**:
    - Same number of columns
    - Same data types
