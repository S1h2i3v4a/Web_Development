# 🌐 Express + MongoDB Integration (Complete RESTful CRUD)

Comprehensive handwritten notes, architecture diagrams, and full code guides for building a **production-ready RESTful CRUD application with Express.js, EJS templates, Mongoose ODM, and MongoDB**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./06_Express_MongoDB_Integration_CRUD_English.pdf) | [🌐 View HTML](./06_Express_MongoDB_Integration_CRUD_English.html) | Technical architecture, REST patterns & English notes |
| **Hinglish Edition** | [📄 Download PDF](./06_Express_MongoDB_Integration_CRUD_Hinglish.pdf) | [🌐 View HTML](./06_Express_MongoDB_Integration_CRUD_Hinglish.html) | Conversational walkthrough, step-by-step code & Hinglish notes |

---

## 💡 The 7 RESTful CRUD Routes

| Route # | HTTP Verb | Path | Action | Description |
| :---: | :--- | :--- | :--- | :--- |
| **1** | `GET` | `/products` | **Index** | Fetch all products and display list |
| **2** | `GET` | `/products/new` | **New** | Render HTML form to create a new product |
| **3** | `POST` | `/products` | **Create** | Save new product to MongoDB and redirect |
| **4** | `GET` | `/products/:id` | **Show** | Fetch product by ID and display details |
| **5** | `GET` | `/products/:id/edit` | **Edit** | Render pre-populated edit form |
| **6** | `PUT` / `PATCH` | `/products/:id` | **Update** | Update product in MongoDB via `method-override` |
| **7** | `DELETE` | `/products/:id` | **Destroy** | Remove product from MongoDB and redirect |

---

## 💻 Sample Implementation Pattern

```javascript
const express = require('express');
const app = express();
const methodOverride = require('method-override');
const Product = require('./models/product');

app.use(express.urlencoded({ extended: true }));
app.use(methodOverride('_method'));

// 1. Index Route
app.get('/products', async (req, res) => {
    const products = await Product.find({});
    res.render('products/index', { products });
});

// 2. Create Route
app.post('/products', async (req, res) => {
    const newProduct = new Product(req.body);
    await newProduct.save();
    res.redirect(`/products/${newProduct._id}`);
});

// 3. Update Route
app.put('/products/:id', async (req, res) => {
    const { id } = req.params;
    await Product.findByIdAndUpdate(id, req.body, { runValidators: true, new: true });
    res.redirect(`/products/${id}`);
});

// 4. Delete Route
app.delete('/products/:id', async (req, res) => {
    const { id } = req.params;
    await Product.findByIdAndDelete(id);
    res.redirect('/products');
});
```
