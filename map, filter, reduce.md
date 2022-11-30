<h1><u>Map</u>, <u>Filter</u> <u>&</u> <u>Reduce</u></h1>
<p>

<b><u>Map</u> <u>Function</u></b> : 

- Used when we need to tranform an array. Eg, double the values, triple, find binary of the values.

<code>Example :-</code>

```javascript
const arr = [5, 1, 3, 2, 6];

// Double - [10, 2, 6, 4, 12]
function double(x) {
  return x * 2;
}

// Triple - [15, 3, 9, 6, 18]
function triple(x) {
  return x * 3;
}

// Binary - ["101", "1", "11", "10", "110"]
function binary(x) {
  return x.toString(2);
}

const output1 = arr.map(double);
const output2 = arr.map(triple);
const output3 = arr.map(binary);

// In terms of arrow function
const output4 = arr.map((x) => x.toString(2));

console.log(output1);
console.log(output2);
console.log(output3);
console.log(output4);
```

<code>Output :-</code>

```javascript
[10, 2, 6, 4, 12][(15, 3, 9, 6, 18)][("101", "1", "11", "10", "110")][
  ("101", "1", "11", "10", "110")
];
```

<b><u>Filter</u> <u>Function</u></b> : 

- Used to filter the values inside an array. Eg, find odd elements, even elemnets, elements > 4, etc

<code>Example :-</code>

```javascript
const arr = [5, 1, 3, 2, 6];

// filter odd values
function isOdd(x) {
  return x % 2;
}

// filter even values
function isEven(x) {
  return x % 2 == 0;
}

// grearter than 4
function grearterThanFour(x) {
  return x > 4;
}

const output1 = arr.filter(isOdd);
const output2 = arr.filter(isEven);
const output3 = arr.filter(grearterThanFour);
const output4 = arr.filter((x) => x < 3);

console.log(output1);
console.log(output2);
console.log(output3);
console.log(output4);
```

<code>Output :-</code>

```javascript
[5, 1, 3];[(2, 6)];[(5, 6)];[(1, 2)];
```

<b><u>Reduce</u> <u>Function</u></b> : 

- When you have to iterate over all the elements of an array and come out with a single element. Eg, finding sum, max elemnet, etc. 

- reduce() takes two arguments: function & inital value.

- The function takes 2 parameters: accumulator(accumulates the result) & current(represents the values of the array).

- Initial value takes the inital value of the accumulator.

<code>Example :-</code>

```javascript
const arr = [5, 1, 3, 2, 6];

// Sum
function findSum(arr) {
  let sum = 0;
  for (const i of arr) {
    sum = sum + i;
  }
  return sum;
}

console.log(findSum(arr));

const output = arr.reduce(function (acc, curr) {
  acc = acc + curr;
  return acc;
}, 0);

console.log(output);
```

<code>Output :-</code>

```javascript
17;
17;
```

<b><u>Tricky</u> <u>Example</u></b> :

<code>Example 1 :-</code>

```javascript
const arr = [5, 1, 3, 2, 6];

// Max
function findMax(arr) {
  let max = 0;
  for (const i of arr) {
    if (i > max) {
      max = i;
    }
  }
  return sum;
}

console.log(findMax(arr));

const output = arr.reduce(function (max, curr) {
  if (max < curr) {
    max = curr;
  }
  return acc;
}, 0);

console.log(output);
```

<code>Output :-</code>

```javascript
6;
6;
```

<code>Example 2 :-</code>

```javascript
const users = [
   { firstName: 'Anwesh', lastName: 'Mishra', age: 23},
   { firstName: 'Abhipsha', lastName: 'Patro', age: 22},
   { firstName: 'Manas', lastName: 'Patra', age: 23},
   { firstName: 'Akash', lastName: 'Singh', age: 31},
   { firstName: 'Ankit', lastName: 'Tripathy', age: 35},
]

// list of full names
// ["Anwesh Mishra", "Abhipsha Patro"....]
const fullNames = users.map(x => x.firstName + " " + x.lastName)

// age = { '20': 1, '22': 1, '23': 2, '27': 1 }
const age = users.reduce(function (age, curr) {
   if (age[curr.age]) {
      age[curr.age] = ++age[curr.age]
   } else {
      age[curr.age] = 1;
   }
   return age
}, {}) 
```

- We can chain map(), filter() & reduce()

```javascript
// FirstName whose age < 30 using chaining of function
const nameOfAgeLessThanThirty = users.filter((x) => x.age < 30).map((x) => x.firstName)

// FirstName whose age < 30 using reduce
const output = users.reduce(function (acc, curr){
   if (curr.age < 30) {
      acc.push(curr.firstName)
   }
   return acc
}, [])

console.log(fullNames)
console.log(age)
console.log(nameOfAgeLessThanThirty)
console.log(output)
```

<code>Output :-</code>

```javascript
[ 'Anwesh Mishra',
  'Abhipsha Patro',
  'Manas Patra',
  'Akash Singh',
  'Ankit Tripathy' ]
{ '22': 1, '23': 2, '31': 1, '35': 1 }
[ 'Anwesh', 'Abhipsha', 'Manas' ]
[ 'Anwesh', 'Abhipsha', 'Manas' ]
```

</p>