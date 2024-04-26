# Frontend Zip - Mastering Front-End Job Interviews

1\. What is Hoisting in JavaScript?

Hoisting in JavaScript is the behavior by which the declaration of variables and functions are moved to the top. This means that the variable or function declaration need not be done before initializing and calling them.

Hoisting will happen only if `var` is used for declaration and not with `const` or `let` declarations. To avoid hoisting in JavaScript, the strict mode can be used.

#### Example (Variable Hoisting)

Without Hoisting:

```
var num = 5; // num is declared and then initialized
console.log(num); // num is called
```

With Hoisting:

```
num = 5; // num is initialized
console.log(num); // num is called
var num; // num is declared after initializing it. During execution, this will be moved to the top
```

#### Example (Function Hoisting)

Without Hoisting:

```
function functionName() {
  console.log("frontendzip");
}
functionName(); // function is called after declaring it
```

With Hoisting:

```
functionName(); // function is called before declaring it
function functionName() {
  console.log("frontendzip");
}
```

## 2\. What are Callbacks in JavaScript?

Callbacks are functions that can be passed as an argument to another function. The callback function can be called from the function to which it was passed (caller) after some event has happened. A common use case of a callback function is to call it after some asynchronous processing has occurred inside the caller function.

**Example:**

```
function square(number) {
  console.log(number * number);
}

function mainFunction(callback) {
  const number = 5;
  callback(number);
}

// This function call will print 25
mainFunction(square);
```

In the above example, the function 'square' was a callback function since it was passed as an argument to the `mainFunction` and was executed after that.

## 3\. What are Closures in JavaScript?

Closures in JavaScript refer to the ability of a function to access variables and functions that are lexically outside of its scope. Closures are created whenever new functions are defined and have references to their surrounding state.

**Example:**

```
function welcome() {
  const name = "frontendzip"; // 'name' is a local variable created by 'welcome'

  function displayName() {
    // 'displayName()' is an inner function, a closure
    console.log(name); // It can access the variable declared in the parent function
  }

  displayName();
}

welcome();
```

In the example above, the function `displayName` can access the variable `'name'`, which is declared outside of the function `displayName`. This ability to capture and remember the variables from their containing function's scope is what makes it a closure in JavaScript.

## 4\. What are async functions in JavaScript?

**Async functions** in JavaScript are used to introduce asynchronous, promise-based behavior without the need to explicitly work with Promises. They make it easier to write asynchronous code that appears more like traditional synchronous code.

To create an async function, you use the `async` keyword before the function declaration. Inside the async function, you can use the `await` keyword, which pauses the execution of the function until the promise is resolved or rejected.

Here's an example:

```
function resolveAfter2Seconds() {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve("frontendzip");
    }, 2000);
  });
}

async function asyncCall() {
  const result = await resolveAfter2Seconds();
  console.log(result);
}

asyncCall(); // Calling the async function asyncCall() will output 'frontendzip' after 2 seconds.
```

In this example, the `asyncCall` function contains the `await` expression, which waits for the `resolveAfter2Seconds` promise to resolve before continuing the execution. This makes asynchronous code more readable and easier to work with, especially when dealing with multiple asynchronous operations.

## 5\. What is the purpose of constructors in JavaScript?

Constructor is used in JavaScript to create objects with similar properties and methods. While creating a constructor function, the name of the function should start with a capital letter. The `'new'` keyword is used to create a new object.

```
function Student(name, age, mark) {
  this.name = name;
  this.age = age;
  this.mark = mark;
}

const studentOne = new Student("Elon", 50, 98);
const studentTwo = new Student("Mark", 37, 97);
```

In the above example, the function `Student` is the Constructor function as it is used to create multiple objects of the same properties.

## 6\. Explain equality in JavaScript

JavaScript has both strict and type–converting comparisons:

- **Strict comparison (e.g., ===)** checks for value equality without allowing _coercion_
- **Abstract comparison (e.g. ==)** checks for value equality with _coercion_ allowed

```
var a = "42";
var b = 42;

a == b; // true
a === b; // false
```

Some simple equalityrules:

- If either value (aka side) in a comparison could be the `true` or `false` value, avoid `==` and use `===`.
- If either value in a comparison could be of these specific values (`0`, `""`, or `[]` — empty array), avoid `==` and use `===`.
- In all other cases, you’re safe to use `==`. Not only is it safe, but in many cases it simplifies your code in a way that improves readability.

**Source:** [FullStack.Cafe](https://www.fullstack.cafe/)

## 7\. What is the difference between 'null' and 'undefined' in JavaScript?

In JavaScript, there is a distinction between 'null' and 'undefined' that relates to the state of a variable or value:

**null:**

`null` is a value that can be assigned to a variable intentionally. It represents the intentional absence or lack of a value. When a variable is explicitly set to `null`, it means that the variable is intended to have no value. For example:

```
const x = null;
console.log(x); // null
```

**undefined:**

`undefined` is a primitive value that is automatically assigned to a variable when it is declared but not initialized with a value. It indicates that a variable has been declared, but its value has not been set. For example:

```
let x;
console.log(x); // undefined
```

In summary, 'null' is used to intentionally represent the absence of a value, while 'undefined' is automatically assigned to a variable that has been declared but not initialized. They are both distinct in meaning, and it's essential to understand when and how to use them in your JavaScript code.

## 8\. What are the different data types in JavaScript?

- **Number**: It is a double-precision 64-bit binary format value that can represent any number. There is no concept of int/float in JS. Every number is a 64-bit floating-point number.
      *   _Example_

      ```
  const x = 1;

````


*   **Boolean**: It can have only two values and represents a logical entity. The two values are true and false.

    *   _Example_

    ```
const x = 0;
const y = 1;
const z = 1;
x == y; // returns false
y == z; // returns true
````

- **String**: It is used to represent textual data. It can be represented using a pair of single-quotes or double-quotes.
      *   _Example_

      ```
  const name = "frontendzip";

````


*   **BigInt**: It is used to represent the numbers that are greater than those that can be represented using the Number data type.

    *   _Example_

    ```
const bigInteger = 2234567899876543212345678987654321223;
````

- **Null**: It is used to represent the intentional absence of a variable value.
      *   _Example_

      ```
  const userName = null;

````


*   **Undefined**: The value undefined is assigned to a variable if it has not been initialized. The type of undefined is also undefined.

    *   _Example_

    ```
const userName;
const userAge = undefined;
````

The above data types represent primitive data types. To store any non-primitive data, we have objects in JavaScript. Any kind of data structure that we need to create can be done through objects.

- _Example_

```
const user = {
  name: "Elon",
  age: 50,
  isActive: true,
};

console.log(user.name + " " + user.age + " " + user.isActive); // Elon 50 true
```

## 9\. What is NaN in JavaScript?

**NaN (Not-a-Number)** is a JavaScript property used to represent values that are not proper numbers. NaN is returned by numerical operations where the operation is unable to resolve a numerical value.

**Examples**

```
parseInt("frontendzip");
Math.sqrt(-1);
"frontendzip" / 3;
```

The `isNaN()` function can be used to check whether a value is NaN or not. When using the `isNaN()` function, the value will be first converted to a Number type, and then a check would happen to find out whether it is NaN or not.

**Examples**

```
isNaN(123); // false
isNaN("frontendzip"); // true
isNaN("123"); // false → '123' is converted to Number type (123), and hence it is not NaN
isNaN(undefined); // true
isNaN(true); // false → true corresponds to 1, which is converted to Number type and checked
isNaN(false); // false
```

In summary, NaN is a special value in JavaScript used to indicate that a value is not a valid number, and it is often encountered in situations where an operation or conversion cannot produce a meaningful numeric result.

## 10\. What are `var`, `const`, and `let` keywords in JavaScript?

In JavaScript, `var`, `const`, and `let` are keywords used for declaring variables, but they differ in terms of their scope and mutability:

### **var**:

- **Scope:** `var` variables are function-scoped or globally scoped. This means they are accessible throughout the entire function in which they are declared or in the global scope if declared outside of any function.
- **Reassignment:** `var` variables can be reassigned.
- **Hoisting:** Variables declared with `var` are hoisted to the top of their containing function or the global context. This means that they are processed before the actual code execution, which can sometimes lead to unexpected behavior.

```
function varExample() {
  var x = 10; // Function-scoped variable
  if (true) {
    var x = 20; // This reassigns the outer variable
  }
  console.log(x); // Output: 20
}
varExample();
```

#### **let**:

- **Scope:** `let` variables have block scope, meaning they are only accessible within the block (a pair of curly braces) in which they are declared. This is particularly useful for avoiding variable leakage into outer scopes.
- **Reassignment:** `let` variables can be reassigned after their initial declaration.

```
function letExample() {
  let y = 10; // Block-scoped variable
  if (true) {
    let y = 20; // This creates a new block-scoped variable
  }
  console.log(y); // Output: 10
}
letExample();
```

#### **const**:

- **Scope:** `const` variables also have block scope, just like `let`.
- **Reassignment:** `const` variables, as the name suggests, are constants, and their value cannot be reassigned after the initial assignment. However, it's important to note that if a `const` variable holds an object or array, the properties or elements of the object or array can be modified, but the variable itself cannot be assigned to a different value.
- **Use Case:** `const` is often used when you want to ensure that a variable remains constant throughout its scope. It's a good practice to use `const` by default for variable declarations and only use `let` when you expect the variable's value to change.

```
function constExample() {
  const z = 10; // Block-scoped constant
  if (true) {
    // Attempting to reassign a constant will result in an error
    // z = 20; // This would cause an error
  }
  console.log(z); // Output: 10
}
constExample();
```

In modern JavaScript development, it's recommended to use `const` by default and only use `let` when you know the variable's value will change. This approach helps prevent unintended variable reassignments and makes your code more predictable and less error-prone. It's generally advisable to avoid using `var` in modern JavaScript because of its less predictable scope and hoisting behavior.

## 11\. What is 'strict mode' in JavaScript?

Strict mode can be used to enforce the restricted variant of JavaScript along with non-strict mode code or alone. It can be applied to the entire script or individual functions and won't be applicable to block statements enclosed in { }.

```
"use strict";
const name = "frontendzip";
```

**Example**

```
function user() {
  "use strict";
  console.log("Strict mode");
}
```

## 12\. What are Arrow Functions in JavaScript?

Arrow functions, introduced in ECMAScript 6 (ES6), are a concise way to write functions in JavaScript. They provide a more compact syntax compared to traditional function expressions, making your code cleaner and easier to read. Arrow functions have a few key characteristics:

1.  **Shorter Syntax:** Arrow functions use a compact syntax with the `=>` (fat arrow) operator.
2.  **Implicit Return:** When the function body consists of a single expression, the function automatically returns the result of that expression without needing the `return` keyword.
3.  **No `this` Binding:** Arrow functions do not have their own `this` context. They inherit the `this` value from the containing function or context in which they are defined. This can be advantageous in some cases.

Here's the basic syntax of an arrow function:

```
(parameter1, parameter2, ...) => expression
```

For example, a traditional function that adds two numbers could be written as an arrow function:

```
// Traditional function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

Arrow functions are commonly used for short, simple functions and in scenarios where you want to maintain the outer context's `this` value. However, they are not suitable for all use cases, especially when you need the `this` binding to be dynamic or when working with object methods.

Here's an example demonstrating the usage of an arrow function as a callback:

```
const numbers = [1, 2, 3, 4, 5];
const squared = numbers.map((number) => number * number);
console.log(squared); // [1, 4, 9, 16, 25]
```

Arrow functions have become an essential part of modern JavaScript, making code more concise and readable, especially in functional programming and when working with asynchronous operations.

## 13\. What is Object Destructuring in JavaScript?

Object Destructuring or destructuring assignment is an approach by which the properties from an object or values from an array can be directly unpacked to different variables.

**Example (Without Object Destructuring):**

```
const course = {
    name: 'Introduction to JavaScript',
    isPaid: true,
    cost: {
        amount: 999,
        currency: 'INR'
    };
}
const name = course.name;
const isPaid = course.isPaid;
const cost = course.cost;
console.log(name); // Introduction to JavaScript
console.log(isPaid); // true
console.log(cost); // { amount: 999, currency: 'INR' }
```

**Example (With Object Destructuring):**

```
const course = {
    name: 'Introduction to JavaScript',
    isPaid: true,
    cost: {
        amount: 999,
        currency: 'INR'
    };
}
const { name, isPaid, cost } = course; // destructuring is done here
console.log(name); // Introduction to JavaScript
console.log(isPaid); // true
console.log(cost); // { amount: 999, currency: 'INR' }
```

**Example (With Object Destructuring and having alias for properties):**

```
const course = {
    name: 'Introduction to JavaScript',
    isPaid: true,
    cost: {
        amount: 999,
        currency: 'INR'
    };
}
const { name: courseName, isPaid, cost: courseCost } = course;
console.log(courseName); // Introduction to JavaScript
console.log(isPaid); // true
console.log(courseCost); // { amount: 999, currency: 'INR' }
```

**Example (Partial Object Destructuring):**

```
const course = {
  name: "Introduction to JavaScript",
  website: "frontendzip.com",
  isPaid: true,
  cost: 999,
};
const { name, cost, ...rest } = course;
console.log(name); // Introduction to JavaScript
console.log(cost); // 999
console.log(rest); // { website: 'frontendzip.com', isPaid: true }
```

**Example (Array Destructuring):**

```
const nums = [4, 5, 6, 7];
const [first, second, ...rest] = nums;
console.log(first); // 4
console.log(second); // 5
console.log(rest); // [6, 7]
```

These examples illustrate how object destructuring and array destructuring work in JavaScript. Destructuring can make your code more concise and readable when working with objects and arrays.

## 14\. What is the Spread Syntax or Spread Operator?

The Spread Syntax or Spread Operator is a feature in JavaScript introduced in ECMAScript 6 (ES6) that allows you to spread elements of an iterable (e.g., an array or an object) into another iterable or object literal. It is denoted by three dots (`...`) and can be used in various contexts. The primary purpose of the spread operator is to make it easier to work with collections of data.

Here are some common use cases for the spread operator:

**1\. Arrays:**

- Combining Arrays: You can concatenate two or more arrays together.
- Copying Arrays: Create a shallow copy of an array.
- Adding Elements: Add elements to an existing array without mutating the original.

Example of combining arrays:

```
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combined = [...arr1, ...arr2];
// Result: [1, 2, 3, 4, 5, 6]
```

**2\. Objects:**

- Merging Objects: Combine the properties of multiple objects into a single object.
- Copying Objects: Create a shallow copy of an object.

Example of merging objects:

```
const obj1 = { a: 1, b: 2 };
const obj2 = { b: 3, c: 4 };
const merged = { ...obj1, ...obj2 };
// Result: { a: 1, b: 3, c: 4 }
```

**3\. Function Arguments:**

- You can use the spread operator to pass an array of arguments to a function.

Example of spreading function arguments:

```
function sum(a, b, c) {
  return a + b + c;
}
const numbers = [1, 2, 3];
const result = sum(...numbers);
// Result: 6
```

**4\. Cloning Iterables:**

- You can use the spread operator to clone iterables like arrays or strings.

Example of cloning an array:

```
const originalArray = [1, 2, 3];
const clonedArray = [...originalArray];
// clonedArray is a new array with the same elements as originalArray
```

It's important to note that the spread operator creates shallow copies of objects and arrays. If the iterable being spread contains nested objects or arrays, those nested items will still be references to the same objects in memory. If you need a deep copy, you would need to use additional techniques to achieve that.

The spread operator is a powerful and versatile feature in JavaScript, making it easier to work with data structures and simplifying common operations.

## 15\. What is the Rest Syntax or Rest Operator?

The rest parameter or the rest syntax is opposite to the spread parameter in a way. It collects multiple elements (or arguments)and converts them into a single element. They are used in function declarations, array destructuring, and object destructuring.

It can be used through triple dots `(...)`. The rest should be used as the last parameter of the function or as the last variable while destructuring.

**Example (Function Arguments)**:

```
function myFunction(a, b, ...rest) {
  console.log("a", a);
  console.log("b", b);
  console.log("rest", rest);
}
myFunction("one", "two", "three", "four", "five");
```

**Example (Array Destructuring)**:

```
let numbers = [5, 7, 2, 1, 3];

numbers = [a, b, c, ...rest];
console.log(a); // 5
console.log(b); // 7
console.log(c); // 2
console.log(rest); // [1, 3]
```

**Example (Object Destructuring)**:

```
const obj = {
  firstName: "Elon",
  lastName: "Musk",
  country: "US",
  companies: ["Paypal", "Tesla", "SpaceX"],
};
const { firstName, lastName, ...rest } = obj;
console.log(firstName); // Elon
console.log(lastName); // Musk
console.log(rest); // { 'country': 'US', companies: ['Paypal', 'Tesla', 'SpaceX'] }
```

## 16\. What are Higher-order functions in JavaScript?

Higher-Order Function are functions that can return a function or receive argument or arguments which have a value of a function.

```
function higherOrderFunction(param, callback) {
  return callback(param);
}
```

## 17\. What is the difference between map() and forEach() in JavaScript?

The `forEach()` method iterates over a list (or an array) and carries out some operations on each of the elements.

**Example**

```
const array = [1, 2, 3, 4, 5];
array.forEach((element) => {
  console.log(element);
}); // outputs every element of the array
```

The `map()` method iterates over a list, applies some callback function to each element, and constructs an array from the results. It does not cause any change in the list on which it was called.

**Example**

```
const array = [1, 2, 3, 4, 5];
const map = array.map((element) => element * element);
console.log(map); // outputs the square of each element as a new array
```

An **IIFE** or **Immediately Invoked Function Expression** is a function that is gonna get invoked or executed after its creation or declaration. The syntax for creating IIFE is that we wrap the `function (){}` inside a parentheses `()` or the Grouping Operator to treat the function as an expression and after that we invoke it with another parentheses `()`. So an IIFE looks like this `(function(){})()`.

```
(function () {})();
(function () {})();
(function named(params) {})();
(() => {})();
(function (global) {})(window);
const utility = (function () {
  return {
    //utilities
  };
})();
```

These examples are all valid IIFE. The second to the last example shows we can pass arguments to an IIFE function. The last example shows that we can save the result of the IIFE to a variable so we can reference it later.

The best use of IIFE is making initialization setup functionalities and to avoid naming collisions with other variables in the global scope or polluting the global namespace. Let's have an example.

```
<script src="https://cdnurl.com/somelibrary.js"></script>
```

Suppose we have a link to a library `somelibrary.js` that exposes some global functions that we use can in our code but this library has two methods that we don't use `createGraph` and `drawGraph` because these methods have bugs in them. And we want to implement our own `createGraph` and `drawGraph` methods.

- One way of solving this is by changing the structure of our scripts.

```

<script src="https://cdnurl.com/somelibrary.js"></script>
<script>
  function createGraph() {
    // createGraph logic here
  }
  function drawGraph() {
    // drawGraph logic here
  }
</script>
```

When we use this solution we are overriding those two methods that the library gives us.

- Another way of solving this is by changing the name of our own helper functions.

```

<script src="https://cdnurl.com/somelibrary.js"></script>
<script>
  function myCreateGraph() {
    // createGraph logic here
  }
  function myDrawGraph() {
    // drawGraph logic here
  }
</script>
```

When we use this solution we will also change those function calls to the new function names.

- Another way is using an **IIFE**.

```

<script src="https://cdnurl.com/somelibrary.js"></script>
<script>
  const graphUtility = (function () {
    function createGraph() {
      // createGraph logic here
    }
    function drawGraph() {
      // drawGraph logic here
    }
    return {
      createGraph,
      drawGraph,
    };
  })();
</script>
```

In this solution, we are making a utility variable that is the result of **IIFE** which returns an object that contains two methods `createGraph` and `drawGraph`.

Another problem that **IIFE** solves is in this example.

```
var li = document.querySelectorAll(".list-group > li");
for (var i = 0, len = li.length; i < len; i++) {
  li[i].addEventListener("click", function (e) {
    console.log(i);
  });
}
```

Suppose we have a `ul` element with a class of list-group and it has 5 `li` child elements. And we want to `console.log` the value of `i` when we click an individual `li` element. But the behavior we want in this code does not work. Instead, it logs 5 in any click on an `li` element. The problem we're having is due to how Closures work. Closures are simply the ability of functions to remember the references of variables on its current scope, on its parent function scope and in the global scope. When we declare variables using the `var` keyword in the global scope, obviously we are making a global variable `i`. So when we click an `li` element it logs 5 because that is the value of `i` when we reference it later in the callback function.

- One solution to this is an IIFE.

```
var li = document.querySelectorAll(".list-group > li");
for (var i = 0, len = li.length; i < len; i++) {
  (function (currentIndex) {
    li[currentIndex].addEventListener("click", function (e) {
      console.log(currentIndex);
    });
  })(i);
}
```

This solution works because of the reason that the **IIFE** creates a new scope for every iteration and we capture the value of `i` and pass it into the `currentIndex` parameter so the value of `currentIndex` is different for every iteration when we invoke the **IIFE**.

## 19\. What is the purpose of the 'this' operator in JavaScript?

In JavaScript, the `'this'` keyword inside an object refers to that object itself. It is mainly used in functions and constructors to access the properties and functions of that object.

**Example**

```
class Person {
  constructor(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }
  getFullName() {
    return `${this.firstName} ${this.lastName}`;
  }
}
const person = new Person("Elon", "Musk");
console.log(person.getFullName()); // Elon Musk
```

## 20\. What are Promises in JavaScript?

Promises in JavaScript allow us to defer a set of actions until a particular action is completed. We do not need to wait for the actions to be completed. We can instead defer the further actions to be done only after the prerequisite action has been done.

**Example**

- Start making tea and serve tea after it has been made
- Start making breakfast and serve breakfast after it has been made
- Work

We can write the above set of actions like this:

- `make('tea').then(tea => {serve(tea);});`
- `make('breakfast').then(breakfast => {serve(breakfast);});`
- `work();`

What Promise means is that "I promise to let you know when I'm done". In the above examples, it means "I promise to let you know when making a tea is done.". The consumer can do any action after the promise is fulfilled. Here, the then part will be automatically called once the Promise is completed.

In the above code, we saw how we can add a then block to the promise to handle it on completion. There we looked at only the success scenario. What if the Promise fails. We can send two callbacks to `'then'` (one for success and the other for failure) like this:

```
asyncFunction().then(onSuccess, onError);
```

If we are only interested in the success scenario, we can omit the `onError` callback and directly write:

```
asyncFunction().then(onSuccess);
```

What if we are only interested in handling the error and do not want to handle success scenarios?

We can pass null to `onSuccess` and pass a callback to `onError` like this:

```
asyncFunction().then(null, onError);
```

Not a very clean solution, right?

There is a function in the promise object which acts as an alias to the above:

```
asyncFunction().catch(onError);
```

Note that `catch(onError)` is the same as `then(null, onError)`. You can consider it just an alias.

## 21\. What are events in JavaScript?

In JavaScript, events are actions or occurrences that happen in the browser or in the Document Object Model (DOM), such as a user clicking on a button, a webpage finishing loading, a key being pressed, or the mouse moving over an element. JavaScript allows you to respond to these events by defining functions or event handlers that execute when a specific event occurs. This enables you to create interactive and dynamic web applications.

Here are some key concepts related to events in JavaScript:

1.  Event Types: There are various types of events in JavaScript, such as mouse events (click, hover, etc.), keyboard events (keydown, keyup), form events (submit, change), and document events (DOMContentLoaded, load), among others.
2.  Event Handlers: Event handlers are JavaScript functions that are executed when a specific event occurs. You can attach event handlers to HTML elements or DOM nodes to respond to user interactions.
3.  Event Listener: Event listeners are used to register event handlers. They allow you to listen for specific events on an element and execute a function when the event is triggered.

```
// Example of adding an event listener to a button element
const button = document.getElementById("myButton");
button.addEventListener("click", function () {
  alert("Button clicked!");
});
```

4.  Event Object: When an event occurs, an event object is created. This object contains information about the event, such as the type of event, the target element, mouse coordinates, and other event-specific data. You can access this information within your event handler function.

```
// Example of accessing event object properties
element.addEventListener("click", function (event) {
  console.log(`Event type: ${event.type}`);
  console.log(`Target element: ${event.target}`);
});
```

5.  Event Propagation: Events can propagate through the DOM tree in two phases: capturing phase and bubbling phase. You can use event methods like `stopPropagation()` to control how events propagate.

Events play a fundamental role in building interactive web applications. They enable you to create responsive user interfaces and implement functionality like form validation, user interface animations, and more. JavaScript libraries and frameworks often provide abstractions and utilities for working with events to simplify event handling in complex applications.

## 22\. What are setTimeout and setInterval methods in JavaScript?

In JavaScript, the `setTimeout` method takes a callback function and timer as arguments and invokes the callback once the timer expires. It can be used to execute any logic that needs to be done after a particular time.

**Example**

```
setTimeout(function () {
  console.log("Frontendzip");
}, 2000); // outputs Frontendzip after 2 seconds
```

Similar to `setTimeout`, `setInterval` is also used to execute a function after a delay. The difference here is that the function would be called repeatedly after the mentioned delay.

**Example**

```
setInterval(() => {
  console.log("Frontendzip");
}, 3000); // outputs Frontendzip after every 3 seconds
```

## 23\. What is debouncing and throttling in JavaScript?

Debouncing and throttling are two techniques used in JavaScript to control the rate at which a particular function is executed, especially in response to events like scrolling, resizing, typing, or other potentially frequent triggers. These techniques are useful for optimizing performance and avoiding excessive function calls. Here's an explanation of each:

**Debouncing :**

Debouncing is a technique that ensures a function is only executed after a certain amount of time has passed since the last time the event was triggered. It's especially useful when you want to delay the execution of a function until the user has stopped interacting with a specific element or event.

The idea is to create a delayed or "cooldown" period during which multiple rapid triggers of the event are ignored. This helps in scenarios like autosuggestions in search bars or handling scroll events more efficiently.

_Example of debouncing:_

```
function debounce(func, delay) {
  let timer;
  return function () {
    const context = this;
    const args = arguments;
    clearTimeout(timer);
    timer = setTimeout(function () {
      func.apply(context, args);
    }, delay);
  };
}

const debounceFunction = debounce(someFunction, 300);
```

In this example, `debounceFunction` is a debounced version of `someFunction`. When you call `debounceFunction`, it will execute `someFunction` after a 300ms delay only if there are no new function calls within that time.

**Throttling :**

Throttling is a technique that ensures a function is executed at a maximum rate, typically at a fixed time interval, regardless of how frequently the event is triggered. It limits the execution of a function to a specified rate, preventing it from being called more often than desired.

Throttling is useful when you want to control the rate of execution, such as handling scroll events or ensuring that a button can only be clicked once every few seconds.

_Example of throttling:_

```
function throttle(func, limit) {
  let inThrottle;
  return function () {
    const context = this;
    const args = arguments;
    if (!inThrottle) {
      func.apply(context, args);
      inThrottle = true;
      setTimeout(function () {
        inThrottle = false;
      }, limit);
    }
  };
}

const throttleFunction = throttle(someFunction, 300);
```

In this example, `throttleFunction` is a throttled version of `someFunction`. It will execute `someFunction` at most every 300ms, regardless of how frequently you call `throttleFunction`.

Debouncing and throttling are essential tools for improving the performance and user experience of web applications, ensuring that resource-intensive functions are executed judiciously, and providing a smoother and more responsive interface. Depending on the use case, you may choose either debouncing or throttling to achieve your desired behavior.

## 24\. What is event bubbling in JavaScript?

Assume that an HTML element is present inside another element (parent element) and both of them have their event handlers. In this scenario, if an event happens on the child element, the event handler of the child element will handle it first followed by the event handler of the parent element. This principle is called event bubbling in JavaScript.

**Example**

```
<form onclick="alert('form : parent')">
  form : parent
  <div onclick="alert('div : child of form')">
    div : child of form
    <p onclick="alert('p : child of div')">p : child of div </p>
  </div>
</form>
```

In the above example, if the `p` element is clicked then its event handler will be invoked followed by the handler in `div` followed by the handler in `form`.

## 25\. What are the different scopes in JavaScript?

In JavaScript, scope gives the context about the accessibility of a variable or function in the code. There are three types of scope based on which a function or a variable can be accessed. They are:

**1\. Global Scope**  
**2\. Function/Local Scope**  
**3\. Block Scope**

### Global Scope

The variables or functions that are declared in the global scope can be accessed anywhere in the code.

```
const name = 'frontendzip';
function printName() {
    console.log(name);
}
printName();    // outputs frontendzip
```

### Function/Local Scope

The variables or functions that are defined in the function/local scope can be accessed only within that function and not outside it.

```
function printName() {
  const name = 'frontendzip';
  console.log(name);    // outputs frontendzip
}

console.log(name);    // throws an error as the variable name cannot be accessed outside the function
```

### Block Scope

The variables that are defined using let and const inside a `{ }` (block) cannot be accessed outside that block. Block scope is not applicable for the variables defined using var.

```
let x = 5;
if(x === 5) {
    const a = x;
    console.log(a);    // outputs 5
}

console.log(a);    // throws an error
```
