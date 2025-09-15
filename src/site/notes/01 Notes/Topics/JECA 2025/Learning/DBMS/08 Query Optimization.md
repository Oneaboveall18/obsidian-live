---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/08-query-optimization/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

# **Query Optimization in SQL/DBMS**

**Query Optimization** is the process of **choosing the most efficient way** to execute a database query. The goal is to **minimize resource usage** (CPU, memory, disk I/O) and **speed up query execution**.

# **Why Is It Needed?**

- Large databases may have **millions of records**.
- A query can be written in multiple ways that give the **same result** but have **different performance**.
- Optimization helps **reduce execution time**.

# **How It Works**

When a SQL query is run:

1. The **query parser** checks for syntax errors.
2. The **query optimizer** generates multiple ways (called **query plans**) to get the result.
3. It selects the **least-cost** plan based on:
    - Number of rows to process
    - Use of indexes
    - Join strategies
    - Sorting methods

# **Techniques of Query Optimization**

|Technique|Description|
|---|---|
|**Use of Indexes**|Speeds up data access|
|**Predicate Pushdown**|Apply `WHERE` conditions **early** to reduce rows|
|**Join Order Optimization**|Join smaller tables first|
|**Projection Pushdown**|Select only needed columns early (`SELECT name` instead of `SELECT *`)|
|**Avoid nested queries**|Replace with **JOINs** if possible|
|**Use of Statistics**|DBMS collects table info to estimate costs|

# **Example**

❌ Inefficient:

```sql
SELECT * FROM Students WHERE Age > 18;
```

✅ Optimized:

```sql
SELECT Name, Roll FROM Students WHERE Age > 18;
```

- Selects only needed columns → faster
- If `Age` has an index, performance improves

---

# **Query Optimizer Components**

1. **Cost-based Optimizer** – selects the plan with **lowest estimated cost**
2. **Rule-based Optimizer** – uses **predefined rules** (less common now)