<h1>Handy JS Notes</h1>

1. Everything in JS happens inside an <b><i>Execution Context</i></b>.

2. Exceution Context :-
     Its consists of two compoenents :- <br>
     <p>
        i) <b>Memory Component</b> :- Also known as Variable Environment. Its stores variables and functions as key : value pairs.
              <br>
        ii) <b>Code Component</b> :- Also known as Thread of Execution. Where the code is executed line by line.
     </p>

3. JS is a synchronus single-threaded language.

4. When we run a code a global execution context is created. Execution context is created in two phases :-
<br>
     i) <b>Memory Creation Phase</b> : It allocates memory to different variables & functions. For vaiables it stores undefined while for function its stores the code.
        <br>
     ii) <b>Code Execution Phase</b> : Runs through the whole js program line by line. Here the value of variables are assigned in memory.

5. Everytime a funtion is called it creates a execution context.

6. Return keyword tells the function to return the control back where it is invoked.

7. Whole execution context will be deleted after execution of a function or program.

8. Js manages all the execution context using call stack and global execution context is at the bottom of the stack.

9. Call stack maintains the order of execution contexts.

10. Hoisting in js allows us the access/invoke the function even before it is declared.

11. Not defined is when a variable is not declared whereas undefined is the value initialised to a variable during memory creation phase.

12. Arrow funciton behaves as a variable. So calling it before defining it gives undefined as output.

13. The same variable defined in different scopes will act as different variables even if it has same name.

14. Js engines searches the value of variable in the local memory of particular execution context which is being executed.

15. Every execution context have there own memory space.

16. Even if the js file have no code js engine creates a global execution context. So the smallest js program is an empty js file.

17. Window is a global object and collection of functions.

18. It is not a good practice to assign undefined to any variable.

19. Scope is where you can access a specific variable.

20. Lexical Environement is the local memory along with the lexical environment of the parent.

21. Chain of lexical environment is known as scope chain.

22. let & const declarations are Hoisted.

23. const and let are hoisted in different memory space.

24. <b>Temporal Dead Zone</b> :- Time between a variable is declared and initialized (From hoisting till it is assigned a value).

25. <b>3 types of Error</b> :- Reference Error, Type Error, and Syntax Error.

26. To avoid temporal dead zone write all the initialization and declaration at the top.

27. "let & const are Block Scoped"

28. Block is defined by {....}. Also known as compound statement. We wrap multiple statement into a group where Js expects only a single statement.

29. Block scope is what all variables we can access inside a block. 

30. If we have same named variable in block scope and in global scope, then which ever is declared later overshadows the other.

31. <b>Closures</b> :- A function bundled together with its lexical environment.

32. We can pass a function as a parameter during function call. Also we can return a function. It not only returns the function but also returns its lexical scope.

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

33. Closures comes with some corner cases.

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

34. <b>Uses of Closures</b> :- 
      - Module Design Pattern
      - Currying
      - Functions like once
      - Memorize
      - Maintaining state in async world
      - setTimeouts
      - Iterators
      - and many more...

35. <b>setTimeout</b> :- This method sets a timer which executes a function or specified piece of code once the timer expires.

36. In this example, "Namaste Javascript" will get executed as soon as we run the js file but the "1" will be executed after 3000ms.

<code>Example :-</code>
```java
function z() {
   var i = 1;
   setTimeout(function () {
      console.log(i);
   }, 3000);
   console.log("Namaste Javascript");
}
```
<code>Output :-</code>
```java
Namaste Javascript
1
```

37. The loop has already compiled and the value of i has been changed to 6 in the memory. So it prints 6 everytime. When we change the var with let it create a fresh value of i in the memory and creates 5 different copies of i and with every function call it calls different values of i.

<code>Example :-</code>
```java
function z() {
   for (var i = 1; i <= 5; i++) {
      setTimeout(function () {
         console.log(i);
      }, i * 1000);
   }
   console.log("Namaste Javascript");
}
```
<code>Output :-</code>
```java
Namaste Javascript
6
6
6
6
6
```

<code>Example :-</code>
```java
function z() {
   for (let i = 1; i <= 5; i++) {
      setTimeout(function () {
         console.log(i);
      }, i * 1000);
   }
   console.log("Namaste Javascript");
}
```
<code>Output :-</code>
```java
Namaste Javascript
1
2
3
4
5
```

38. We can also solve this problem by using var, by creating a new close function and running the setTimeout function inside it and passing i to the function as parameter.

<code>Example :-</code>
```java
function z() {
   for (var i = 1; i <= 5; i++) {
      function close(i) {
         setTimeout(function () {
            console.log(i);
         }, i * 1000);
      }
      close(i);
   }
   console.log("Namaste Javascript");
}
```
<code>Output :-</code>
```java
Namaste Javascript
1
2
3
4
5
```