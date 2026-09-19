# 🛡️ Form Validation & Error Handling Notes

Comprehensive handwritten notes, validation flowcharts, and quick-reference cheat sheets covering **client-side & server-side form validation**, custom error handling middleware, and async error management in Express.js (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **Form Validation & Errors Handwritten Notes (English)** | English | PDF (8 Pages) | [`Form_Validation_Errors_Handwritten_Notes_English.pdf`](./Form_Validation_Errors_Handwritten_Notes_English.pdf) |
| **Form Validation & Errors Handwritten Notes (Hinglish)** | Hinglish | PDF (8 Pages) | [`Form_Validation_Errors_Handwritten_Notes_Hinglish.pdf`](./Form_Validation_Errors_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`Form_Validation_Notes_English.html`](./Form_Validation_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`Form_Validation_Notes_Hinglish.html`](./Form_Validation_Notes_Hinglish.html) |

---

## 📚 Topics & Key Concepts

### 1. Client-Side vs Server-Side Validation

```
[ User Input ]
       │
       ▼
[ Client-Side Validation ] ────(Fail)───► Instant UI Error (No server hit)
       │ (Pass)
       ▼
   HTTP Request
       │
       ▼
[ Server-Side Validation ] ────(Fail)───► Returns 400 Bad Request
       │ (Pass)
       ▼
[ Database Storage ]
```

- **Client-Side:** Immediate feedback using HTML5 attributes (`required`, `minlength`, `type="email"`) or Bootstrap's `.needs-validation`. *Can be bypassed (via Postman, curl, or disabling JS).*
- **Server-Side:** Essential security layer verifying data integrity before database insertion (e.g. using Joi schemas or manual validation checks).

---

### 2. Custom Error Class (`ExpressError`)

```javascript
class ExpressError extends Error {
    constructor(statusCode, message) {
        super();
        this.statusCode = statusCode;
        this.message = message;
    }
}

module.exports = ExpressError;
```

---

### 3. Async Error Handling (`wrapAsync`)

In Express, errors in asynchronous route handlers must be passed to `next(err)` to avoid unhandled promise rejections. A clean wrapper utility eliminates repetitive `try-catch` blocks:

```javascript
function wrapAsync(fn) {
    return function (req, res, next) {
        fn(req, res, next).catch(next);
    };
}

// Usage in route handler:
app.get('/posts/:id', wrapAsync(async (req, res, next) => {
    const { id } = req.params;
    const post = await Post.findById(id);
    if (!post) {
        throw new ExpressError(404, 'Post Not Found!');
    }
    res.render('posts/show', { post });
}));
```

---

### 4. Express Error-Handling Middleware

Error middleware must always declare all 4 parameters: `(err, req, res, next)`:

```javascript
// Catch-all 404 handler for undefined routes:
app.all('*', (req, res, next) => {
    next(new ExpressError(404, 'Page Not Found!'));
});

// Centralized error handler:
app.use((err, req, res, next) => {
    const { statusCode = 500, message = 'Something went wrong!' } = err;
    res.status(statusCode).render('error', { statusCode, message });
});
```
