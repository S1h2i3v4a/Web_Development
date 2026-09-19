# 🛡️ Express Middlewares & Error Handling

Comprehensive handwritten notes, execution flowcharts, and code guides covering **Express middleware lifecycle, custom error classes, 404 handlers, and global error middleware**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./07_Express_Middlewares_Error_Handling_English.pdf) | [🌐 View HTML](./07_Express_Middlewares_Error_Handling_English.html) | Middleware lifecycle, error architecture & English notes |
| **Hinglish Edition** | [📄 Download PDF](./07_Express_Middlewares_Error_Handling_Hinglish.pdf) | [🌐 View HTML](./07_Express_Middlewares_Error_Handling_Hinglish.html) | Conversational walkthrough, diagrams & Hinglish notes |

---

## 💡 Key Architectural Concepts

### 1. Middleware Execution Pipeline
Middleware functions have access to `req`, `res`, and the `next` function in the request-response cycle:
- Execute any code.
- Make changes to the request and the response objects.
- End the request-response cycle.
- Call `next()` to pass control to the next middleware in the stack.

### 2. Custom Error Class (`ExpressError`)
```javascript
class ExpressError extends Error {
    constructor(message, statusCode) {
        super();
        this.message = message;
        this.statusCode = statusCode;
    }
}

module.exports = ExpressError;
```

### 3. Centralized Error Handling Middleware
In Express, error-handling middleware is defined with **four parameters**: `(err, req, res, next)`:

```javascript
// 404 Route Handler (Catch-all for undefined routes)
app.all('*', (req, res, next) => {
    next(new ExpressError('Page Not Found', 404));
});

// Centralized Error-Handling Middleware
app.use((err, req, res, next) => {
    const { statusCode = 500, message = 'Something went wrong' } = err;
    res.status(statusCode).render('error', { err });
});
```
