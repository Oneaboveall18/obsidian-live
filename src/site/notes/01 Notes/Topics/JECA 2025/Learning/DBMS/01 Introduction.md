---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/01-introduction/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

# What is a Database?

A **database** is an organized collection of related data that is stored and accessed electronically. It allows easy insertion, updating, retrieval, and deletion of data.

# DBMS (Database Management System)

A **DBMS** is a software system that allows users to define, create, maintain, and control access to the database.  
Examples: MySQL, PostgreSQL, Oracle, MongoDB, SQLite.

# Advantages of DBMS:

1. **Data Redundancy Control** – Same data is not repeated unnecessarily.
2. **Data Integrity** – Accuracy and consistency of data are maintained.
3. **Data Security** – Only authorized users can access or modify data.
4. **Data Independence** – Data is independent of the application programs.
5. **Concurrency Control** – Multiple users can access data at the same time without conflict.

# DBMS Components:

1. **Hardware** – Physical devices (computers, storage).
2. **Software** – The DBMS software itself.
3. **Data** – Actual data stored.
4. **Users** – Database users (DBA, Developers, End-users).
5. **Procedures** – Instructions and rules on how to use the DBMS.

# Types of Databases:

- **Relational Database (RDBMS)** – Tables with rows and columns (e.g., MySQL, PostgreSQL).
- **NoSQL Database** – Non-relational (e.g., MongoDB, Redis).
- **Hierarchical & Network Databases** – Outdated models, used earlier.

# Architecture of DBMS:

1. **1-tier** – DBMS directly on client machine.
2. **2-tier** – Client application and database server.
3. **3-tier** – Client → Application Server → Database Server (most common).

# Data Models:

Defines how data is logically structured:

- **Hierarchical Model**
- **Network Model**
- **Relational Model (most used)**
- **Object-Oriented Model**