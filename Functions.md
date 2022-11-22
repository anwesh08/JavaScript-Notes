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
||||||| e57b33c
- Major difference between FE & FS is hoisting.
=======
- Major difference between FE & FS is hoisting. Here in the above example, function a is called (reason: hoisting) but function b throws an error because the function was initialised to a variable "b" and this variable was called before it was initialised.
>>>>>>> 83de085d426651c07e291fa0a3819c24212f9713

- Anonymous Function :- Function w/o a name. Doesn't have their own identity. Its looks similar to function statement. Its is used where functions are used as values.

```java
// Anonymous Function 
function () {

}
```
<code>Output :- </code>
```java
a called
Uncaught SyntaxError: function statements require a function name.
```

```java
// Named Function Expression
```

```java
// Difference Between Parameters & Argument 
```

```java
// First Class Functions 
```

```java
// Arrow Functions
```
</p>
