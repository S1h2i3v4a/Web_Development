# 🔍 MongoDB CRUD Operations & Query Operators

Comprehensive handwritten notes, query operator cheat sheets, and code guides covering **MongoDB shell CRUD operations, comparison operators, and logical operators**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./02_MongoDB_CRUD_Query_Operators_English.pdf) | [🌐 View HTML](./02_MongoDB_CRUD_Query_Operators_English.html) | Formal technical explanations, filter syntax & English notes |
| **Hinglish Edition** | [📄 Download PDF](./02_MongoDB_CRUD_Query_Operators_Hinglish.pdf) | [🌐 View HTML](./02_MongoDB_CRUD_Query_Operators_Hinglish.html) | Conversational explanations, analogies & Hinglish notes |

---

## 💡 Key CRUD Commands & Operators

### 1. Insertion (Create)
```javascript
// Insert single document
db.products.insertOne({
    name: "Mechanical Keyboard",
    price: 3499,
    category: "Electronics",
    inStock: true
});

// Insert multiple documents
db.products.insertMany([
    { name: "Gaming Mouse", price: 1499, category: "Electronics" },
    { name: "USB-C Hub", price: 899, category: "Accessories" }
]);
```

### 2. Querying (Read) & Projections
```javascript
// Find all documents
db.products.find();

// Find with filter condition
db.products.find({ category: "Electronics" });

// Find single document
db.products.findOne({ _id: ObjectId("64a7f9b8c1234567890abcde") });

// Projection: Return only name and price, exclude _id
db.products.find({}, { name: 1, price: 1, _id: 0 });
```

### 3. Comparison Query Operators
- `$eq` / `$ne`: Matches values equal to / not equal to a specified value.
- `$gt` / `$gte`: Greater than / Greater than or equal to.
- `$lt` / `$lte`: Less than / Less than or equal to.
- `$in` / `$nin`: Matches any of the values specified in an array / none of the values.

```javascript
// Find products priced between 1000 and 5000
db.products.find({ price: { $gte: 1000, $lte: 5000 } });

// Find products in specific categories
db.products.find({ category: { $in: ["Electronics", "Computers"] } });
```

### 4. Logical Query Operators
- `$and`: Joins query clauses with a logical AND.
- `$or`: Joins query clauses with a logical OR.
- `$not`: Inverts the effect of a query predicate.
- `$nor`: Matches all documents where both clauses fail.

```javascript
// Find products that are in Electronics OR cost less than 1000
db.products.find({
    $or: [
        { category: "Electronics" },
        { price: { $lt: 1000 } }
    ]
});
```
