---
{"dg-publish":true,"permalink":"/01-notes/topics/jeca-2025/learning/dbms/02-er-diagram/","tags":["#topic/jeca","#type/notes","#notes/topic/jeca/dbms"],"noteIcon":""}
---

# Introduction

An **ER diagram** is a visual representation of data and their relationships in a database system. It helps in designing the logical structure of a database before implementation.
# Components of ER Diagram:

1. **Entity**:
	- Real-world object or concept.
	- Represented by a **rectangle**.
	- Two types:
	    - **Strong Entity** – Exists independently.
		- **Weak Entity** – Cannot exist without another entity (uses a **double rectangle**).
	Example: `Student`, `Course`

2. **Attributes**:
    - Properties of an entity.
    - Represented by **ellipses (ovals)**.
    - Types:
        - **Simple**: Cannot be divided (e.g., Name).
        - **Composite**: Can be divided (e.g., Full Name → First Name, Last Name).
        - **Derived**: Calculated from other attributes (e.g., Age from DOB).
        - **Multivalued**: Can have multiple values (e.g., Phone Numbers) → **double oval**.
        - **Key Attribute**: Uniquely identifies the entity → **underlined**.

3. **Relationship**:
    - Shows how two entities are related.
    - Represented by a **diamond shape**.
    - Can have their own attributes (called **relationship attributes**).
    Example: `Enrolled` between `Student` and `Course`

4. **Cardinality (Mapping Constraints)**:    
    - Specifies the number of entity instances in a relationship.
    - Types:
        - **One to One (1:1)**
        - **One to Many (1:N)**
        - **Many to One (N:1)**
        - **Many to Many (M:N)**

5. **Participation Constraints**:
    - **Total Participation**: Entity must participate (represented by **double line**).
    - **Partial Participation**: Entity may or may not participate (**single line**).

# Example ER Diagram: Student & Course

```text
   +-----------+         +-----------+
   |  Student  |         |  Course   |
   +-----------+         +-----------+
        |                    |
        |                    |
        +------Enrolled------+
               (many-to-many)
```

# Entities:

- **Student** with attributes: Student_ID (PK), Name, Email
- **Course** with attributes: Course_ID (PK), Title

# Relationship:

- **Enrolled** with attribute: Date_of_Enrollment

# Converting ER to Table (Relational Model):

- Entities become **tables**.
- Attributes become **columns**.
- Relationships may become:
    - Foreign keys (for 1:1 and 1:N)
    - Separate tables (for M:N with keys from both entities)

# Importance of ER Diagram:

- Helps database designers plan structure clearly.
- Identifies relationships before actual implementation.
- Reduces data redundancy and improves consistency.