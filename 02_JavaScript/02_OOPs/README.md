# 🧱 Object-Oriented Programming (OOP) in JavaScript

Comprehensive handwritten notes, prototype chaining diagrams, and quick-reference cheat sheets covering **Object-Oriented Programming (OOP)** in JavaScript (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **OOPs in JS Handwritten Notes (English)** | English | PDF (4 Pages) | [`OOPs_JS_Handwritten_Notes_English.pdf`](./OOPs_JS_Handwritten_Notes_English.pdf) |
| **OOPs in JS Handwritten Notes (Hinglish)** | Hinglish | PDF (5 Pages) | [`OOPs_JS_Handwritten_Notes_Hinglish.pdf`](./OOPs_JS_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`OOPs_JS_Notes_English.html`](./OOPs_JS_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`OOPs_JS_Notes_Hinglish.html`](./OOPs_JS_Notes_Hinglish.html) |

---

## 📚 Topics & Key Concepts

### 1. Purpose of OOP
- **Core Philosophy:** Structure and organize code into modular, reusable objects that bundle state (properties) and behavior (methods) together.
- **Why OOP?** Eliminates redundant code duplication, adheres to the DRY (*Don't Repeat Yourself*) principle, and models real-world business domains effectively.

---

### 2. Prototypes & Prototype Chaining
In JavaScript, objects inherit properties directly from other objects through their internal prototype link:
- Every JavaScript object has a built-in reference called `[[Prototype]]` (accessible via `__proto__`).
- **Prototype Chain:** When accessing a property or method on an object, JavaScript checks:
  $$\text{Current Object} \longrightarrow \text{Object.__proto__} \longrightarrow \text{Object.prototype} \longrightarrow \text{null}$$

```javascript
const arr = [1, 2, 3];
console.log(arr.__proto__ === Array.prototype); // true
console.log(Array.prototype.__proto__ === Object.prototype); // true
```

---

### 3. Factory Functions vs Constructors & The `new` Keyword

#### The `new` Operator Mechanism:
When invoking a function with `new`:
1. Creates a brand new, empty object `{}`.
2. Binds `this` to point to the newly created instance.
3. Links the new object's prototype (`__proto__`) to the constructor's `prototype`.
4. Implicitly returns `this` if no explicit object is returned.

```javascript
function Person(name, age) {
    this.name = name;
    this.age = age;
}

Person.prototype.greet = function() {
    return `Hello, my name is ${this.name}!`;
};

const user = new Person('Shivam', 22);
```

---

### 4. Modern ES6 Classes & Inheritance

ES6 introduced syntactical sugar over JavaScript's existing prototype-based inheritance:

```javascript
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    introduce() {
        return `Hi, I am ${this.name}, ${this.age} years old.`;
    }
}

class Developer extends Person {
    constructor(name, age, techStack) {
        super(name, age); // Calls parent Person constructor
        this.techStack = techStack;
    }

    code() {
        return `${this.name} is coding with ${this.techStack}.`;
    }
}

const dev = new Developer('Shivam', 22, 'Full Stack JavaScript');
console.log(dev.introduce());
console.log(dev.code());
```

---

### 5. Summary Cheat Sheet

| Feature | Description | Example |
| :--- | :--- | :--- |
| `prototype` | Property on functions/classes where shared methods reside | `Person.prototype.talk = ...` |
| `__proto__` | Reference on an object pointing to its prototype | `obj.__proto__` |
| `constructor` | Special method called when instantiating a class | `constructor(name) { ... }` |
| `extends` | Keyword establishing class inheritance | `class Student extends Person` |
| `super()` | Calls parent class constructor and methods | `super(name, age)` |
