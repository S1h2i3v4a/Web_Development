# ⚙️ Backend Web Development

Resources, architectural guides, command cheat sheets, and handwritten notes for complete backend engineering — from command line navigation and server frameworks to relational and NoSQL databases.

---

## 📂 Modules & Learning Track

```plaintext
03_Backend/
├── 📁 01_Terminal/                                    # Priority 4: Terminal & CLI
│   ├── 📄 Backend_Terminal_Handwritten_Notes.pdf      # Illustrated notes (Topic 01 - 08)
│   ├── 📄 Backend_Terminal_Notes.html                 # Interactive printable notes
│   └── 📄 README.md                                   # CLI commands cheat sheet & guide
│
├── 📁 02_NodeJS/                                      # Priority 5: Node.js Runtime
│   ├── 📄 Nodejs_Handwritten_Notes_English.pdf       # English handwritten notes (4 pages)
│   ├── 📄 Nodejs_Handwritten_Notes_Hinglish.pdf      # Hinglish handwritten notes (4 pages)
│   ├── 📄 Nodejs_Notes_English.html                  # Printable styled HTML notes (English)
│   ├── 📄 Nodejs_Notes_Hinglish.html                 # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # Node.js runtime & module guide
│
├── 📁 03_Express_EJS/                                 # Priority 6: Express.js & EJS
│   ├── 📄 Express_EJS_Handwritten_Notes_English.pdf  # Express & EJS notes (6 pages)
│   ├── 📄 Express_EJS_Handwritten_Notes_Hinglish.pdf # Hinglish notes (6 pages)
│   ├── 📄 Express_EJS_Notes_English.html             # Printable styled HTML notes (English)
│   ├── 📄 Express_EJS_Notes_Hinglish.html            # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # Express routes, params & EJS guide
│
├── 📁 04_REST_APIs/                                   # Priority 7: RESTful APIs & CRUD
│   ├── 📄 REST_API_Handwritten_Notes_English.pdf     # REST API English notes (8 pages)
│   ├── 📄 REST_API_Handwritten_Notes_Hinglish.pdf    # REST API Hinglish notes (8 pages)
│   ├── 📄 REST_API_Notes_English.html                # Printable styled HTML notes (English)
│   ├── 📄 REST_API_Notes_Hinglish.html               # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # 7 REST CRUD routes & methods guide
│
├── 📁 05_Form_Validation_Errors/                      # Priority 8: Validation & Error Handling
│   ├── 📄 Form_Validation_Errors_Handwritten_Notes_English.pdf  # Validation notes (8 pages)
│   ├── 📄 Form_Validation_Errors_Handwritten_Notes_Hinglish.pdf # Hinglish notes (8 pages)
│   ├── 📄 Form_Validation_Notes_English.html         # Printable styled HTML notes (English)
│   ├── 📄 Form_Validation_Notes_Hinglish.html        # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # Error middleware & wrapAsync guide
│
├── 📁 06_SQL_Database/                                # Priority 9: Relational Databases & SQL
│   ├── 📄 SQL_Database_Handwritten_Notes_English.pdf # SQL English notes (10 pages)
│   ├── 📄 SQL_Database_Handwritten_Notes_Hinglish.pdf# SQL Hinglish notes (10 pages)
│   ├── 📄 SQL_Database_Notes_English.html            # Printable styled HTML notes (English)
│   ├── 📄 SQL_Database_Notes_Hinglish.html           # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # SQL queries, RDBMS, joins & constraints
│
├── 📁 07_Node_MySQL/                                  # Priority 10: Node.js with MySQL
│   ├── 📄 Node_MySQL_Handwritten_Notes_English.pdf   # Node + MySQL notes (8 pages)
│   ├── 📄 Node_MySQL_Handwritten_Notes_Hinglish.pdf  # Hinglish notes (8 pages)
│   ├── 📄 Node_MySQL_Notes_English.html              # Printable styled HTML notes (English)
│   ├── 📄 Node_MySQL_Notes_Hinglish.html             # Printable styled HTML notes (Hinglish)
│   └── 📄 README.md                                  # mysql2, connection pools & queries
│
└── 📁 08_MongoDB_Mongoose/                            # Priority 11: NoSQL & Mongoose ODM
    ├── 📁 English/                                   # 9 Topicwise English PDFs & HTMLs
    ├── 📁 Hinglish/                                  # 9 Topicwise Hinglish PDFs & HTMLs
    └── 📄 README.md                                  # 9-topic curriculum, schemas & populate
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
| **8** | **MongoDB & Mongoose ODM** | NoSQL document model, BSON, `mongosh` shell CRUD, Mongoose schemas, validations, Express integration, relationships & `.populate()`. | Completed | [Explore MongoDB Notes](./08_MongoDB_Mongoose/) |
| **—** | **Authentication & Security** | JWT, Sessions, OAuth, Password hashing (bcrypt), CORS, Helmet, Rate limiting. | Planned | *Upcoming* |

---

## 🚀 Quick Links

- [Open Terminal Notes PDF](./01_Terminal/Backend_Terminal_Handwritten_Notes.pdf)
- [Open Node.js Notes (English) PDF](./02_NodeJS/Nodejs_Handwritten_Notes_English.pdf)
- [Open Express & EJS Notes (English) PDF](./03_Express_EJS/Express_EJS_Handwritten_Notes_English.pdf)
- [Open REST API Notes (English) PDF](./04_REST_APIs/REST_API_Handwritten_Notes_English.pdf)
- [Open Form Validation Notes (English) PDF](./05_Form_Validation_Errors/Form_Validation_Errors_Handwritten_Notes_English.pdf)
- [Open SQL Database Notes (English) PDF](./06_SQL_Database/SQL_Database_Handwritten_Notes_English.pdf)
- [Open Node + MySQL Notes (English) PDF](./07_Node_MySQL/Node_MySQL_Handwritten_Notes_English.pdf)
- [Open MongoDB & Mongoose Curriculum Index](./08_MongoDB_Mongoose/README.md)
