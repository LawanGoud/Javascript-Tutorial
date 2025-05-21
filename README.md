# Javascript-Tutorial

Got it! We'll take it step by step with the topics you give, and I won’t introduce anything new until you’re ready. Let’s start with the first topic you gave:

---

## 1. Variables

### What is a Variable?

A **variable** in JavaScript is like a container that stores data values. You can think of it as a labeled box where you keep some information and use it later.

### Variable Declaration and Assigning a Value

To create (declare) a variable, you use the keyword **`let`** (or `var` / `const`, but let's keep it simple with `let` for now). Then, you assign a value to it with the **assignment operator `=`**.

Example:

```javascript
let age; // Declare a variable named 'age'
age = 25; // Assign the value 25 to the variable 'age'

let name = "Alice"; // Declare and assign a value at the same time
```

Here:

- `let age;` declares a variable but doesn’t give it a value yet.
- `age = 25;` assigns the value 25 to `age`.
- `let name = "Alice";` declares and assigns the value `"Alice"` in one line.

---

Great! Moving on to:

---

## 2. DOM Object Model (DOM)

### What is the DOM?

The **DOM (Document Object Model)** is a programming interface for HTML documents. It represents the page so that programs can change the document structure, style, and content.

Think of the DOM as a **tree** where each element (like a paragraph, div, button) is a **node** (a box on the tree). JavaScript can access and manipulate these nodes.

---

### Document Object

The **`document`** object represents the entire HTML page loaded in the browser. You use it to get or change elements on the page.

Example:

```javascript
console.log(document); // Logs the entire document object to the console
```

---

### HTML DOM Tree

Every HTML element on the page is a **node** in the DOM tree. For example, an HTML like:

```html
<body>
  <h1>Hello</h1>
  <p>Welcome to JavaScript!</p>
</body>
```

is represented in the DOM as a tree structure:

- document

  - html

    - body

      - h1
      - p

---

### Methods

#### `textContent`

- This gets or sets the text inside an element.

Example:

```html
<p id="demo">Old Text</p>
<script>
  let para = document.getElementById("demo");
  console.log(para.textContent); // Outputs: Old Text

  para.textContent = "New Text"; // Changes the paragraph text
</script>
```

#### `style`

- This lets you change the CSS styles of an element directly through JavaScript.

Example:

```html
<p id="demo" style="color: blue;">This text is blue.</p>
<script>
  let para = document.getElementById("demo");
  para.style.color = "red"; // Changes the text color to red
</script>
```

---

### Events

#### `onclick` Event

- This event triggers a function when an element is clicked.

Example:

```html
<button id="btn">Click Me</button>
<script>
  let button = document.getElementById("btn");
  button.onclick = function () {
    alert("Button clicked!");
  };
</script>
```

---

Perfect! You’ve shared the **HTML** and **CSS** for a switch that shows a bulb and a cat image with ON and OFF buttons. Now, we’ll use **JavaScript** to make the ON and OFF buttons actually work using the concepts we just learned:

- `document.getElementById()`
- `textContent`
- `style`
- `onclick` event

---

### ✅ Add JavaScript: `switchOn()` and `switchOff()` Functions

Let’s write the JavaScript code you need to turn the switch ON and OFF:

```html
<script>
  function switchOff() {
    // Change bulb image to OFF
    document.getElementById("bulbImage").src =
      "https://d1tgh8fmlzexmh.cloudfront.net/ccbp-dynamic-webapps/bulb-go-off-img.png";

    // Change cat image
    document.getElementById("catImage").src =
      "https://d1tgh8fmlzexmh.cloudfront.net/ccbp-dynamic-webapps/cat-img.png";

    // Change text to "Switched Off"
    document.getElementById("switchStatus").textContent = "Switched Off";

    // Optional: Change background color of switch board
    document.querySelector(".switch-board").style.backgroundColor = "#0b0b0b";
  }

  function switchOn() {
    // Change bulb image to ON
    document.getElementById("bulbImage").src =
      "https://d1tgh8fmlzexmh.cloudfront.net/ccbp-dynamic-webapps/bulb-go-on-img.png";

    // Change cat image
    document.getElementById("catImage").src =
      "https://d1tgh8fmlzexmh.cloudfront.net/ccbp-dynamic-webapps/cat-img.png";

    // Change text to "Switched On"
    document.getElementById("switchStatus").textContent = "Switched On";

    // Optional: Restore background color of switch board
    document.querySelector(".switch-board").style.backgroundColor = "#7b8794";
  }
</script>
```

---

### 🧠 Breakdown:

- `document.getElementById("bulbImage").src = ...`
  → Changes the **bulb image**.

- `textContent`
  → Updates the **status text** (e.g., from "Switched On" to "Switched Off").

- `style.backgroundColor`
  → Changes the background color of the switch panel for visual feedback.

- `onclick="switchOn()"` and `onclick="switchOff()"`
  → These run the corresponding functions when the user clicks the buttons.

---

You can place this `<script>` block either **at the end of your `<body>`** or inside a `<script>` tag before the `</body>` tag to ensure the HTML is loaded before JavaScript runs.

Perfect, let’s continue as per your list — clear, focused, and step by step.

---

## 1. JavaScript Values

### 🔹 Primitive Values

**Primitive values** are simple data types. They are stored directly in memory and are **immutable** (can’t be changed).

Here are the most common primitive types in JavaScript:

| Type      | Example             |
| --------- | ------------------- |
| Number    | `5`, `3.14`, `-10`  |
| String    | `"hello"`, `'abc'`  |
| Boolean   | `true`, `false`     |
| Null      | `null`              |
| Undefined | `undefined`         |
| Symbol    | `Symbol("id")`      |
| BigInt    | `9007199254740991n` |

✅ **Example:**

```javascript
let age = 25; // Number
let name = "Alice"; // String
let isOn = true; // Boolean
let nothing = null; // Null
let x; // Undefined (no value assigned)
```

---

### 🔹 Reference Types

Reference types **store a reference (address)** to a value in memory. These include:

- **Objects**
- **Arrays**
- **Functions**

✅ **Example:**

```javascript
let person = { name: "Bob", age: 30 }; // Object
let colors = ["red", "green", "blue"]; // Array
function greet() {
  console.log("Hello");
} // Function
```

Difference:

- Primitive = value stored directly
- Reference = points to where the value is stored

---

## 2. Operators

### `typeof()` Operator

The `typeof` operator tells you the **type of a value**.

✅ **Examples:**

```javascript
console.log(typeof 123); // "number"
console.log(typeof "hello"); // "string"
console.log(typeof true); // "boolean"
console.log(typeof null); // "object" (this is a known JS quirk)
console.log(typeof undefined); // "undefined"
console.log(typeof [1, 2, 3]); // "object"
console.log(typeof function () {}); // "function"
```

---

## 3. Converting String to a Number

Sometimes you get numbers in **string** form and need to convert them.

✅ **Methods:**

### `Number()`

```javascript
let str = "42";
let num = Number(str); // 42
```

### `parseInt()` and `parseFloat()`

```javascript
let intVal = parseInt("42"); // 42
let floatVal = parseFloat("42.5"); // 42.5
```

### Unary `+` (quick trick)

```javascript
let n = +"123"; // 123
```

---

## 4. Conditional Statements

Used to run different code based on conditions.

### `if`, `else if`, `else`

✅ **Example:**

```javascript
let age = 20;

if (age < 18) {
  console.log("Minor");
} else if (age >= 18 && age < 65) {
  console.log("Adult");
} else {
  console.log("Senior");
}
```

### Ternary Operator (short form)

```javascript
let status = age >= 18 ? "Adult" : "Minor";
console.log(status);
```

---

Awesome! You’ve got the HTML and CSS ready for a **Counter App** with **INCREASE**, **DECREASE**, and **RESET** buttons.

Let’s now add the **JavaScript logic** to:

- Track the counter value (using variables)
- Update the DOM using `textContent`
- Handle button clicks (`onclick` events)
- Use **conditional logic** if needed (e.g., stop at zero or limit range)

---

## ✅ JavaScript Code to Add

Add this inside a `<script>` tag just **before the closing `</body>` tag** in your HTML:

```html
<script>
  // Declare the variable to store the counter value
  let counter = 0;

  // Reference to the <p> element that displays the value
  let counterElement = document.getElementById("counterValue");

  function onIncrement() {
    counter = counter + 1; // or counter += 1;
    counterElement.textContent = counter;
  }

  function onDecrement() {
    counter = counter - 1; // or counter -= 1;
    counterElement.textContent = counter;
  }

  function onReset() {
    counter = 0;
    counterElement.textContent = counter;
  }
</script>
```

---

### 🔍 Breakdown of Concepts Used:

| Concept            | Explanation                       |
| ------------------ | --------------------------------- |
| `let counter = 0;` | Declares and initializes a number |
| `getElementById()` | Gets the `<p id="counterValue">`  |
| `textContent`      | Updates the number on the screen  |
| `onclick`          | Runs the right function on click  |

---

Excellent! Let’s break down the next set of concepts **one by one** with clear examples, and in the order you asked:

---

## ✅ Math Functions

### 🔹 `Math.random()`

Generates a **random number between 0 (inclusive) and 1 (exclusive)**.

```javascript
let randomNum = Math.random();
console.log(randomNum); // Example: 0.5392...
```

#### Random number between 1 and 10:

```javascript
let random1to10 = Math.floor(Math.random() * 10) + 1;
```

---

### 🔹 `Math.ceil()`

Rounds a number **up to the nearest integer**.

```javascript
let value = 4.2;
console.log(Math.ceil(value)); // Output: 5
```

---

## ✅ HTML Input Elements

### 🔹 Text Input

```html
<input type="text" id="username" />
```

### 🔹 Password Input

```html
<input type="password" id="password" />
```

These elements let users enter text and passwords. We'll use **`.value`** to access what the user typed.

---

## ✅ DOM Property: `value`

Used to get or set the value of an `<input>` element.

### Example:

```html
<input type="text" id="usernameInput" />
<button onclick="showUsername()">Show Username</button>

<script>
  function showUsername() {
    let inputElement = document.getElementById("usernameInput");
    let username = inputElement.value;
    alert("Entered username: " + username);
  }
</script>
```

---

## ✅ Comparison Operators

### 🔹 `==` (Loose Equality)

- **Compares values**, but allows **type conversion**.

```javascript
console.log("5" == 5); // true (string gets converted to number)
```

### 🔹 `===` (Strict Equality)

- Compares **both value and type**. No type conversion.

```javascript
console.log("5" === 5); // false (string !== number)
console.log(5 === 5); // true
```

Use `===` for **safer, more predictable comparisons**.

---

## ✅ Quick Mini Example (All Concepts Combined)

```html
<input type="text" id="inputNumber" />
<button onclick="showRandomCeil()">Show Random & Ceil</button>

<script>
  function showRandomCeil() {
    let inputVal = document.getElementById("inputNumber").value;

    // Convert string to number
    let number = Number(inputVal);

    // Generate random number between 0 and the input
    let randomNum = Math.random() * number;
    let ceilNum = Math.ceil(randomNum);

    alert("Random: " + randomNum + ", Ceil: " + ceilNum);
  }
</script>
```

---

Great! You’ve built a solid HTML and CSS layout for a **"Guess The Number"** game. Now, let’s add the **JavaScript logic** to complete the functionality using the concepts you’re learning:

---

## ✅ JavaScript to Add (Place before `</body>`)

```html
<script>
  // Step 1: Generate a random number between 1 and 100
  let correctNumber = Math.ceil(Math.random() * 100);

  function checkGuess() {
    // Step 2: Get user input from the input box
    let userInputElement = document.getElementById("userInput");
    let userGuess = userInputElement.value;

    // Step 3: Convert string to number
    let guessedNumber = parseInt(userGuess);

    // Step 4: Get the result element
    let resultElement = document.getElementById("gameResult");

    // Step 5: Compare the guess and show the result
    if (isNaN(guessedNumber)) {
      resultElement.textContent = "Please enter a valid number.";
    } else if (guessedNumber > correctNumber) {
      resultElement.textContent = "Too High! Try a smaller number.";
    } else if (guessedNumber < correctNumber) {
      resultElement.textContent = "Too Low! Try a bigger number.";
    } else if (guessedNumber === correctNumber) {
      resultElement.textContent = "🎉 Congratulations! You guessed it right.";
    }
  }
</script>
```

---

## ✅ Concepts Used in This Example

| Concept               | Usage                                  |
| --------------------- | -------------------------------------- |
| `Math.random()`       | To generate a number between 0 and 1   |
| `Math.ceil()`         | To ensure the random number is 1–100   |
| `input` + `.value`    | To get user input                      |
| `parseInt()`          | Convert string to number               |
| `===` strict equality | To compare number & type accurately    |
| `textContent`         | To update result on the page           |
| `onclick`             | To trigger guess check on button click |

---

Would you like to add features like:

- Reset button
- Limit number of guesses
- Display number after win/loss

Or should we move on to your next JavaScript topics?

Excellent — let’s now walk through each of the next topics with **clear explanations and examples** in the order you listed:

---

## ✅ 1. Data Structures

In JavaScript, a **data structure** is a way to organize and store data.
Common types include:

- Arrays
- Objects
- Maps
- Sets

We’ll focus on **arrays** next.

---

## ✅ 2. Arrays

### 🔹 a. Creating an Array

```javascript
let fruits = ["apple", "banana", "cherry"];
```

### 🔹 b. Accessing an Array Item

```javascript
console.log(fruits[0]); // Output: "apple"
console.log(fruits[2]); // Output: "cherry"
```

### 🔹 c. Modifying an Array Item

```javascript
fruits[1] = "orange";
console.log(fruits); // ["apple", "orange", "cherry"]
```

### 🔹 d. Finding Array Length

```javascript
console.log(fruits.length); // Output: 3
```

### 🔹 e. Array Methods

#### `push()` – Adds to the end

```javascript
fruits.push("grape");
console.log(fruits); // ["apple", "orange", "cherry", "grape"]
```

#### `pop()` – Removes from the end

```javascript
fruits.pop();
console.log(fruits); // ["apple", "orange", "cherry"]
```

---

## ✅ 3. Functions

### 🔹 a. Function Declaration

```javascript
function greet(name) {
  console.log("Hello, " + name + "!");
}

greet("Alice"); // Output: Hello, Alice!
```

### 🔹 b. Function Expression

```javascript
let greetUser = function (name) {
  console.log("Hi, " + name + "!");
};

greetUser("Bob"); // Output: Hi, Bob!
```

---

## ✅ 4. More DOM Manipulations

### 🔹 a. `createElement()`

Used to **create a new HTML element**.

```javascript
let newDiv = document.createElement("div");
```

### 🔹 b. `appendChild()`

Used to **add the new element** to the DOM.

```javascript
let container = document.getElementById("mainContainer");
container.appendChild(newDiv);
```

### 🔹 c. Adding Event Listeners Dynamically

```javascript
let button = document.createElement("button");
button.textContent = "Click Me";

button.addEventListener("click", function () {
  alert("Button clicked!");
});

document.body.appendChild(button);
```

### 🔹 d. `classList.add()`

Adds a CSS class dynamically.

```javascript
newDiv.classList.add("highlight");
```

### 🔹 e. `classList.remove()`

Removes a class dynamically.

```javascript
newDiv.classList.remove("highlight");
```

---

## ✅ Mini Example (Putting DOM methods together)

```html
<div id="mainContainer"></div>
```

```javascript
let newButton = document.createElement("button");
newButton.textContent = "Click Me";
newButton.classList.add("btn", "btn-primary");

newButton.addEventListener("click", function () {
  newButton.classList.remove("btn-primary");
  newButton.classList.add("btn-danger");
  alert("Style changed!");
});

document.getElementById("mainContainer").appendChild(newButton);
```

---

Great! Let’s now learn about **JavaScript Objects** with structured explanations and examples for everything you've listed.

---

## ✅ Object in JavaScript

An **object** is a collection of **key-value pairs**. It is used to store related data and functionality.

---

### 🔹 1. Creating an Object

An object is created using `{}` (curly braces).
Each key (called a property) is a **string identifier**, and values can be of any type.

```javascript
let person = {
  name: "Alice",
  age: 25,
  isStudent: false,
};
```

#### ✔ Identifiers (Keys)

- Must be valid strings.
- Usually follow variable naming rules.
- Can be quoted (`"name"`) or unquoted (`name`).

---

### 🔹 2. Accessing Object Properties

#### ✔ Dot Notation

```javascript
console.log(person.name); // "Alice"
```

#### ✔ Bracket Notation

```javascript
console.log(person["age"]); // 25
```

#### ✔ Accessing Non-existent Properties

```javascript
console.log(person.height); // undefined
```

#### ✔ Variables as a Key

```javascript
let key = "name";
console.log(person[key]); // "Alice"
```

#### ✔ Object Destructuring

You can **extract properties** into variables.

```javascript
let { name, age } = person;
console.log(name); // "Alice"
console.log(age); // 25
```

---

### 🔹 3. Modifying Objects

#### ✔ Modifying Object Property

```javascript
person.age = 30;
console.log(person.age); // 30
```

#### ✔ Adding New Object Property

```javascript
person.city = "New York";
console.log(person.city); // "New York"
```

---

### 🔹 4. Property Value Types

#### ✔ Property as Function

```javascript
let user = {
  greet: function () {
    console.log("Hello!");
  },
};

user.greet(); // Output: Hello!
```

#### ✔ Property as Array

```javascript
let student = {
  scores: [85, 90, 95],
};

console.log(student.scores[1]); // 90
```

#### ✔ Property as Another Object

```javascript
let company = {
  name: "Tech Corp",
  location: {
    city: "San Francisco",
    country: "USA",
  },
};

console.log(company.location.city); // "San Francisco"
```

---

## ✅ Summary

| Action                        | Example                      |
| ----------------------------- | ---------------------------- |
| Create object                 | `let obj = { key: value }`   |
| Access via dot notation       | `obj.key`                    |
| Access via bracket notation   | `obj["key"]`                 |
| Destructure                   | `let { key } = obj`          |
| Modify property               | `obj.key = newValue`         |
| Add new property              | `obj.newKey = value`         |
| Use function as property      | `obj.method = function() {}` |
| Nest object/array in property | `obj.key = [1, 2] / {}`      |

---

Would you like a small **coding exercise** on objects? Or should we move to the next topic?
