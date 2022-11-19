<h1>Closures</h1>
<p>

- <b>Closures</b> means functions bundled together with its lexical environment.

- We can pass a function as a parameter during function call. Also we can return a function. It not only returns the function but also returns its lexical scope.

<code>Example :-</code>
```java
function x() {
   var a = 7;
   return function y() {
      console.log(a);
   }
   return y;
}
var z = x();
console.log(z);
z();
```
<code>Output :-</code>
```java
f y() {
   console.log(a);
}
7
```

- Closures comes with some corner cases.

<code>Example :-</code>
```java
function x() {
   var a = 7;
   return function y() {
      console.log(a);
   }
   a = 100
   return y;
}
var z = x();
console.log(z);
z();
```
<code>Output :-</code>
```java
f y() {
   console.log(a);
}
100
```
<code>Example :-</code>
```java
function z() {
   var b = 900;
   function x() {
      var a = 7;
      return function y() {
         console.log(a, b);
      }
      y();
   }
   x();
}
z();
```
<code>Output :-</code>
```java
7, 900
```

- <b>Uses of Closures</b> :- 
      - Module Design Pattern
      - Currying
      - Functions like once
      - Memorize
      - Maintaining state in async world
      - setTimeouts
      - Iterators
      - and many more...

- 
</p>