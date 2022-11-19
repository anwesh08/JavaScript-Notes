1. <b>Closures</b> :- A function bundled together with its lexical environment.

2. We can pass a function as a parameter during function call. Also we can return a function. It not only returns the function but also returns its lexical scope.

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

3. Closures comes with some corner cases.

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

4. <b>Uses of Closures</b> :- 
      - Module Design Pattern
      - Currying
      - Functions like once
      - Memorize
      - Maintaining state in async world
      - setTimeouts
      - Iterators
      - and many more...

5. 