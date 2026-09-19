# ⚡ Mongoose Queries, Updates & Schema Validations

Comprehensive handwritten notes, method comparisons, and validation guides covering **Mongoose query operations, document updating, built-in validations, and custom validators**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./05_Mongoose_Queries_Updates_Validations_English.pdf) | [🌐 View HTML](./05_Mongoose_Queries_Updates_Validations_English.html) | Method cheat sheets, validation rules & English notes |
| **Hinglish Edition** | [📄 Download PDF](./05_Mongoose_Queries_Updates_Validations_Hinglish.pdf) | [🌐 View HTML](./05_Mongoose_Queries_Updates_Validations_Hinglish.html) | Conversational explanations, edge cases & Hinglish notes |

---

## 💡 Key Operations & Code

### 1. Querying Documents
```javascript
// Find all matching documents
const expensiveBooks = await Book.find({ price: { $gte: 500 } });

// Find single document by query
const book = await Book.findOne({ author: "Cal Newport" });

// Find single document by ID
const bookById = await Book.findById("64a7f9b8c1234567890abcde");
```

### 2. Updating Documents & `runValidators`
By default, Mongoose does **NOT** run schema validations on update operations! Always pass `{ runValidators: true, new: true }`:

```javascript
// findByIdAndUpdate with options
const updatedBook = await Book.findByIdAndUpdate(
    id,
    { price: 599 },
    { new: true, runValidators: true } // Return updated doc & enforce schema rules
);
```

### 3. Built-in Schema Validations
```javascript
const productSchema = new mongoose.Schema({
    name: {
        type: String,
        required: [true, 'Product name is required!'],
        maxlength: [50, 'Name cannot exceed 50 characters'],
        trim: true
    },
    price: {
        type: Number,
        min: [0, 'Price must be positive']
    },
    category: {
        type: String,
        enum: ['electronics', 'books', 'fashion'] // Restricted to allowed list
    }
});
```

### 4. Custom Validators
```javascript
const userSchema = new mongoose.Schema({
    phone: {
        type: String,
        validate: {
            validator: function(v) {
                return /^\d{10}$/.test(v); // Must be exactly 10 digits
            },
            message: props => `${props.value} is not a valid 10-digit phone number!`
        }
    }
});
```
