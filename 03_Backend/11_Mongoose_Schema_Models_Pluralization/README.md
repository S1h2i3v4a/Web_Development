# 📐 Mongoose Schemas, Models & Collection Pluralization

Comprehensive handwritten notes, SchemaType tables, and code guides covering **Mongoose Schema definitions, model compilation, data types, and collection naming conventions**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./04_Mongoose_Schema_Models_Pluralization_English.pdf) | [🌐 View HTML](./04_Mongoose_Schema_Models_Pluralization_English.html) | Technical schema architecture, models & English notes |
| **Hinglish Edition** | [📄 Download PDF](./04_Mongoose_Schema_Models_Pluralization_Hinglish.pdf) | [🌐 View HTML](./04_Mongoose_Schema_Models_Pluralization_Hinglish.html) | Conversational explanations, real-world examples & Hinglish notes |

---

## 💡 Key Concepts & Code

### 1. Schema vs Model
- **Schema:** Blueprint defining document structure, data types, default values, and validations.
- **Model:** A compiled constructor class derived from the Schema, used to instantiate documents and perform CRUD operations.

### 2. Defining a Schema & Supported SchemaTypes
```javascript
const mongoose = require('mongoose');

const bookSchema = new mongoose.Schema({
    title: { type: String, required: true },
    author: String,
    pages: Number,
    price: Number,
    publishedDate: { type: Date, default: Date.now },
    isAvailable: { type: Boolean, default: true },
    tags: [String] // Array of strings
});
```

### 3. Compiling Model & Automatic Pluralization
When compiling a model, Mongoose takes the singular model name, converts it to **all lowercase**, and applies English **pluralization**:

```javascript
// Model name: 'Book' -> Collection name in MongoDB: 'books'
const Book = mongoose.model('Book', bookSchema);

// Model name: 'Person' -> Collection name: 'people'
// Model name: 'Category' -> Collection name: 'categories'
```

### 4. Creating & Saving Document Instances
```javascript
// Method 1: new instance + .save()
const novel = new Book({
    title: "Atomic Habits",
    author: "James Clear",
    pages: 320,
    price: 499
});

novel.save()
    .then((data) => console.log('Book Saved:', data))
    .catch((err) => console.error('Save Error:', err));

// Method 2: Model.insertMany()
Book.insertMany([
    { title: "Deep Work", author: "Cal Newport", pages: 304, price: 399 },
    { title: "Clean Code", author: "Robert C. Martin", pages: 464, price: 699 }
]);
```
