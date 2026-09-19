# 🔄 Async Error Handling & the wrapAsync Pattern

Comprehensive handwritten notes, comparison diagrams, and code patterns covering **asynchronous error propagation, unhandled promise rejections, the wrapAsync higher-order function, and Mongoose error handling**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./08_Async_Errors_wrapAsync_Pattern_English.pdf) | [🌐 View HTML](./08_Async_Errors_wrapAsync_Pattern_English.html) | Technical async handling, wrapper patterns & English notes |
| **Hinglish Edition** | [📄 Download PDF](./08_Async_Errors_wrapAsync_Pattern_Hinglish.pdf) | [🌐 View HTML](./08_Async_Errors_wrapAsync_Pattern_Hinglish.html) | Conversational explanations, real-world examples & Hinglish notes |

---

## 💡 Key Architectural Patterns

### 1. The Problem with Async Errors in Express
Synchronous errors in Express are caught automatically. However, **asynchronous errors** (e.g. database rejections) will crash the process or hang the request unless explicitly passed to `next(err)`:

```javascript
// Risky: If Book.findById fails, app hangs or crashes!
app.get('/books/:id', async (req, res, next) => {
    const book = await Book.findById(req.params.id);
    res.render('books/show', { book });
});
```

### 2. The `wrapAsync` (or `catchAsync`) Pattern
Instead of wrapping every route handler with tedious `try...catch` blocks, use a higher-order utility function:

```javascript
// utils/wrapAsync.js
module.exports = function wrapAsync(fn) {
    return function (req, res, next) {
        fn(req, res, next).catch(err => next(err));
    };
};
```

### 3. Clean Route Handlers with `wrapAsync`
```javascript
const wrapAsync = require('./utils/wrapAsync');

app.get('/books/:id', wrapAsync(async (req, res, next) => {
    const book = await Book.findById(req.params.id);
    if (!book) {
        throw new ExpressError('Book Not Found', 404);
    }
    res.render('books/show', { book });
}));
```

### 4. Handling Mongoose-Specific Errors
- **`CastError`:** Triggered when an invalid MongoDB `ObjectId` is passed (e.g., `id = "123"`).
- **`ValidationError`:** Triggered when schema rules (such as `required`, `min`, `max`) fail.
- **`MongoServerError` (Code 11000):** Duplicate key error on unique indexes.
