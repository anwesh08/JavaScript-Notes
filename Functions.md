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