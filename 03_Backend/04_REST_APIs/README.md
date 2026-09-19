# 🌐 RESTful APIs & CRUD Architecture Notes

Comprehensive handwritten notes, route architecture cheat sheets, and quick-reference guides covering **RESTful API design**, standard CRUD route conventions, HTTP verbs (`GET`, `POST`, `PATCH`, `DELETE`), and resource management in Express.js (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **REST API Handwritten Notes (English)** | English | PDF (8 Pages) | [`REST_API_Handwritten_Notes_English.pdf`](./REST_API_Handwritten_Notes_English.pdf) |
| **REST API Handwritten Notes (Hinglish)** | Hinglish | PDF (8 Pages) | [`REST_API_Handwritten_Notes_Hinglish.pdf`](./REST_API_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`REST_API_Notes_English.html`](./REST_API_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`REST_API_Notes_Hinglish.html`](./REST_API_Notes_Hinglish.html) |

---

## 📚 Topics & Key Concepts

### 1. What is a RESTful API?
- **Definition:** REST (*Representational State Transfer*) is an architectural style for designing networked applications and web APIs based on standard HTTP protocols.
- **Core Principles:**
  - **Client-Server Separation:** Client handles UI/presentation; server handles logic and storage.
  - **Stateless:** Each request from the client contains all necessary information to be understood and fulfilled.
  - **Resource-Based URLs:** Endpoints represent *nouns/resources* (e.g. `/posts`), while HTTP methods represent *actions* (`GET`, `POST`, `PATCH`, `DELETE`).

---

### 2. The 7 Standard RESTful CRUD Routes

| Operation | HTTP Method | Route Endpoint | Purpose / Action |
| :--- | :--- | :--- | :--- |
| **Index** | `GET` | `/posts` | List and display all posts |
| **New** | `GET` | `/posts/new` | Render form to create a new post |
| **Create** | `POST` | `/posts` | Save new post to server/database |
| **Show** | `GET` | `/posts/:id` | Display full details of a specific post |
| **Edit** | `GET` | `/posts/:id/edit` | Render pre-filled form to edit post |
| **Update** | `PATCH` / `PUT` | `/posts/:id` | Update specific post details |
| **Destroy** | `DELETE` | `/posts/:id` | Delete post permanently |

---

### 3. Method Override for HTML Forms
Standard HTML forms natively only support `GET` and `POST`. To perform `PATCH`, `PUT`, and `DELETE` requests from forms:

```javascript
const methodOverride = require('method-override');
app.use(methodOverride('_method'));
```

```html
<!-- Form submitting a PATCH request -->
<form method="POST" action="/posts/<%= post.id %>?_method=PATCH">
  <textarea name="content"><%= post.content %></textarea>
  <button type="submit">Update</button>
</form>

<!-- Form submitting a DELETE request -->
<form method="POST" action="/posts/<%= post.id %>?_method=DELETE">
  <button type="submit">Delete</button>
</form>
```

---

### 4. HTTP Status Codes Cheat Sheet
- **`200 OK`**: Successful request.
- **`201 Created`**: Resource successfully created.
- **`204 No Content`**: Action succeeded, no content returned.
- **`400 Bad Request`**: Malformed request or client error.
- **`404 Not Found`**: Target resource does not exist.
- **`500 Internal Server Error`**: Unexpected server-side failure.
