# 📦 Nested Documents, Deletions & Mongoose Setup

Comprehensive handwritten notes, syntax cheat sheets, and integration guides covering **MongoDB nested/embedded documents, dot notation queries, document deletions, and Mongoose ODM setup**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./03_Nested_Docs_Deletions_Mongoose_Setup_English.pdf) | [🌐 View HTML](./03_Nested_Docs_Deletions_Mongoose_Setup_English.html) | Formal technical explanations, nested models & English notes |
| **Hinglish Edition** | [📄 Download PDF](./03_Nested_Docs_Deletions_Mongoose_Setup_Hinglish.pdf) | [🌐 View HTML](./03_Nested_Docs_Deletions_Mongoose_Setup_Hinglish.html) | Conversational explanations, analogies & Hinglish notes |

---

## 💡 Key Concepts & Code

### 1. Embedded / Nested Documents & Dot Notation
Documents inside MongoDB can store other documents as values. To query fields inside a nested document, use **dot notation** enclosed in quotation marks:

```javascript
// Sample document
{
    name: "Shivam",
    address: {
        city: "Varanasi",
        pincode: 221005
    }
}

// Querying nested fields:
db.users.find({ "address.city": "Varanasi" });
```

### 2. Document Deletion Commands
```javascript
// Delete first matching document
db.products.deleteOne({ name: "Mouse" });

// Delete all matching documents
db.products.deleteMany({ inStock: false });

// Delete all documents in a collection
db.products.deleteMany({});
```

### 3. What is Mongoose ODM?
- **ODM (Object Data Modeling):** An abstraction layer between Node.js and MongoDB.
- Translates JavaScript objects into MongoDB documents and vice-versa.
- Provides strict schema definition, type casting, validation, middleware, and query builders.

### 4. Mongoose Installation & Connection Setup
```bash
npm install mongoose
```

```javascript
const mongoose = require('mongoose');

// Connect to MongoDB instance
mongoose.connect('mongodb://127.0.0.1:27017/shopApp')
    .then(() => console.log('Connected to MongoDB via Mongoose!'))
    .catch((err) => console.error('MongoDB Connection Error:', err));
```
