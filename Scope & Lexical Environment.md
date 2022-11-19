1. Scope is where you can access a specific variable.

2. Lexical Environement is the local memory along with the lexical environment of the parent.

3. Chain of lexical environment is known as scope chain.

<code>Example 1 :-</code>
```java
function a() {
   c();
   function c() {
      console.log(b);
   }
}
var b = 10;
a()
```
<code>Output :-</code>
```java
10
```

<code>Example 2 :-</code>
```java
function a() {
   var b = 10;
   c();
   function c() {
      
   }
}
a();
console.log(b);
```
<code>Output :-</code>
```java
Uncaught ReferenceError: b is not defined.
```