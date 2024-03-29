<h1>Functions</h1>

<p>

<code>Example :-</code>

```javascript
// Function Statement aka Function Declaration
a();
function a() {
  console.log("a called");
}
```

<code>Output :- </code>

```javascript
a called
```

- Functions can act like a value.

<code>Example :-</code>

```javascript
// Function Expression
b();
var b = function () {
  console.log("b called");
};
```

<code>Output :- </code>

```javascript
Uncaught TypeError: b is not a function.
```

<code>Example :-</code>

```javascript
// Difference Between Function Expression & Function Statement
a();
b();
function a() {
  console.log("a called");
}
var b = function () {
  console.log("b called");
};
```

<code>Output :- </code>

```javascript
a called
Uncaught TypeError: b is not a function.
```

- Major difference between Function Expression & Function Statement is hoisting.

- Major difference between FE & FS is hoisting. Here in the above example, function a is called (reason: hoisting) but function b throws an error because the function was initialised to a variable "b" and this variable was called before it was initialised.

- Anonymous Function :- Function w/o a name. Doesn't have their own identity. Its looks similar to function statement. Its is used where functions are used as values.

<code>Example :-</code>

```javascript
// Anonymous Function
function () {

}
```

<code>Output :- </code>

```javascript
Uncaught SyntaxError: function statements require a function name.
```

- Named Function Expression: Instead of anonymous function, we use a function with a name

<code>Example :-</code>

```javascript
// Named Function Expression
function a() {
  console.log("a called");
}
var b = function xyz() {
  console.log("b called");
};
a();
b();
xyz();
```

<code>Output :- </code>

```javascript
a called
b called
Uncaught ReferenceError: xyz is not defined.
```

- This throws an error because xyz() is only accessible to inner scope and cannot be accessed in the global context. Check the below example.

<code>Example :-</code>

```javascript
// Named Function Expression
function a() {
  console.log("a called");
}
var b = function xyz() {
  console.log(xyz);
};
a();
b();
```

<code>Output :- </code>

```javascript
a called
f xyz(){
   console.log(xyz);
}
```

<b>Difference Between Parameters & Argument</b> :

- Parameters :- Identifiers/ labels/ local variable present in the parenthesis of the function statement. They get the arguments.

- Arguments :- Values that are passed inside a function.

<code>Example :-</code>

```javascript
// Difference Between Parameters & Argument
function a() {
  console.log("a called");
}
var b = function (param1, param2) {
  console.log("b called");
};

a();
b(1, 2);
```

- In the above example, Parameters are param1 & param2 and Arguments are 1 & 2

- <b>First Class Functions</b> :- Function inside functions as an argument. Ability to treat a function as a value, pass it as an argument and return it is known as First class functions.

- This ability makes the functions as "First Class Citizens" in JS

<code>Example :-</code>

```javascript
// First Class Functions
var b = function (param1) {
  console.log(param1);
};
function xyz() {}
b(xyz);
```

<code>Output :- </code>

```java
f xyz() {}
```

<code>Example :-</code>

```javascript
// First Class Functions
var b = function (param1) {
  console.log(param1);
};
b(function xyz() {});
```

<code>Output :- </code>

```java
f xyz() {}
```

```javascript
// First Class Functions
var b = function () {
  return function xyz() {};
};

console.log(b());
```

<code>Output :- </code>

```javascript
f xyz() {}
```

- <b>Arrow Functions</b> :- Introduced in ES6 (Ecma Script).

<code>Example :-</code>

```javascript
// Arrow Functions
const b = () => {
  console.log("arrow function");
};
```

<b>Callback Functions</b> :

- Function that is passed on as argument to another function is called callback function.

<code>Example :-</code>

```javascript
setTimeout(function (), {
   console.log("timer");
}, 5000)
function x() {
   console.log("x");
   y();
}
x(function y() {
   console.log("y");
})
```

<code>Output :- </code>

```javascript
y;
x;
timer;
```

- We can acheive asynchronus operations by using web API's.

- setTimeout does not help to convert from sync to async. setTimeout itself is async operation.

- Event listeners can also invoke closures with scope.

<code>Example :-</code>

```javascript
function attachEventListener() {
  let count = 0;
  document.getElementById("clickMe").addEventListener("click", function xyz() {
    console.log("Button Clicked", ++count);
  });
}
attachEventListener();
```

- Event listeners consume a lot of memory which can potentially slow down the website therefore it is good practice to remove if it is not used.

</p>