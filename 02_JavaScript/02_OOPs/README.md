# 🧱 Object-Oriented Programming (OOP) in JavaScript

Comprehensive handwritten notes, prototype chaining diagrams, VS Code-formatted code snippets, and cheat sheets covering the **4 Core Pillars of OOP (Encapsulation, Inheritance, Polymorphism, Abstraction)**, ES6 classes, prototypes, and advanced design principles in JavaScript (available in both **English** and **Hinglish** editions).

---

## 📑 Included Resources

| Resource | Language | Format / Pages | Link |
| :--- | :--- | :--- | :--- |
| **OOPs in JS Notes (English)** | English | PDF (8 Pages) | [`OOPs_JS_Handwritten_Notes_English.pdf`](./OOPs_JS_Handwritten_Notes_English.pdf) |
| **OOPs in JS Notes (Hinglish)** | Hinglish | PDF (9 Pages) | [`OOPs_JS_Handwritten_Notes_Hinglish.pdf`](./OOPs_JS_Handwritten_Notes_Hinglish.pdf) |
| **Interactive Printable Notes (English)** | English | HTML Document | [`OOPs_JS_Notes_English.html`](./OOPs_JS_Notes_English.html) |
| **Interactive Printable Notes (Hinglish)** | Hinglish | HTML Document | [`OOPs_JS_Notes_Hinglish.html`](./OOPs_JS_Notes_Hinglish.html) |

---

## 🏛️ The 4 Core Pillars of OOP in JavaScript

```plaintext
                   ┌─────────────────────────────────────────┐
                   │    4 Pillars of OOP in JavaScript       │
                   └────────────────────┬────────────────────┘
                                        │
         ┌──────────────────┬───────────┴───────────┬──────────────────┐
         │                  │                       │                  │
         ▼                  ▼                       ▼                  ▼
┌─────────────────┐ ┌─────────────────┐   ┌─────────────────┐ ┌─────────────────┐
│ 1. Encapsulation│ │ 2. Inheritance  │   │ 3. Polymorphism │ │ 4. Abstraction  │
│  (#private,     │ │  (extends,      │   │  (Method        │ │  (Hiding details│
│   get/set)      │ │   super())      │   │   Overriding)   │ │   new.target)   │
└─────────────────┘ └─────────────────┘   └─────────────────┘ └─────────────────┘
```

---

### 1. 🛡️ Pillar 1: Encapsulation
**Concept:** Bundling data (properties) and behavior (methods) together while **restricting direct external access** to sensitive internal state.
- **Modern ES2022 Private Fields (`#`):** Truly private fields enforced at runtime by the V8 JavaScript engine.
- **Private Methods (`#method()`):** Helper methods callable only from within the class body.
- **Getters & Setters (`get`, `set`):** Provide controlled, validated read/write access.

```javascript
// BankAccount.js (VS Code Format)
class BankAccount {
    owner;             // Public field
    #balance = 0;      // Private field (ES2022)
    #pin;              // Private field

    constructor(owner, initialDeposit, pin) {
        this.owner = owner;
        this.#balance = initialDeposit;
        this.#pin = pin;
    }

    // Private Method: Internal validation helper
    #validatePin(enteredPin) {
        return this.#pin === enteredPin;
    }

    // Public Method: Controlled mutation
    withdraw(amount, pin) {
        if (!this.#validatePin(pin)) throw new Error("Invalid PIN!");
        if (amount > this.#balance) throw new Error("Insufficient balance!");
        this.#balance -= amount;
        return `Withdrew ₹${amount}. New balance: ₹${this.#balance}`;
    }

    // Getter: Controlled read-only access
    get balance() {
        return this.#balance;
    }
}

const account = new BankAccount("Shivam", 5000, 1234);
console.log(account.balance); // 5000 (accessed via getter)
// account.#balance = 100000; // ❌ SyntaxError: Private field '#balance' must be declared in an enclosing class
```

---

### 2. 🧬 Pillar 2: Inheritance
**Concept:** Allows a child class to inherit properties and methods from a parent class via `extends`, adhering to the **DRY (Don't Repeat Yourself)** principle.
- `super()`: Calls the parent constructor. Must be invoked before accessing `this` in child constructor.
- `super.method()`: Calls parent implementation directly.

```javascript
// Inheritance.js (VS Code Format)
class Person {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }

    introduce() {
        return `Hi, I am ${this.name}, ${this.age} years old.`;
    }
}

class Student extends Person {
    constructor(name, age, marks) {
        super(name, age); // Calls Person constructor
        this.marks = marks;
    }

    study() {
        return `${this.name} is studying. Scored: ${this.marks}%.`;
    }
}

const student = new Student("Rahul", 20, 95);
console.log(student.introduce()); // Inherited from Person!
console.log(student.study());     // Defined on Student
```

---

### 3. 🎭 Pillar 3: Polymorphism
**Concept:** "Many forms." Allows different child classes to provide specialized implementations for a method defined with the same name in a parent class (**Method Overriding**).
- **Dynamic Dispatch & Duck Typing:** JavaScript allows iterating over collections of heterogeneous objects and invoking the shared method uniformly.

```javascript
// Polymorphism.js (VS Code Format)
class Animal {
    speak() {
        return "Some generic sound";
    }
}

class Dog extends Animal {
    speak() {
        return "Woof! Woof!"; // Method Overriding
    }
}

class Cat extends Animal {
    speak() {
        return "Meow! Meow!"; // Method Overriding
    }
}

// Polymorphic behavior: Uniform invocation across an array
const animals = [new Dog(), new Cat(), new Animal()];
animals.forEach(a => console.log(a.speak()));
// Output:
// Woof! Woof!
// Meow! Meow!
// Some generic sound
```

---

### 4. 🔍 Pillar 4: Abstraction
**Concept:** Hiding background complexity and showing only essential, clean interfaces to the consumer.
- **Simulating Abstract Classes in JS:** JavaScript does not have an `abstract` keyword, but we enforce it using `new.target === AbstractClass` and throwing errors for unimplemented abstract methods.

```javascript
// AbstractShape.js (VS Code Format)
class Shape {
    constructor() {
        if (new.target === Shape) {
            throw new Error("Cannot instantiate abstract class Shape directly!");
        }
    }

    // Abstract method contract: Must be implemented by subclasses
    calculateArea() {
        throw new Error("Abstract method calculateArea() must be implemented by subclass!");
    }
}

class Circle extends Shape {
    constructor(radius) {
        super();
        this.radius = radius;
    }

    calculateArea() {
        return Math.PI * this.radius * this.radius;
    }
}

// const s = new Shape(); // ❌ Error: Cannot instantiate abstract class Shape directly!
const circle = new Circle(5);
console.log(circle.calculateArea().toFixed(2)); // 78.54
```

---

## ⚡ Additional Essential OOP Concepts

### Static Methods & Properties
Members marked `static` belong to the **class constructor itself**, not instance objects:

```javascript
class MathUtil {
    static PI = 3.14159; // Static property

    static calculateCircumference(radius) { // Static utility method
        return 2 * MathUtil.PI * radius;
    }
}

console.log(MathUtil.PI);                          // 3.14159
console.log(MathUtil.calculateCircumference(10));  // 62.8318
```

### The `instanceof` Operator
Verifies if `Constructor.prototype` appears anywhere in the prototype chain of an instance:

```javascript
class Employee {}
class Manager extends Employee {}

const mgr = new Manager();
console.log(mgr instanceof Manager);  // true
console.log(mgr instanceof Employee); // true (inherited)
console.log(mgr instanceof Object);   // true (root prototype)
```

### Prototypes & Prototype Chaining Under the Hood
In JavaScript, all objects link to a prototype:
$$\text{instance} \xrightarrow{\text{__proto__}} \text{Constructor.prototype} \xrightarrow{\text{__proto__}} \text{Object.prototype} \xrightarrow{\text{__proto__}} \text{null}$$

---

## 📋 4 Pillars Master Summary Table

| Pillar | Core Meaning | JavaScript Mechanism | Primary Benefit |
| :--- | :--- | :--- | :--- |
| **1. Encapsulation** | Data hiding & security | `#privateField`, `#privateMethod()`, `get/set` | Prevents unauthorized state mutation |
| **2. Inheritance** | Code reusability | `class Child extends Parent`, `super()` | Avoids duplicate logic (DRY) |
| **3. Polymorphism** | Many forms of same method | Method overriding & dynamic dispatch | Clean, unified API execution loops |
| **4. Abstraction** | Hiding internal complexity | Public APIs, `new.target === AbstractClass` | Simplifies usage & reduces cognitive load |

---

## 🚀 Quick Links

- [Open Complete OOPs Notes (English) PDF](./OOPs_JS_Handwritten_Notes_English.pdf)
- [Open Complete OOPs Notes (Hinglish) PDF](./OOPs_JS_Handwritten_Notes_Hinglish.pdf)
- [Open Printable English HTML Notes](./OOPs_JS_Notes_English.html)
- [Open Printable Hinglish HTML Notes](./OOPs_JS_Notes_Hinglish.html)
