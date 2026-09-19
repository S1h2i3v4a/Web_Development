# 🐬 Node.js with MySQL Integration

Comprehensive handwritten notes, architecture diagrams, code patterns, and interactive guides for connecting **Node.js / Express applications to MySQL databases**, executing parameterized queries, preventing SQL injection, and managing connection pools (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **Node.js + MySQL Notes (English)** | English | PDF (8 Pages) | [`Node_MySQL_Handwritten_Notes_English.pdf`](./Node_MySQL_Handwritten_Notes_English.pdf) |
| **Node.js + MySQL Notes (Hinglish)** | Hinglish | PDF (8 Pages) | [`Node_MySQL_Handwritten_Notes_Hinglish.pdf`](./Node_MySQL_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`Node_MySQL_Notes_English.html`](./Node_MySQL_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`Node_MySQL_Notes_Hinglish.html`](./Node_MySQL_Notes_Hinglish.html) |

---

## 📚 Topics Covered

### 1. Connecting Node.js to MySQL
- Using the modern `mysql2` driver (`npm install mysql2`).
- Setting up database credentials with environment variables (`.env`).
- Single Connection (`mysql.createConnection`) vs Connection Pool (`mysql.createPool`).
- Why Connection Pooling? Reusing active connections, handling concurrent requests, avoiding connection exhaustion.

### 2. Executing Queries from Express
- `pool.query()` with callback and promise wrappers (`mysql2/promise`).
- Parameterized Queries with placeholder `?` to prevent **SQL Injection** attacks.
- Reading query results (`[rows, fields]`).

### 3. Full CRUD Implementation with Express & MySQL
- **Create:** `INSERT INTO users (name, email) VALUES (?, ?)`
- **Read:** `SELECT * FROM users WHERE id = ?`
- **Update:** `UPDATE users SET name = ? WHERE id = ?`
- **Delete:** `DELETE FROM users WHERE id = ?`

### 4. Database Seeding & Mock Data
- Using libraries like `@faker-js/faker` to generate thousands of realistic mock user records.
- Batch insertion syntax: `INSERT INTO users (id, name, email) VALUES ?`.

---

## 💻 Code Reference: Connection Pool & CRUD

```javascript
// db.js - MySQL Connection Pool
const mysql = require('mysql2/promise');

const pool = mysql.createPool({
    host: process.env.DB_HOST || 'localhost',
    user: process.env.DB_USER || 'root',
    password: process.env.DB_PASSWORD || 'password123',
    database: process.env.DB_NAME || 'my_app_db',
    waitForConnections: true,
    connectionLimit: 10,
    queueLimit: 0
});

module.exports = pool;
```

```javascript
// app.js - Express Route with Parameterized Query
const express = require('express');
const pool = require('./db');
const app = express();

app.use(express.json());

// GET: Fetch all users
app.get('/users', async (req, res) => {
    try {
        const [rows] = await pool.query('SELECT id, name, email FROM users ORDER BY created_at DESC');
        res.json(rows);
    } catch (err) {
        res.status(500).json({ error: err.message });
    }
});

// POST: Create new user with parameterized query (Safe from SQL Injection)
app.post('/users', async (req, res) => {
    const { name, email } = req.body;
    try {
        const query = 'INSERT INTO users (name, email) VALUES (?, ?)';
        const [result] = await pool.query(query, [name, email]);
        res.status(201).json({ id: result.insertId, name, email });
    } catch (err) {
        res.status(500).json({ error: err.message });
    }
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

## 🚀 Quick Links

- [Open Node + MySQL (English) PDF](./Node_MySQL_Handwritten_Notes_English.pdf)
- [Open Node + MySQL (Hinglish) PDF](./Node_MySQL_Handwritten_Notes_Hinglish.pdf)
- [Open Printable English HTML](./Node_MySQL_Notes_English.html)
- [Open Printable Hinglish HTML](./Node_MySQL_Notes_Hinglish.html)
