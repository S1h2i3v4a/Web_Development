# 🗄️ SQL & Relational Databases (RDBMS)

Comprehensive handwritten notes, query cheat sheets, architectural diagrams, and interactive web guides covering **Relational Databases, SQL (Structured Query Language), MySQL**, schema design, constraints, and complex queries (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **SQL Database Notes (English)** | English | PDF (10 Pages) | [`SQL_Database_Handwritten_Notes_English.pdf`](./SQL_Database_Handwritten_Notes_English.pdf) |
| **SQL Database Notes (Hinglish)** | Hinglish | PDF (10 Pages) | [`SQL_Database_Handwritten_Notes_Hinglish.pdf`](./SQL_Database_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`SQL_Database_Notes_English.html`](./SQL_Database_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`SQL_Database_Notes_Hinglish.html`](./SQL_Database_Notes_Hinglish.html) |

---

## 📚 Syllabus & Topics Covered

### 1. Database & RDBMS Fundamentals
- What is a Database? File storage vs Database Management Systems (DBMS).
- Relational Database Management Systems (RDBMS): Tables, Rows (Tuples), Columns (Attributes).
- Primary Keys vs Foreign Keys, Candidate Keys, Composite Keys.
- Schema Design & Normalization (1NF, 2NF, 3NF).

### 2. SQL Command Classifications
- **DDL (Data Definition Language):** `CREATE`, `ALTER`, `DROP`, `TRUNCATE`, `RENAME`.
- **DML (Data Manipulation Language):** `INSERT`, `UPDATE`, `DELETE`.
- **DQL (Data Query Language):** `SELECT`, filtering, projection.
- **DCL (Data Control Language):** `GRANT`, `REVOKE`.
- **TCL (Transaction Control Language):** `COMMIT`, `ROLLBACK`, `SAVEPOINT`.

### 3. Constraints in SQL
- `NOT NULL`: Ensures column cannot hold `NULL` values.
- `UNIQUE`: Guarantees all values in a column are distinct.
- `PRIMARY KEY`: Combines `NOT NULL` and `UNIQUE` to uniquely identify each row.
- `FOREIGN KEY`: Enforces referential integrity across related tables (`ON DELETE CASCADE`).
- `DEFAULT`: Provides a default value when none is specified.
- `CHECK`: Ensures values satisfy a boolean condition (e.g. `age >= 18`).

### 4. Querying, Filtering & Sorting
- `SELECT * FROM table_name WHERE condition;`
- Logical Operators: `AND`, `OR`, `NOT`, `BETWEEN ... AND ...`, `IN (...)`, `LIKE '%pattern%'`.
- Sorting: `ORDER BY column_name ASC|DESC`.
- Pagination: `LIMIT offset, count`.

### 5. Aggregate Functions & Grouping
- Aggregates: `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`.
- `GROUP BY`: Groups rows that share values in specified columns.
- `HAVING`: Filters grouped records (used instead of `WHERE` with aggregate functions).

### 6. SQL Joins
- `INNER JOIN`: Returns records that have matching values in both tables.
- `LEFT JOIN` (or `LEFT OUTER JOIN`): Returns all records from left table and matched records from right table.
- `RIGHT JOIN`: Returns all records from right table and matched records from left table.
- `FULL OUTER JOIN`: Returns all records when there is a match in either left or right table.

---

## 💻 Essential SQL Cheat Sheet

```sql
-- 1. Database Operations
CREATE DATABASE college_db;
USE college_db;
DROP DATABASE IF EXISTS test_db;

-- 2. Table Creation with Constraints
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    age INT CHECK (age >= 17),
    course VARCHAR(50) DEFAULT 'Computer Science',
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- 3. Inserting Data (DML)
INSERT INTO students (name, email, age, course)
VALUES ('Shivam Keshari', 'shivam@example.com', 22, 'B.Tech IT'),
       ('Rahul Sharma', 'rahul@example.com', 21, 'BCA');

-- 4. Querying & Filtering (DQL)
SELECT name, email, course FROM students
WHERE age >= 21 AND course LIKE '%IT%'
ORDER BY name ASC
LIMIT 10;

-- 5. Updating & Deleting
UPDATE students SET course = 'Full Stack Web Dev' WHERE id = 1;
DELETE FROM students WHERE id = 2;

-- 6. Joins Example
SELECT s.name, c.course_name, c.fee
FROM students s
INNER JOIN courses c ON s.course_id = c.id;
```

---

## 🚀 Quick Links

- [Open SQL Notes (English) PDF](./SQL_Database_Handwritten_Notes_English.pdf)
- [Open SQL Notes (Hinglish) PDF](./SQL_Database_Handwritten_Notes_Hinglish.pdf)
- [Open Printable English HTML](./SQL_Database_Notes_English.html)
- [Open Printable Hinglish HTML](./SQL_Database_Notes_Hinglish.html)
