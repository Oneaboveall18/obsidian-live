---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/07-indexing/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

# **What is an Index?**

An **index** in SQL is like a **table of contents** in a book — it helps the database **find rows faster** without scanning the entire table. It **improves the speed of SELECT queries** by quickly locating data.
## **Why Use Indexing?**

- Speeds up **data retrieval**
- Especially useful for **large tables**
- Reduces **disk I/O operations**

## **Syntax**:

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

### Example:

```sql
CREATE INDEX idx_student_name
ON Students (Name);
```

This creates an index on the `Name` column of the `Students` table.


## **Types of Indexes**:

| Type                    | Description                                            |
| ----------------------- | ------------------------------------------------------ |
| **Single-Column Index** | Index on one column                                    |
| **Composite Index**     | Index on multiple columns                              |
| **Unique Index**        | Prevents duplicate values                              |
| **Primary Index**       | Automatically created on primary key                   |
| **Clustered Index**     | Sorts actual table data (usually only one per table)   |
| **Non-clustered Index** | Stores a separate structure with pointers to data rows |

## **How Index Works (Conceptual)**

- Imagine a book: instead of flipping every page to find "Chapter 5", you look at the **index** and jump directly to the page.
- In a database, instead of scanning every row, SQL uses the index to go **directly to the matching row**.

## **When Not to Use Indexes**

- On **small tables** (no noticeable speed gain)
- On columns that are **frequently updated**
- On columns with **very few unique values** (like `Gender`)

## **Dropping an Index**:

```sql
DROP INDEX index_name;
```

## Summary for Exam:

| Point        | Summary                                                           |
| ------------ | ----------------------------------------------------------------- |
| Purpose      | Speed up **searching** and **retrieval**                          |
| Works on     | `SELECT`, `WHERE`, `JOIN`, `ORDER BY`                             |
| Auto-created | On **PRIMARY KEY** and **UNIQUE** columns                         |
| Can slow     | **INSERT**, **UPDATE**, **DELETE** (extra work to maintain index) |
| Not useful   | On small tables or low-uniqueness columns                         |
