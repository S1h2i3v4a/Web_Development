# 🟢 Node.js Runtime & Module System Notes

Comprehensive handwritten notes, illustrated architecture diagrams, and quick-reference guides covering the **Node.js Runtime**, module exports/imports, and package management with **NPM** (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **Node.js Handwritten Notes (English)** | English | PDF (4 Pages) | [`Nodejs_Handwritten_Notes_English.pdf`](./Nodejs_Handwritten_Notes_English.pdf) |
| **Node.js Handwritten Notes (Hinglish)** | Hinglish | PDF (4 Pages) | [`Nodejs_Handwritten_Notes_Hinglish.pdf`](./Nodejs_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`Nodejs_Topper_Notes_English.html`](./Nodejs_Topper_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`Nodejs_Topper_Notes_Hinglish.html`](./Nodejs_Topper_Notes_Hinglish.html) |

---

## 📚 Topics & Key Concepts

### 1. What is Node.js?
- **Definition:** Node.js is an open-source, cross-platform **JavaScript Runtime Environment** that executes JavaScript outside the web browser on the server.
- **Under the Hood:**
  $$\text{Chrome V8 Engine} + \text{C++ Bindings} + \text{Libuv (Event Loop \& Async I/O)} \longrightarrow \text{Node.js Runtime}$$
- **Golden Rule:** Node.js is **NOT** a language, library, or framework. It is an execution runtime.
- **Node REPL:** Launch the interactive REPL in the terminal by simply typing:
  ```bash
  node
  ```

---

### 2. The `process` Object
The `process` global provides information and control over the current running Node.js process:
- `process.version`: Node.js version installed.
- `process.argv`: Array containing command-line arguments passed when executing the script.
- `process.cwd()`: Current working directory from where the command was executed.
- `process.exit()`: Terminates the running Node.js process.

---

### 3. Modular Programming & Exports (CommonJS vs ES6)

#### Exporting & Importing with CommonJS (Default):
```javascript
// math.js
const sum = (a, b) => a + b;
const PI = 3.14159;

module.exports = { sum, PI };
```
```javascript
// app.js
const math = require('./math');
console.log(math.sum(2, 3)); // 5
```

#### Requiring an Entire Directory:
When importing a folder without specifying a filename:
```javascript
const fruits = require('./fruits');
```
Node.js automatically looks for and executes **`index.js`** inside that folder as the default entry point!

---

### 4. NPM (Node Package Manager)

NPM serves two critical functions:
1. **Online Registry:** Centralized open-source repository containing millions of JavaScript libraries.
2. **CLI Tool:** Terminal package manager used to install, update, and manage dependencies.

#### Key Files & Directories:
| Entity | Role |
| :--- | :--- |
| `package.json` | Project manifest recording metadata, scripts (`start`, `dev`), and direct dependencies (`npm init -y`). |
| `package-lock.json` | Automatically generated lockfile pinning exact semantic versions and nested dependency trees for reproducible builds. |
| `node_modules/` | Directory where downloaded package code resides. **Must be added to `.gitignore`**. |

---

### 5. Common NPM Commands

```bash
npm init -y             # Initialize project with default package.json
npm install <pkg>       # Install package as local dependency (e.g. npm i express)
npm install -D <pkg>    # Install package as development dependency (e.g. nodemon)
npm install -g <pkg>    # Install package globally on machine
npm uninstall <pkg>     # Remove an installed package
```
