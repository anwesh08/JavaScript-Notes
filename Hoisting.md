<h1>Hoisting in JS</h1>

1. Hoisting in js allows us the access/invoke the function even before it is declared.

<code>Example 1 :-</code>
```java
var x = 7;
function getName() {
   console.log("Namaste Javascript");
}
getName();
console.log(x);
```

<code>Output :-</code>
```java
Namaste Javascript
7
```

2. Not defined is when a variable is not declared whereas undefined is the value initialised to a variable during memory creation phase.

<code>Example 2 :-</code>
```java
getName();
console.log(x);
console.log(getName);
var x = 7;
function getName() {
   console.log("Namaste Javascript");
}
```

<code>Output :-</code>
```java
Namaste Javascript
undefined
f getName() {
   console.log("Namaste Javascript")
}
```

<code>Example 3 :-</code>
```java
getName();
console.log(x);

function getName() {
   console.log("Namaste Javascript");
}
```

<code>Output :-</code>
```java
Namaste Javascript
Uncaught ReferenceError: x is not defined.
```

3. Arrow funciton behaves as a variable. So calling it before defining it gives undefined as output.

<code>Example 4 :-</code>
```java
getName();
console.log(x);
console.log(getName);
var x = 7;
var getName = () => {
   console.log("Namaste Javascript");
}
```

<code>Output :-</code>
```java
Uncaught TypeError: getName is not a function.
```