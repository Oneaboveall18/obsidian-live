---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/05-normalization/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

# Introduction

**Normalization** is a systematic approach to organize data within a database to reduce redundancy and eliminate undesirable characteristics such as insertion, update, and deletion anomalies. The process involves breaking down large tables into smaller, well-structured ones and defining relationships between them. This not only reduces the chances of storing duplicate data but also improves the overall efficiency of the database.
![[bcnf.webp\|bcnf.webp]]

# Why is Normalization Important?

- **Reduces Data Redundancy**: Duplicate data is stored efficiently, saving disk space and reducing inconsistency.
- **Improves Data Integrity**: Ensures the accuracy and consistency of data by organizing it in a structured manner.
- **Simplifies Database Design**: By following a clear structure, database designs become easier to maintain and update.
- **Optimizes Performance**: Reduces the chance of anomalies and increases the efficiency of database operations.

# Normal Forms in DBMS

## 1. **First Normal Form (1NF)**: Eliminating Duplicate Records

A table is in **1NF** if it satisfies the following conditions:

- All columns contain atomic values (i.e., indivisible values).
- Each row is unique (i.e., no duplicate rows).
- Each column has a unique name.
- The order in which data is stored does not matter.

**Example of 1NF Violation:** If a table has a column "Phone Numbers" that stores multiple phone numbers in a single cell, it violates 1NF. To bring it into 1NF, you need to separate phone numbers into individual rows.

## 2. **Second Normal Form (2NF)**: Eliminating Partial Dependency

A relation is in **2NF** if it satisfies the conditions of 1NF and additionally. No partial dependency exists, meaning every non-prime attribute (non-key attribute) must depend on the entire primary key, not just a part of it.

**Example:** For a composite key ***(StudentID, CourseID)***, if the ***StudentName*** depends only on ***StudentID*** and not on the entire key, it violates 2NF. To normalize, move ***StudentName*** into a separate table where it depends only on ***StudentID***.

## 3. **Third Normal Form (3NF)**: Eliminating Transitive Dependency

A relation is in **3NF** if it satisfies 2NF and additionally, there are no transitive dependencies. In simpler terms, non-prime attributes should not depend on other non-prime attributes.

**Example:** Consider a table with ***(StudentID, CourseID, Instructor)***. If ***Instructor*** depends on ***CourseID***, and ***CourseID*** depends on ***StudentID***, then ***Instructor*** indirectly depends on ***StudentID***, which violates 3NF. To resolve this, place ***Instructor*** in a separate table linked by ***CourseID***.

## 4. **Boyce-Codd Normal Form (BCNF)**: The Strongest Form of 3NF

BCNF is a stricter version of 3NF where for every non-trivial functional dependency (X → Y), X must be a superkey (a unique identifier for a record in the table).

**Example:** If a table has a dependency ***(StudentID, CourseID)*** → Instructor, but neither StudentID nor CourseID is a superkey, then it violates BCNF. To bring it into BCNF, decompose the table so that each determinant is a candidate key.

## 5. **Fourth Normal Form (4NF)**: Removing Multi-Valued Dependencies

A table is in **4NF** if it is in BCNF and has no multi-valued dependencies. A multi-valued dependency occurs when one attribute determines another, and both attributes are independent of all other attributes in the table.

**Example:** Consider a table where ***(StudentID, Language, Hobby)*** are attributes. If a student can have multiple hobbies and languages, a ***multi-valued dependency*** exists. To resolve this, split the table into separate tables for ***Languages*** and ***Hobbies***.

## 6. **Fifth Normal Form (5NF)**: Eliminating Join Dependency

**5NF** is achieved when a table is in **4NF** and all join dependencies are removed. This form ensures that every table is fully decomposed into smaller tables that are logically connected without losing information.

**Example:** If a table contains (StudentID, Course, Instructor) and there is a dependency where all combinations of these columns are needed for a specific relationship, you would split them into smaller tables to remove redundancy.