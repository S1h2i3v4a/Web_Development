# 🍃 MongoDB Architecture, Shell & BSON

Comprehensive handwritten notes, architectural diagrams, shell cheat sheets, and conceptual guides covering **MongoDB NoSQL Architecture, Document Model, BSON data types, and mongosh CLI commands**.

---

## 📑 Study Notes & Visual Guides

| Edition | Handwritten Notes PDF | Interactive Web Notes HTML | Focus & Language |
| :--- | :--- | :--- | :--- |
| **English Edition** | [📄 Download PDF](./01_MongoDB_Architecture_Shell_BSON_English.pdf) | [🌐 View HTML](./01_MongoDB_Architecture_Shell_BSON_English.html) | Formal technical explanations, diagrams & English notes |
| **Hinglish Edition** | [📄 Download PDF](./01_MongoDB_Architecture_Shell_Hinglish.pdf) | [🌐 View HTML](./01_MongoDB_Architecture_Shell_BSON_Hinglish.html) | Conversational explanations, real-world analogies & Hinglish notes |

---

## 💡 Key Architectural Concepts

### 1. SQL vs NoSQL (Document Database)
- **RDBMS (SQL):** Tables, Rows, Columns, Fixed Schema, Foreign Keys, ACID transactions.
- **MongoDB (NoSQL):** Collections, Documents (BSON/JSON), Dynamic Flexible Schema, Embedded & Referenced data.

### 2. MongoDB Architecture
- **MongoDB Server (`mongod`):** The background daemon process that manages data requests, formats, and background operations.
- **MongoDB Shell (`mongosh`):** Interactive JavaScript interface to communicate with the MongoDB server directly.
- **Database > Collections > Documents:** A MongoDB instance contains multiple databases, each containing collections, which store individual JSON/BSON documents.

### 3. BSON vs JSON
- **JSON (JavaScript Object Notation):** Human-readable text format, limited types (string, number, boolean, array, object, null).
- **BSON (Binary JSON):** Binary-encoded serialization of JSON-like documents. High performance, fast traversability, lightweight, and supports extra types:
  - `ObjectId` (12-byte unique identifier)
  - `Date` (64-bit integer timestamp)
  - `BinData` (binary data/byte arrays)
  - `Decimal128` (high-precision numbers)

---

## 💻 Essential `mongosh` Shell Commands

```javascript
// 1. View all databases
show dbs

// 2. Switch to / Create a database
use shopApp

// 3. Check currently active database
db

// 4. View collections in active database
show collections

// 5. Drop current database
db.dropDatabase()

// 6. Drop a specific collection
db.products.drop()
```
