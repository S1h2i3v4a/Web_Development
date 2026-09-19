# 🔗 MongoDB Data Relationships & Mongoose Population

Comprehensive handwritten notes, schema relationship diagrams, and code guides covering **One-to-Few, One-to-Many, One-to-Squillions, Mongoose `.populate()`, and cascade deletion middlewares**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./09_MongoDB_Relationships_Population_English.pdf) | [🌐 View HTML](./09_MongoDB_Relationships_Population_English.html) | Relational architecture, populate patterns & English notes |
| **Hinglish Edition** | [📄 Download PDF](./09_MongoDB_Relationships_Population_Hinglish.pdf) | [🌐 View HTML](./09_MongoDB_Relationships_Population_Hinglish.html) | Conversational explanations, real-world analogies & Hinglish notes |

---

## 💡 The 3 NoSQL Relationship Models

### 1. One-to-Few (Embedded / Nested)
Used when subdocuments are few and tightly coupled to parent (e.g., User with 2-3 addresses):
```javascript
const userSchema = new mongoose.Schema({
    name: String,
    addresses: [
        {
            location: String,
            city: String
        }
    ]
});
```

### 2. One-to-Many (Referenced using `ObjectId`)
Used when child documents can grow into hundreds or are shared across entities (e.g., User and Orders):
```javascript
const userSchema = new mongoose.Schema({
    name: String,
    orders: [
        {
            type: mongoose.Schema.Types.ObjectId,
            ref: 'Order' // Reference to Order model
        }
    ]
});
```

### 3. One-to-Squillions (Parent Referencing)
Used when child documents can grow into millions (e.g., Twitter Tweets or Log entries). Instead of storing an unbounded array on the user, each child document stores the parent's `ObjectId`:
```javascript
const tweetSchema = new mongoose.Schema({
    text: String,
    likes: Number,
    user: {
        type: mongoose.Schema.Types.ObjectId,
        ref: 'User' // Reference to parent User
    }
});
```

---

## 💻 Mongoose `.populate()` & Cascade Deletions

### Populating References
```javascript
// Populate the 'orders' field with full documents instead of just IDs
const user = await User.findOne({ name: 'Shivam' }).populate('orders');
console.log(user.orders); // Array of full Order documents
```

### Cascade Deletion Middleware
```javascript
// Automatically delete all associated orders when a user is deleted
userSchema.post('findOneAndDelete', async function (user) {
    if (user.orders.length) {
        await Order.deleteMany({ _id: { $in: user.orders } });
    }
});
```
