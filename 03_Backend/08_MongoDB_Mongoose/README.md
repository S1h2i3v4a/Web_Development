# 🍃 MongoDB & Mongoose ODM (NoSQL Database)

Comprehensive handwritten notes, architecture diagrams, shell cheat sheets, code guides, and topicwise modules covering **MongoDB (NoSQL Document Database), Mongoose ODM, Express Integration, Schema Design, and Data Relationships** (available in both **English** and **Hinglish** editions).

---

## 📑 Complete 9-Topic Curriculum Index

All 9 topics are organized into dedicated subfolders with high-resolution handwritten PDF notes and interactive printable HTML guides:

| Topic # | Topic Title | Focus & Key Concepts | English Edition | Hinglish Edition |
| :---: | :--- | :--- | :--- | :--- |
| **01** | **MongoDB Architecture, Shell & BSON** | NoSQL Document model, MongoDB Server vs Client, Collections vs Tables, BSON vs JSON, `mongosh` CLI commands (`show dbs`, `use`, `show collections`). | [PDF](./English/01_MongoDB_Architecture_Shell_BSON_English.pdf) • [HTML](./English/01_MongoDB_Architecture_Shell_BSON_English.html) | [PDF](./Hinglish/01_MongoDB_Architecture_Shell_BSON_Hinglish.pdf) • [HTML](./Hinglish/01_MongoDB_Architecture_Shell_BSON_Hinglish.html) |
| **02** | **MongoDB CRUD & Query Operators** | `insertOne()`, `insertMany()`, `find()`, `findOne()`, query filters, comparison operators (`$gt`, `$gte`, `$lt`, `$lte`, `$in`, `$ne`), logical operators (`$and`, `$or`). | [PDF](./English/02_MongoDB_CRUD_Query_Operators_English.pdf) • [HTML](./English/02_MongoDB_CRUD_Query_Operators_English.html) | [PDF](./Hinglish/02_MongoDB_CRUD_Query_Operators_Hinglish.pdf) • [HTML](./Hinglish/02_MongoDB_CRUD_Query_Operators_Hinglish.html) |
| **03** | **Nested Documents & Mongoose Setup** | Embedded/nested documents, dot notation queries (`address.city`), deletion commands (`deleteOne`, `deleteMany`), installing Mongoose, connecting via `mongoose.connect()`. | [PDF](./English/03_Nested_Docs_Deletions_Mongoose_Setup_English.pdf) • [HTML](./English/03_Nested_Docs_Deletions_Mongoose_Setup_English.html) | [PDF](./Hinglish/03_Nested_Docs_Deletions_Mongoose_Setup_Hinglish.pdf) • [HTML](./Hinglish/03_Nested_Docs_Deletions_Mongoose_Setup_Hinglish.html) |
| **04** | **Mongoose Schemas, Models & Pluralization** | `new mongoose.Schema()`, SchemaTypes (`String`, `Number`, `Boolean`, `Date`), compiling models with `mongoose.model()`, automatic lowercase pluralization rules. | [PDF](./English/04_Mongoose_Schema_Models_Pluralization_English.pdf) • [HTML](./English/04_Mongoose_Schema_Models_Pluralization_English.html) | [PDF](./Hinglish/04_Mongoose_Schema_Models_Pluralization_Hinglish.pdf) • [HTML](./Hinglish/04_Mongoose_Schema_Models_Pluralization_Hinglish.html) |
| **05** | **Queries, Updates & Schema Validations** | Built-in validations (`required`, `min`, `max`, `enum`), custom validators, `findByIdAndUpdate()`, enabling `runValidators: true`, delete operations. | [PDF](./English/05_Mongoose_Queries_Updates_Validations_English.pdf) • [HTML](./English/05_Mongoose_Queries_Updates_Validations_English.html) | [PDF](./Hinglish/05_Mongoose_Queries_Updates_Validations_Hinglish.pdf) • [HTML](./Hinglish/05_Mongoose_Queries_Updates_Validations_Hinglish.html) |
| **06** | **Express + MongoDB Integration (CRUD)** | Building a full RESTful Express application with Mongoose models, Index, Show, New, Create, Edit, Update, and Destroy routes. | [PDF](./English/06_Express_MongoDB_Integration_CRUD_English.pdf) • [HTML](./English/06_Express_MongoDB_Integration_CRUD_English.html) | [PDF](./Hinglish/06_Express_MongoDB_Integration_CRUD_Hinglish.pdf) • [HTML](./Hinglish/06_Express_MongoDB_Integration_CRUD_Hinglish.html) |
| **07** | **Express Middlewares & Error Handling** | Middleware lifecycle (`req, res, next`), custom error classes (`ExpressError`), default 500 error handlers, handling 404 Not Found routes. | [PDF](./English/07_Express_Middlewares_Error_Handling_English.pdf) • [HTML](./English/07_Express_Middlewares_Error_Handling_English.html) | [PDF](./Hinglish/07_Express_Middlewares_Error_Handling_Hinglish.pdf) • [HTML](./Hinglish/07_Express_Middlewares_Error_Handling_Hinglish.html) |
| **08** | **Async Errors & wrapAsync Pattern** | Unhandled promise rejections in Express, `try-catch` boilerplate elimination using higher-order wrapper functions (`wrapAsync`). | [PDF](./English/08_Async_Errors_wrapAsync_Pattern_English.pdf) • [HTML](./English/08_Async_Errors_wrapAsync_Pattern_English.html) | [PDF](./Hinglish/08_Async_Errors_wrapAsync_Pattern_Hinglish.pdf) • [HTML](./Hinglish/08_Async_Errors_wrapAsync_Pattern_Hinglish.html) |
| **09** | **MongoDB Relationships & Population** | One-to-Few (Embedded), One-to-Many (Parent/Child References with `ObjectId`), One-to-Squillions, using `.populate()` to fetch referenced documents. | [PDF](./English/09_MongoDB_Relationships_Population_English.pdf) • [HTML](./English/09_MongoDB_Relationships_Population_English.html) | [PDF](./Hinglish/09_MongoDB_Relationships_Population_Hinglish.pdf) • [HTML](./Hinglish/09_MongoDB_Relationships_Population_Hinglish.html) |

---

## 💻 Essential Mongoose Code Patterns

### 1. Connection & Schema Setup
```javascript
const mongoose = require('mongoose');

// Connect to local MongoDB instance
mongoose.connect('mongodb://127.0.0.1:27017/shopApp')
    .then(() => console.log('MongoDB Connected Successfully!'))
    .catch(err => console.error('MongoDB Connection Error:', err));

// Define Schema with Validations
const productSchema = new mongoose.Schema({
    name: {
        type: String,
        required: [true, 'Product name is mandatory!'],
        trim: true,
        maxlength: [100, 'Name cannot exceed 100 characters']
    },
    price: {
        type: Number,
        required: true,
        min: [0, 'Price cannot be negative']
    },
    category: {
        type: String,
        lowercase: true,
        enum: ['electronics', 'clothing', 'books', 'groceries']
    },
    inStock: {
        type: Boolean,
        default: true
    }
}, { timestamps: true });

// Compile Model (Collection name will be 'products')
const Product = mongoose.model('Product', productSchema);
```

### 2. Relationships with References & Populate
```javascript
const userSchema = new mongoose.Schema({
    username: String,
    orders: [
        {
            type: mongoose.Schema.Types.ObjectId,
            ref: 'Order' // Reference to Order model
        }
    ]
});

const User = mongoose.model('User', userSchema);

// Finding a user and populating their full order documents:
const userWithOrders = await User.findOne({ username: 'shivam' }).populate('orders');
console.log(userWithOrders.orders); // Full Order documents instead of just ObjectIds!
```

---

## 📂 Subdirectories

- [**`English/`**](./English/) — All 9 topicwise handwritten PDF notes and printable HTML files in English.
- [**`Hinglish/`**](./Hinglish/) — All 9 topicwise handwritten PDF notes and printable HTML files in conversational Hinglish.
