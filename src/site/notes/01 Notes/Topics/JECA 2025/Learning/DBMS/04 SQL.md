---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/04-sql/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

# Introduction

**SQL** is a standard language used to **communicate with relational databases**. It is used to **create**, **modify**, **query**, and **manage** data stored in tables.
# Categories of SQL Commands:

| Type                                   | Description                     | Example                                |
| -------------------------------------- | ------------------------------- | -------------------------------------- |
| **DDL** (Data Definition Language)     | Defines structure of DB objects | `CREATE`, `ALTER`, `DROP`              |
| **DML** (Data Manipulation Language)   | Manipulates data                | `SELECT`, `INSERT`, `UPDATE`, `DELETE` |
| **DCL** (Data Control Language)        | Controls access                 | `GRANT`, `REVOKE`                      |
| **TCL** (Transaction Control Language) | Manages transactions            | `COMMIT`, `ROLLBACK`, `SAVEPOINT`      |

# 1. **DDL Commands**

## `CREATE`

```sql
CREATE TABLE Students (
  ID INT PRIMARY KEY,
  Name VARCHAR(50),
  Age INT
);
```

## `ALTER`

```sql
ALTER TABLE Students ADD Email VARCHAR(100);
```

## `DROP`

```sql
DROP TABLE Students;
```

# 2. **DML Commands**

## `INSERT`

```sql
INSERT INTO Students (ID, Name, Age) VALUES (1, 'Aditya', 21);
```

## `SELECT`

```sql
SELECT Name, Age FROM Students WHERE Age > 20;
```

## `UPDATE`

```sql
UPDATE Students SET Age = 22 WHERE ID = 1;
```

## `DELETE`

```sql
DELETE FROM Students WHERE ID = 1;
```

# 3. **DCL Commands**

## `GRANT`

```sql
GRANT SELECT ON Students TO user1;
```

## `REVOKE`

```sql
REVOKE SELECT ON Students FROM user1;
```

# 4. **TCL Commands**

## `COMMIT`

- Saves all changes permanently to the database.

## `ROLLBACK`

- Undo changes made in the current transaction.

## `SAVEPOINT`

- Set a savepoint within a transaction to roll back to later.

# 5. **Clauses in SELECT**

| Clause                  | Purpose            |
| ----------------------- | ------------------ |
| `WHERE`                 | Filter rows        |
| `ORDER BY`              | Sorts the result   |
| `GROUP BY`              | Groups rows        |
| `HAVING`                | Filter groups      |
| `DISTINCT`              | Removes duplicates |
| `IN`, `BETWEEN`, `LIKE` | Used in conditions |

## Example:

```sql
SELECT Name FROM Students
WHERE Age BETWEEN 18 AND 25
ORDER BY Age DESC;
```

# 6. **Joins** (Combining data from multiple tables)

| Type           | Description                        | Syntax Example                       |
| -------------- | ---------------------------------- | ------------------------------------ |
| **INNER JOIN** | Matches rows in both tables        | `A INNER JOIN B ON A.id = B.id`      |
| **LEFT JOIN**  | All rows from left + matched right | `A LEFT JOIN B ON A.id = B.id`       |
| **RIGHT JOIN** | All rows from right + matched left | `A RIGHT JOIN B ON A.id = B.id`      |
| **FULL JOIN**  | All rows from both sides           | `A FULL OUTER JOIN B ON A.id = B.id` |

# 7. **Aggregate Functions**

| Function  | Description     |
| --------- | --------------- |
| `COUNT()` | Number of rows  |
| `SUM()`   | Total of values |
| `AVG()`   | Average         |
| `MIN()`   | Minimum         |
| `MAX()`   | Maximum         |

```sql
SELECT COUNT(*) FROM Students WHERE Age > 20;
```

---

#  8. **Subqueries**

Query within a query.

```sql
SELECT Name FROM Students
WHERE Age > (SELECT AVG(Age) FROM Students);
```
