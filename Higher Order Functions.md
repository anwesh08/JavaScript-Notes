<h1>Higher Order Functions</h1>
<p>

- A function which takes another fucntion as an argument is called a higher order function.

- A function which is passed into the higher order function is called the callback function(which is called afterwards in the function ; possible because functions are first class citizens in js)

<code>Example :-</code>
```javascript
function x() {
   console.log("Namaste");
}
function y(x) {
   x();
}
// y is the higher order function
```

<code>Example :-</code>
```javascript
const radius = [3, 1, 2, 4];
const calculateArea = function (radius) {
   const output = [];
   for (let i =0; i < radius.length; i++) {
      output.push(Math.PI * radius[i] * radius[i]);
   }
   return output;
}
console.logcalculateArea(radius));
const calculateCircumference = function (radius) {
   const output = [];
   for (let i =0; i < radius.length; i++) {
      output.push(2 * Math.PI * radius[i]);
   }
   return output;
}
console.logcalculateCircumference(radius));
const calculateDiameter = function (radius) {
   const output = [];
   for (let i =0; i < radius.length; i++) {
      output.push(2 * radius[i]);
   }
   return output;
}
console.logcalculateDiameter(radius));
```

-  Problem in the program: 
   - Repetitive - same code, different logic

- To overcome this problem make the function generic.
                                 
<b>Generic Function :</b>
<code>Example :-</code>
```javascript
const radius = [3, 1, 2, 4];

const area = function (radius) {
   return Math.PI * radius * radius;
}

const circumference = function (radius) {
   return 2 * Math.PI * radius;
}

const diameter = function (radius) {
   return 2 * radius;
}

const calculate = function(radius, logic) {
   const output = [];
   for (let i = 0; i < radius.length; i++) {
      output.push(logic(radius[i]));
   }
   return output;
}
console.log(calculate(radius, area))
console.log(calculate(radius, diameter))
console.log(calculate(radius, circumference))

// calculate function is a higher order function whereas all other functions like area, circumference, diameter are callback function.

console.log(radius.map(area));

// We can use map function which is a higher order function and returns an array as an output. So we can pass the callback function to it as an parameter.
```

<code>Example :-</code>
```javascript
const radius = [3, 1, 2, 4];

const area = function (radius) {
   return Math.PI * radius * radius;
}

const circumference = function (radius) {
   return 2 * Math.PI * radius;
}

const diameter = function (radius) {
   return 2 * radius;
}

// Here, Array.prototype.calculate = it appears in all the arrays. 
// Here, this is pointed to the array. 

// Polyfill for map
Array.prototype.calculate = function(logic) {
   const output = [];
   for (let i = 0; i < this.length; i++) {
      output.push(logic(this[i]));
   }
   return output;
}

console.log(radius.calculate(area));
// Map function can also we wriiten like this
```

- Functional programming deals with pure funtion, composition of function, reusability, modularity.
</p> 
