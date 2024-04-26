# Top JavaScript Interview Questions and Answers (2024)

## 1. What is Hoisting in JavaScript?

Hoisting in JavaScript is the behavior by which the declaration of variables and functions are moved to the top. This means that the variable or function declaration need not be done before initializing and calling them.

Hoisting will happen only if `var` is used for declaration and not with `const` or `let` declarations. To avoid hoisting in JavaScript, the strict mode can be used.

#### Example (Variable Hoisting)

Without Hoisting:

```
var num = 5; // num is declared and then initialized
console.log(num); // num is called
```

#### With Hoisting:

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

#### With Hoisting:

```
functionName(); // function is called before declaring it
function functionName() {
  console.log("frontendzip");
}
```
## 2. What are Callbacks in JavaScript?
Callbacks are functions that can be passed as an argument to another function. The callback function can be called from the function to which it was passed (caller) after some event has happened. A common use case of a callback function is to call it after some asynchronous processing has occurred inside the caller function.

```js
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
In the above example, the function '`square`' was a callback function since it was passed as an argument to the `mainFunction` and was executed after that.


