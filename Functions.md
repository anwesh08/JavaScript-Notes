<h1>Functions</h1>

<p>

```java
// Function Statement aka Function Declaration
a();
function a() {
   console.log("a called");
}
```
<code>Output :- </code>
```java
a called
```

- Functions can act like a value.

```java
// Function Expression
b();
var b = function () {
   console.log("b called");
}
```
<code>Output :- </code>
```java
Uncaught TypeError: b is not a function.
```

<<<<<<< HEAD
```java
// Difference Between Function Expression & Function Statement
a();
b();
function a() {
   console.log("a called");
}
var b = function () {
   console.log("b called");
}
```
<code>Output :- </code>
```java
a called
Uncaught TypeError: b is not a function.
```

- Major difference between Function Expression & Function Statement is hoisting.

- Major difference between FE & FS is hoisting. Here in the above example, function a is called (reason: hoisting) but function b throws an error because the function was initialised to a variable "b" and this variable was called before it was initialised.

- Anonymous Function :- Function w/o a name. Doesn't have their own identity. Its looks similar to function statement. Its is used where functions are used as values.

```java
// Anonymous Function 
function () {

}
```
<code>Output :- </code>
```java
Uncaught SyntaxError: function statements require a function name.
```

- Named Function Expression:  Instead of anonymous function, we use a function with a name

```java
// Named Function Expression
function a() {
   console.log("a called");
}
var b = function xyz() {
   console.log("b called");
}
a();
b();
xyz();
```
<code>Output :- </code>
```java
a called
b called
Uncaught ReferenceError: xyz is not defined.
```

- This throws an error because xyz() is only accessible to inner scope and cannot be accessed in the global context. Check the below example.

```java
// Named Function Expression
function a() {
   console.log("a called");
}
var b = function xyz() {
   console.log(xyz);
}
a();
b();
```
<code>Output :- </code>
```java
a called
f xyz(){
   console.log(xyz);
}
```

<b>Difference Between Parameters & Argument</b> :-
- Parameters :- Identifiers/ labels/ local variable present in the parenthesis of the function statement. They get the arguments. 

- Arguments :- Values that are passed inside a function. 

```java
// Difference Between Parameters & Argument 
function a() {
   console.log("a called");
}
var b = function (param1, param2) {
   console.log("b called");
}

a();
b(1, 2);
```

- In the above example, Parameters are param1 & param2 and Arguments are 1 & 2


- <b>First Class Functions</b> :- Function inside functions as an argument. Ability to treat a function as a value, pass it as an argument and return it is known as First class functions.

- This ability makes the functions as "First Class Citizens" in JS

```java
// First Class Functions 
var b = function (param1) {
   console.log(param1);
}
function xyz() {

}
b(xyz);
```
<code>Output :- </code>
```java
f xyz() {}
```

```java
// First Class Functions 
var b = function (param1) {
   console.log(param1);
}
b(function xyz() {});
```
<code>Output :- </code>
```java
f xyz() {}
```

```java
// First Class Functions 
var b = function () {
   return function xyz() {

   }
}

console.log(b());

```
<code>Output :- </code>
```java
f xyz() {}
```

- <b>Arrow Functions</b> :- Introduced in ES6 (Ecma Script).

```java
// Arrow Functions
const b = () => {
   console.log("arrow function")
}
```
</p>
