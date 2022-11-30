<h1>Closures</h1>
<p>

- <b>Closures</b> means functions bundled together with its lexical environment.

- We can pass a function as a parameter during function call. Also we can return a function. It not only returns the function but also returns its lexical scope.

<code>Example :-</code>

```javascript
function x() {
  var a = 7;
  return function y() {
    console.log(a);
  };
  return y;
}
var z = x();
console.log(z);
z();
```

<code>Output :-</code>

```javascript
f y() {
   console.log(a);
}
7
```

- Closures comes with some corner cases.

<code>Example :-</code>

```javascript
function x() {
  var a = 7;
  return function y() {
    console.log(a);
  };
  a = 100;
  return y;
}
var z = x();
console.log(z);
z();
```

<code>Output :-</code>

```javascript
f y() {
   console.log(a);
}
100
```

<code>Example :-</code>

```javascript
function z() {
  var b = 900;
  function x() {
    var a = 7;
    return function y() {
      console.log(a, b);
    };
    y();
  }
  x();
}
z();
```

<code>Output :-</code>

```javascript
7, 900;
```

- <b>Uses of Closures</b> :- <br> - Module Design Pattern<br> - Currying<br> - Functions like once<br> - Memorize<br> - Maintaining state in async world<br> - setTimeouts<br> - Iterators<br> - Data hiding and encapsulation<br> - and many more...<br>

- Disadvantages of Closures :-<br> - Over consumption of memory

- Garbage collector is like a program in js engine which freeeze up the unused memory.

<b>setTimeout</b> : 
  
- This method sets a timer which executes a function or specified piece of code once the timer expires.

- In this example, "Namaste Javascript" will get executed as soon as we run the js file but the "1" will be executed after 3000ms.

<code>Example :-</code>

```javascript
function z() {
  var i = 1;
  setTimeout(function () {
    console.log(i);
  }, 3000);
  console.log("Namaste Javascript");
}
```

<code>Output :-</code>

```javascript
Namaste Javascript
1
```

- The loop has already compiled and the value of i has been changed to 6 in the memory. So it prints 6 everytime. When we change the var with let it create a fresh value of i in the memory and creates 5 different copies of i and with every function call it calls different values of i.

<code>Example :-</code>

```javascript
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

```javascript
Namaste Javascript
6
6
6
6
6
```

<code>Example :-</code>

```javascript
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

```javascript
Namaste Javascript
1
2
3
4
5
```

- We can also solve this problem by using var, by creating a new close function and running the setTimeout function inside it and passing i to the function as parameter.

<code>Example :-</code>

```javascript
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

```javascript
Namaste Javascript
1
2
3
4
5
```

- In the above example, the setTimeOut will have its closure within the close funtion which creates different copies of a single function with different values and makes it easier.

</p>
