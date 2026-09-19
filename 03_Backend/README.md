# ⚙️ Backend Web Development

Resources, architectural guides, command cheat sheets, and handwritten notes for complete backend engineering — from command line navigation and server frameworks to relational and NoSQL databases.

---

## 📂 Modules & Learning Track

```plaintext
03_Backend/
├── 📁 01_Terminal/                                    # Priority 1: Terminal & CLI Navigation
│   ├── 📄 Backend_Terminal_Handwritten_Notes.pdf      # Illustrated notes (Topic 01 - 08)
│   ├── 📄 Backend_Terminal_Notes.html                 # Interactive printable notes
│   └── 📄 README.md                                   # CLI commands cheat sheet & guide
│
├── 📁 02_NodeJS/                                      # Priority 2: Node.js Runtime & NPM
│   ├── 📄 Nodejs_Handwritten_Notes_English.pdf       # English handwritten notes (4 pages)
│   ├── 📄 Nodejs_Handwritten_Notes_Hinglish.pdf      # Hinglish handwritten notes (4 pages)
│   ├── 📄 Nodejs_Notes_English.html                  # Printable styled HTML notes (English)
│   ├── 📄 Nodejs_Notes_Hinglish.html                 # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # Node.js runtime & module guide
│
├── 📁 03_Express_EJS/                                 # Priority 3: Express.js & EJS
│   ├── 📄 Express_EJS_Handwritten_Notes_English.pdf  # Express & EJS notes (6 pages)
│   ├── 📄 Express_EJS_Handwritten_Notes_Hinglish.pdf # Hinglish notes (6 pages)
│   ├── 📄 Express_EJS_Notes_English.html             # Printable styled HTML notes (English)
│   ├── 📄 Express_EJS_Notes_Hinglish.html            # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # Express routes, params & EJS guide
│
├── 📁 04_REST_APIs/                                   # Priority 4: RESTful APIs & CRUD
│   ├── 📄 REST_API_Handwritten_Notes_English.pdf     # REST API English notes (8 pages)
│   ├── 📄 REST_API_Handwritten_Notes_Hinglish.pdf    # REST API Hinglish notes (8 pages)
│   ├── 📄 REST_API_Notes_English.html                # Printable styled HTML notes (English)
│   ├── 📄 REST_API_Notes_Hinglish.html               # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # 7 REST CRUD routes & methods guide
│
├── 📁 05_Form_Validation_Errors/                      # Priority 5: Validation & Error Handling
│   ├── 📄 Form_Validation_Errors_Handwritten_Notes_English.pdf  # Validation notes (8 pages)
│   ├── 📄 Form_Validation_Errors_Handwritten_Notes_Hinglish.pdf # Hinglish notes (8 pages)
│   ├── 📄 Form_Validation_Notes_English.html         # Printable styled HTML notes (English)
│   ├── 📄 Form_Validation_Notes_Hinglish.html        # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # Error middleware & wrapAsync guide
│
├── 📁 06_SQL_Database/                                # Priority 6: Relational Databases & SQL
│   ├── 📄 SQL_Database_Handwritten_Notes_English.pdf # SQL English notes (10 pages)
│   ├── 📄 SQL_Database_Handwritten_Notes_Hinglish.pdf# SQL Hinglish notes (10 pages)
│   ├── 📄 SQL_Database_Notes_English.html            # Printable styled HTML notes (English)
│   ├── 📄 SQL_Database_Notes_Hinglish.html           # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # SQL queries, RDBMS, joins & constraints
│
├── 📁 07_Node_MySQL/                                  # Priority 7: Node.js with MySQL
│   ├── 📄 Node_MySQL_Handwritten_Notes_English.pdf   # Node + MySQL notes (8 pages)
│   ├── 📄 Node_MySQL_Handwritten_Notes_Hinglish.pdf  # Hinglish notes (8 pages)
│   ├── 📄 Node_MySQL_Notes_English.html              # Printable styled HTML notes (English)
│   ├── 📄 Node_MySQL_Notes_Hinglish.html             # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # mysql2, connection pools & queries
│
├── 📁 08_MongoDB_Architecture_Shell_BSON/             # Priority 8: MongoDB Architecture, Shell & BSON
│   ├── 📄 01_MongoDB_Architecture_Shell_BSON_English.pdf
│   ├── 📄 01_MongoDB_Architecture_Shell_BSON_Hinglish.pdf
│   ├── 📄 01_MongoDB_Architecture_Shell_BSON_English.html
│   ├── 📄 01_MongoDB_Architecture_Shell_BSON_Hinglish.html
│   └── 📄 README.md
│
├── 📁 09_MongoDB_CRUD_Query_Operators/                # Priority 9: MongoDB CRUD & Query Operators
│   ├── 📄 02_MongoDB_CRUD_Query_Operators_English.pdf
│   ├── 📄 02_MongoDB_CRUD_Query_Operators_Hinglish.pdf
│   ├── 📄 02_MongoDB_CRUD_Query_Operators_English.html
│   ├── 📄 02_MongoDB_CRUD_Query_Operators_Hinglish.html
│   └── 📄 README.md
│
├── 📁 10_MongoDB_Nested_Docs_Mongoose_Setup/          # Priority 10: Nested Documents & Mongoose Setup
│   ├── 📄 03_Nested_Docs_Deletions_Mongoose_Setup_English.pdf
│   ├── 📄 03_Nested_Docs_Deletions_Mongoose_Setup_Hinglish.pdf
│   ├── 📄 03_Nested_Docs_Deletions_Mongoose_Setup_English.html
│   ├── 📄 03_Nested_Docs_Deletions_Mongoose_Setup_Hinglish.html
│   └── 📄 README.md
│
├── 📁 11_Mongoose_Schema_Models_Pluralization/        # Priority 11: Mongoose Schemas & Models
│   ├── 📄 04_Mongoose_Schema_Models_Pluralization_English.pdf
│   ├── 📄 04_Mongoose_Schema_Models_Pluralization_Hinglish.pdf
│   ├── 📄 04_Mongoose_Schema_Models_Pluralization_English.html
│   ├── 📄 04_Mongoose_Schema_Models_Pluralization_Hinglish.html
│   └── 📄 README.md
│
├── 📁 12_Mongoose_Queries_Updates_Validations/        # Priority 12: Mongoose Queries & Validations
│   ├── 📄 05_Mongoose_Queries_Updates_Validations_English.pdf
│   ├── 📄 05_Mongoose_Queries_Updates_Validations_Hinglish.pdf
│   ├── 📄 05_Mongoose_Queries_Updates_Validations_English.html
│   ├── 📄 05_Mongoose_Queries_Updates_Validations_Hinglish.html
│   └── 📄 README.md
│
├── 📁 13_Express_MongoDB_Integration_CRUD/            # Priority 13: Express + MongoDB REST CRUD
│   ├── 📄 06_Express_MongoDB_Integration_CRUD_English.pdf
│   ├── 📄 06_Express_MongoDB_Integration_CRUD_Hinglish.pdf
│   ├── 📄 06_Express_MongoDB_Integration_CRUD_English.html
│   ├── 📄 06_Express_MongoDB_Integration_CRUD_Hinglish.html
│   └── 📄 README.md
│
├── 📁 14_Express_Middlewares_Error_Handling/          # Priority 14: Middlewares & Error Handling
│   ├── 📄 07_Express_Middlewares_Error_Handling_English.pdf
│   ├── 📄 07_Express_Middlewares_Error_Handling_Hinglish.pdf
│   ├── 📄 07_Express_Middlewares_Error_Handling_English.html
│   ├── 📄 07_Express_Middlewares_Error_Handling_Hinglish.html
│   └── 📄 README.md
│
├── 📁 15_Async_Errors_wrapAsync_Pattern/              # Priority 15: Async Errors & wrapAsync Pattern
│   ├── 📄 08_Async_Errors_wrapAsync_Pattern_English.pdf
│   ├── 📄 08_Async_Errors_wrapAsync_Pattern_Hinglish.pdf
│   ├── 📄 08_Async_Errors_wrapAsync_Pattern_English.html
│   ├── 📄 08_Async_Errors_wrapAsync_Pattern_Hinglish.html
│   └── 📄 README.md
│
└── 📁 16_MongoDB_Relationships_Population/            # Priority 16: MongoDB Relationships & Population
    ├── 📄 09_MongoDB_Relationships_Population_English.pdf
    ├── 📄 09_MongoDB_Relationships_Population_Hinglish.pdf
    ├── 📄 09_MongoDB_Relationships_Population_English.html
    ├── 📄 09_MongoDB_Relationships_Population_Hinglish.html
    └── 📄 README.md
```

---

## 📑 Curriculum & Notes Index

| Priority | Module | Description | Status | Link |
| :---: | :--- | :--- | :--- | :--- |
| **1** | **Terminal & Shell Basics** | CLI environment, Shell vs Terminal, Navigation (`cd`, `pwd`, `ls`), Path resolution, Flags, and File operations (`touch`, `mkdir`, `rm`). | Completed | [Explore Terminal Notes](./01_Terminal/) |
| **2** | **Node.js Runtime** | V8 engine, `process` global, modules (CommonJS & ES Modules), directory entry (`index.js`), npm package management, `package.json`. | Completed | [Explore Node.js Notes](./02_NodeJS/) |
| **3** | **Express.js & EJS** | Express servers, dynamic routing, path params (`req.params`), query strings (`req.query`), EJS templating, GET vs POST. | Completed | [Explore Express & EJS Notes](./03_Express_EJS/) |
| **4** | **RESTful APIs & CRUD** | 7 RESTful routes, CRUD architecture, resource naming, method override (`PATCH`/`DELETE`), status codes. | Completed | [Explore REST API Notes](./04_REST_APIs/) |
| **5** | **Form Validation & Errors** | Client & server validation, Bootstrap validation, custom `ExpressError` class, `wrapAsync` utility, error middleware. | Completed | [Explore Validation Notes](./05_Form_Validation_Errors/) |
| **6** | **SQL & Relational Databases** | RDBMS architecture, DDL/DML/DQL commands, constraints (`PRIMARY KEY`, `FOREIGN KEY`), Aggregate functions, Table Joins. | Completed | [Explore SQL Notes](./06_SQL_Database/) |
| **7** | **Node.js with MySQL** | `mysql2` driver, connection pooling (`createPool`), parameterized queries, CRUD implementation with Express, mock data seeding. | Completed | [Explore Node + MySQL Notes](./07_Node_MySQL/) |
| **8** | **MongoDB Architecture, Shell & BSON** | NoSQL document model, MongoDB Server vs Client, Collections vs Tables, BSON vs JSON, `mongosh` CLI commands. | Completed | [Explore Topic 08](./08_MongoDB_Architecture_Shell_BSON/) |
| **9** | **MongoDB CRUD & Query Operators** | `insertOne()`, `insertMany()`, `find()`, comparison operators (`$gt`, `$in`, `$ne`), logical operators (`$and`, `$or`). | Completed | [Explore Topic 09](./09_MongoDB_CRUD_Query_Operators/) |
| **10** | **Nested Documents & Mongoose Setup** | Embedded/nested documents, dot notation queries (`address.city`), deletion commands, installing Mongoose, `mongoose.connect()`. | Completed | [Explore Topic 10](./10_MongoDB_Nested_Docs_Mongoose_Setup/) |
| **11** | **Mongoose Schemas & Models** | `new mongoose.Schema()`, SchemaTypes, compiling models with `mongoose.model()`, automatic lowercase pluralization rules. | Completed | [Explore Topic 11](./11_Mongoose_Schema_Models_Pluralization/) |
| **12** | **Mongoose Queries & Validations** | Built-in validations (`required`, `min`, `enum`), custom validators, `findByIdAndUpdate()`, `runValidators: true`, delete methods. | Completed | [Explore Topic 12](./12_Mongoose_Queries_Updates_Validations/) |
| **13** | **Express + MongoDB Integration (CRUD)** | Building a full RESTful Express app with Mongoose models, Index, Show, New, Create, Edit, Update, and Destroy routes. | Completed | [Explore Topic 13](./13_Express_MongoDB_Integration_CRUD/) |
| **14** | **Express Middlewares & Error Handling** | Middleware lifecycle (`req, res, next`), custom error classes (`ExpressError`), default 500 error handlers, 404 Not Found routes. | Completed | [Explore Topic 14](./14_Express_Middlewares_Error_Handling/) |
| **15** | **Async Errors & wrapAsync Pattern** | Unhandled promise rejections in Express, `try-catch` boilerplate elimination using higher-order wrapper functions (`wrapAsync`). | Completed | [Explore Topic 15](./15_Async_Errors_wrapAsync_Pattern/) |
| **16** | **MongoDB Relationships & Population** | One-to-Few (Embedded), One-to-Many (References with `ObjectId`), One-to-Squillions, using `.populate()` to fetch documents. | Completed | [Explore Topic 16](./16_MongoDB_Relationships_Population/) |

---

## 🚀 Quick Links

- [Open Terminal Notes PDF](./01_Terminal/Backend_Terminal_Handwritten_Notes.pdf)
- [Open Node.js Notes (English) PDF](./02_NodeJS/Nodejs_Handwritten_Notes_English.pdf)
- [Open Express & EJS Notes (English) PDF](./03_Express_EJS/Express_EJS_Handwritten_Notes_English.pdf)
- [Open REST API Notes (English) PDF](./04_REST_APIs/REST_API_Handwritten_Notes_English.pdf)
- [Open Form Validation Notes (English) PDF](./05_Form_Validation_Errors/Form_Validation_Errors_Handwritten_Notes_English.pdf)
- [Open SQL Database Notes (English) PDF](./06_SQL_Database/SQL_Database_Handwritten_Notes_English.pdf)
- [Open Node + MySQL Notes (English) PDF](./07_Node_MySQL/Node_MySQL_Handwritten_Notes_English.pdf)
- [Open MongoDB Architecture & BSON Notes PDF](./08_MongoDB_Architecture_Shell_BSON/01_MongoDB_Architecture_Shell_BSON_English.pdf)
- [Open MongoDB CRUD & Query Operators Notes PDF](./09_MongoDB_CRUD_Query_Operators/02_MongoDB_CRUD_Query_Operators_English.pdf)
- [Open Nested Docs & Mongoose Setup Notes PDF](./10_MongoDB_Nested_Docs_Mongoose_Setup/03_Nested_Docs_Deletions_Mongoose_Setup_English.pdf)
- [Open Mongoose Schemas & Models Notes PDF](./11_Mongoose_Schema_Models_Pluralization/04_Mongoose_Schema_Models_Pluralization_English.pdf)
- [Open Mongoose Queries & Validations Notes PDF](./12_Mongoose_Queries_Updates_Validations/05_Mongoose_Queries_Updates_Validations_English.pdf)
- [Open Express + MongoDB Integration Notes PDF](./13_Express_MongoDB_Integration_CRUD/06_Express_MongoDB_Integration_CRUD_English.pdf)
- [Open Express Middlewares & Error Handling Notes PDF](./14_Express_Middlewares_Error_Handling/07_Express_Middlewares_Error_Handling_English.pdf)
- [Open Async Errors & wrapAsync Notes PDF](./15_Async_Errors_wrapAsync_Pattern/08_Async_Errors_wrapAsync_Pattern_English.pdf)
- [Open MongoDB Relationships & Population Notes PDF](./16_MongoDB_Relationships_Population/09_MongoDB_Relationships_Population_English.pdf)
