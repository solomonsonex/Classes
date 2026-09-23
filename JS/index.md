# JavaScript Tutorial

Welcome to this beginner-friendly JavaScript tutorial. JavaScript is the programming language used to make web pages interactive. It can change content, respond to clicks, validate forms, animate elements, and much more.

> **Learning approach:** Read a concept, try the example, change a few values, and run it in the browser to see what happens.

## What you will learn

By the end of this tutorial, you should be able to:

- Understand what JavaScript is and why it is used.
- Write JavaScript in the browser and in scripts.
- Work with variables, data types, and operators.
- Use conditionals and loops.
- Create functions and understand scope.
- Work with arrays and objects.
- Manipulate the DOM.
- Add events and interactivity to webpages.
- Use simple debugging and error-handling techniques.

## 1. What is JavaScript?

JavaScript is a scripting language used to make websites dynamic and interactive. It runs in the browser and can modify HTML and CSS after the page loads.

Example:

```html
<button onclick="alert('Hello!')">Click me</button>
```

This is a simple example of JavaScript responding to a click event.

## 2. Adding JavaScript to HTML

There are three main ways to add JavaScript to a webpage.

### Inline JavaScript

Inline JavaScript is written directly in an HTML attribute.

```html
<button onclick="document.body.style.backgroundColor = 'lightblue';">Change color</button>
```

### Internal JavaScript

Internal JavaScript is written inside a `<script>` tag in the HTML document.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Internal JS</title>
</head>
<body>
  <h1>My Page</h1>
  <script>
    alert('Welcome to my page!');
  </script>
</body>
</html>
```

### External JavaScript

External JavaScript is stored in a separate `.js` file. This is the recommended approach for most projects.

**HTML file**

```html
<script src="script.js"></script>
```

**script.js**

```javascript
console.log('Hello from an external file!');
```

## 3. JavaScript syntax

JavaScript follows rules of syntax. A statement is a complete instruction.

```javascript
console.log("Hello, world!");
```

Semicolons are optional in many cases, but they are often used for clarity.

```javascript
let message = "Hello";
console.log(message);
```

## 4. Variables

Variables store data values.

```javascript
let name = "Alice";
const age = 20;
var city = "Nairobi";
```

### `let`

Used when the value may change.

```javascript
let score = 10;
score = 15;
```

### `const`

Used when the value should not change.

```javascript
const pi = 3.14159;
```

### `var`

Older way to declare variables. It is less preferred in modern JavaScript.

```javascript
var year = 2025;
```

## 5. Data types

JavaScript has several basic data types:

```javascript
let text = "Hello";       // string
let number = 42;           // number
let isActive = true;       // boolean
let empty = null;          // null
let notDefined;            // undefined
let person = { name: "Ann" }; // object
let fruits = ["apple", "mango"]; // array
```

## 6. Operators

Operators perform operations on values.

### Arithmetic operators

```javascript
let a = 10;
let b = 3;

console.log(a + b); // 13
console.log(a - b); // 7
console.log(a * b); // 30
console.log(a / b); // 3.333...
console.log(a % b); // 1
```

### Comparison operators

```javascript
console.log(5 > 3); // true
console.log(5 === 5); // true
console.log(4 !== 5); // true
```

### Logical operators

```javascript
let hasAccess = true;
let isStudent = true;

console.log(hasAccess && isStudent); // true
console.log(hasAccess || isStudent); // true
console.log(!hasAccess); // false
```

## 7. Strings

Strings hold text data.

```javascript
let greeting = "Hello";
let name = "Mary";

console.log(greeting + " " + name); // Hello Mary
console.log(`${greeting} ${name}`); // Hello Mary
```

Common string methods:

```javascript
let text = "JavaScript";

console.log(text.length); // 10
console.log(text.toUpperCase()); // JAVASCRIPT
console.log(text.toLowerCase()); // javascript
console.log(text.substring(0, 4)); // Java
```

## 8. Numbers and math

```javascript
let x = 10;
let y = 3;

console.log(Math.max(x, y)); // 10
console.log(Math.min(x, y)); // 3
console.log(Math.round(4.7)); // 5
console.log(Math.random()); // random number between 0 and 1
```

## 9. Conditionals

Conditionals let the program decide what to do.

```javascript
let score = 75;

if (score >= 80) {
  console.log("Excellent!");
} else if (score >= 50) {
  console.log("Good job!");
} else {
  console.log("Keep practicing!");");
}
```

### Switch statement

```javascript
let day = "Monday";

switch (day) {
  case "Monday":
    console.log("Start of the week");
    break;
  case "Friday":
    console.log("Weekend is near");
    break;
  default:
    console.log("Another day");
}
```

## 10. Loops

Loops run code multiple times.

### For loop

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

### While loop

```javascript
let count = 0;

while (count < 5) {
  console.log(count);
  count++;
}
```

### For...of loop

```javascript
let colors = ["red", "green", "blue"];

for (let color of colors) {
  console.log(color);
}
```

## 11. Functions

Functions are reusable blocks of code.

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet("Alice"));
console.log(greet("Sam"));
```

### Function expressions

```javascript
const add = function(a, b) {
  return a + b;
};

console.log(add(3, 5));
```

### Arrow functions

```javascript
const multiply = (a, b) => a * b;
console.log(multiply(4, 6));
```

## 12. Arrays

Arrays store multiple values in one variable.

```javascript
let fruits = ["apple", "banana", "orange"];

console.log(fruits[0]); // apple
console.log(fruits.length); // 3

fruits.push("mango");
console.log(fruits); // ["apple", "banana", "orange", "mango"]
```

Common array methods:

```javascript
let numbers = [1, 2, 3, 4];

console.log(numbers.pop()); // 4
console.log(numbers.shift()); // 1
console.log(numbers.includes(2)); // true
```

## 13. Objects

Objects store data as key-value pairs.

```javascript
const student = {
  name: "Jane",
  age: 18,
  class: "Grade 10"
};

console.log(student.name); // Jane
console.log(student["age"]); // 18
```

You can also add or change object properties:

```javascript
student.grade = "A";
student.age = 19;
```

## 14. DOM (Document Object Model)

The DOM represents the HTML of a page. JavaScript can access and change the DOM.

```html
<p id="demo">Hello</p>
```

```javascript
const element = document.getElementById("demo");
element.textContent = "Goodbye";
```

### Changing styles

```javascript
document.getElementById("demo").style.color = "blue";
document.getElementById("demo").style.fontSize = "24px";
```

### Adding an event listener

```html
<button id="btn">Click me</button>
```

```javascript
const btn = document.getElementById("btn");

btn.addEventListener("click", function() {
  alert("Button clicked!");
});
```

## 15. Events

Events happen when a user interacts with a page.

Common events:

- `click`
- `mouseover`
- `keydown`
- `submit`
- `change`

Example:

```html
<button id="messageBtn">Show Message</button>
<script>
  document.getElementById("messageBtn").addEventListener("click", function() {
    alert("You clicked the button!");
  });
</script>
```

## 16. JavaScript and forms

JavaScript is often used to validate form inputs.

```html
<form id="signupForm">
  <input type="text" id="name" placeholder="Enter your name">
  <button type="submit">Submit</button>
</form>

<script>
  document.getElementById("signupForm").addEventListener("submit", function(event) {
    event.preventDefault();
    const name = document.getElementById("name").value;
    alert("Welcome, " + name + "!");
  });
</script>
```

## 17. Scope

Scope determines where variables are available.

```javascript
let globalVariable = "I am global";

function testScope() {
  let localVariable = "I am local";
  console.log(globalVariable);
  console.log(localVariable);
}

testScope();
```

`globalVariable` can be used anywhere, but `localVariable` only exists inside the function.

## 18. Error handling

JavaScript can catch errors with `try` and `catch`.

```javascript
try {
  console.log(unknownVariable);
} catch (error) {
  console.log("An error occurred:", error.message);
}
```

This helps keep the code from crashing unexpectedly.

## 19. Basic practice example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JavaScript Example</title>
</head>
<body>
  <h2>Counter</h2>
  <p id="count">0</p>
  <button id="incrementBtn">Increase</button>

  <script>
    let count = 0;
    const countText = document.getElementById("count");
    const button = document.getElementById("incrementBtn");

    button.addEventListener("click", function() {
      count++;
      countText.textContent = count;
    });
  </script>
</body>
</html>
```

This small example shows how JavaScript can update the DOM in response to a button click.

## Practice exercises

1. Create a greeting page that asks for a name and displays a welcome message.
2. Write a function that calculates the area of a rectangle.
3. Make a button that changes the background color of the page.
4. Use a loop to print numbers from 1 to 10.
5. Build a simple to-do list with add and remove buttons.
6. Validate a form so it cannot be submitted empty.
7. Create an array of students and display each name in the page.

## Quick reference

| Topic | Example |
| --- | --- |
| Variable | `let name = "Alice";` |
| Constant | `const pi = 3.14;` |
| Function | `function greet(name) { return name; }` |
| Array | `let colors = ["red", "blue"];` |
| Object | `let person = { name: "Ken" };` |
| Condition | `if (score > 50) { ... }` |
| Loop | `for (let i = 0; i < 5; i++) { ... }` |
| Event | `button.addEventListener("click", ...)` |
| DOM update | `element.textContent = "New text";` |

## Good JavaScript habits

- Use `const` for values that should not change.
- Use `let` for values that may change.
- Keep code readable and well-named.
- Use comments to explain important logic.
- Test code in the browser console.
- Avoid using `var` unless you must support older code.
- Break problems into small functions.
- Use event listeners instead of inline HTML events when possible.

## Summary

JavaScript makes web pages interactive and dynamic. Once you understand variables, functions, conditionals, loops, arrays, and the DOM, you can build engaging and useful web experiences.

Keep practicing, try small examples, and remember: every JavaScript project starts with a simple problem and a few lines of code.
