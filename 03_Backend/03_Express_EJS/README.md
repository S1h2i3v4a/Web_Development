# 🚀 Express.js & EJS Templating Notes

Comprehensive handwritten notes, illustrated architecture cheat sheets, and quick-reference guides covering **Express.js web servers**, routing, path parameters, query strings, and dynamic HTML rendering with **EJS (Embedded JavaScript)** (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **Express & EJS Handwritten Notes (English)** | English | PDF (6 Pages) | [`Express_EJS_Handwritten_Notes_English.pdf`](./Express_EJS_Handwritten_Notes_English.pdf) |
| **Express & EJS Handwritten Notes (Hinglish)** | Hinglish | PDF (6 Pages) | [`Express_EJS_Handwritten_Notes_Hinglish.pdf`](./Express_EJS_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`Express_EJS_Notes_English.html`](./Express_EJS_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`Express_EJS_Notes_Hinglish.html`](./Express_EJS_Notes_Hinglish.html) |

---

## 📚 Topics & Key Concepts

### 1. What is Express.js?
- **Definition:** Express is a fast, unopinionated, minimalist web framework for Node.js designed for building web applications and RESTful APIs.
- **Server Lifecycle:**
  $$\text{Incoming HTTP Request} \longrightarrow \text{Express App / Middleware} \longrightarrow \text{Route Handlers} \longrightarrow \text{HTTP Response}$$
- **Basic Server Setup:**
  ```javascript
  const express = require('express');
  const app = express();
  const PORT = 3000;

  app.get('/', (req, res) => {
      res.send('Hello from Express Server!');
  });

  app.listen(PORT, () => {
      console.log(`Server listening on port ${PORT}`);
  });
  ```

---

### 2. Path Parameters & Query Strings

#### Path Parameters (`req.params`):
Used for identifying specific resources dynamically:
```javascript
app.get('/:username/:id', (req, res) => {
    const { username, id } = req.params;
    res.send(`User: ${username}, ID: ${id}`);
});
```

#### Query Strings (`req.query`):
Used for optional searching, sorting, and filtering:
```javascript
// URL: /search?q=javascript&color=yellow
app.get('/search', (req, res) => {
    const { q, color } = req.query;
    res.send(`Search results for query: ${q}`);
});
```

---

### 3. EJS (Embedded JavaScript) Templating

EJS is a templating engine that allows embedding vanilla JavaScript code into HTML pages to render dynamic content on the server.

- **Configuration:**
  ```javascript
  const path = require('path');

  app.set('view engine', 'ejs');
  app.set('views', path.join(__dirname, 'views'));
  app.use(express.static(path.join(__dirname, 'public')));
  ```

#### EJS Tag Cheat Sheet:
| Tag | Purpose | Example |
| :--- | :--- | :--- |
| `<%= %>` | Evaluates and **escapes** HTML output | `<%= username %>` |
| `<%- %>` | Evaluates and renders **raw / unescaped** HTML output | `<%- include('partials/header') %>` |
| `<% %>` | Scriptlet tag for control flow (`if`, `for`, etc.) | `<% if (isLoggedIn) { %> ... <% } %>` |

---

### 4. HTTP Methods: GET vs POST

| Feature | GET Request | POST Request |
| :--- | :--- | :--- |
| **Purpose** | Retrieving data from the server | Submitting / creating data on the server |
| **Data Location** | URL query string (`req.query`) | Request body (`req.body`) |
| **Security** | Visible in browser URL & history | Hidden from URL, suitable for passwords & forms |
| **Data Size** | Limited by URL length constraints | High capacity (files, JSON, form bodies) |

#### Parsing Request Bodies:
```javascript
// Parse URL-encoded form submissions:
app.use(express.urlencoded({ extended: true }));

// Parse incoming JSON payloads:
app.use(express.json());
```
