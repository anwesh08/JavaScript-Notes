<h1>Asynchronous JS & Event Loop</h1>
<p>

- JS can only do a single operation at a time as Js is a sinlge-threaded language which uses call stack present in the Js engine to execute the function().

- Browser has superpowers that are lent to JS engine to execute some tasks, these superpowers include web API's such as console, location, DOM API, setTimeout, fetch, local storage.

- Callback functions and event handlers are first stored in Web API environment and then transferred to callback queue.

<code>Example :-</code>

```javascript
console.log("Start");

setTimeout(function cb() {
  console.log("CallBack");
}, 5000);

console.log("End");
```

<code>Output :-</code>

```javascript
Start;
End;
CallBack;
```

<code>Example :-</code>

```javascript
console.log("Start");

document.getElementById("btn").addEventListener("click", function xyz() {
  console.log("CallBack");
});

console.log("End");
```

<code>Output :-</code>

```javascript
Start;
End;
CallBack; // callback function is executed if the button is clicked, otherwise the callback function won't be executed.
```

- The Event Loop pushes the "queue" into the Call Stack only when the Call Stack is empty (i.e. the global execution context has been pushed off the call stack).

- The order in which the Event Loop works is: <br>
      1. Call Stack <br>
      2. Microtask Queue <br>
      3. Callback Queue <br>

- All the callback functions which come back through promises goes into the microtask queue.

- Promises and mutation observer are stored in web API's environment and then transferred to microtask queue.

- Event loop continuously observes call stack and when it is empty it transfers task to call stack.

- Micro task is given priority over callback tasks.

- Too many micro tasks generated can cause Starvation (nit giving time to callback tasks to execute).

<code>Example :-</code>

```javascript
console.log("Start");

setTimeout(function cbT() {
  console.log("CB setTimeout");
}, 5000);

// fetch() is ready to be executed when it receives the data requested from the server. The function cbF will go into the Microtask Queue.
fetch("https://api.netflix.com").then(function cbF() {
  console.log("CB Netflix");
});

console.log("End");
```

</p>