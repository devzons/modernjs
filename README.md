# modernjs

## var, let, const
```
let
const 
  - can't reassign
  - have to assign a value
```

## Primitive Data Types vs. Reference Types

### Primitive Data types:
* Stored directly in the location the variable accesses
* Stored on the stack
```
String
Number
Boolean
Null
Undefined
Symbols(ES6)
```

### Reference Data Types:
* Accessed by reference
* Objects that are stroed on the heap
* A pointer to a location in memory

```
Arrays
Object Literals
Functions
Dates
Anything Else...
```
```
typeof
```

## Type conversion

```
// Number to string
val = String(111);

// Bool to String
val = String(true);

// Date to String
val = String(new Date());

// Array to String
val = String([1,2,3,4];)

// toString()
val = (5).toString();
val = (true).toString();

// String to number - val.toFixed()
val = Number('5');
val = Number(true);
val = Number('hello'); // NaN
val = Number([1,2,3]); // NaN

// parseInt, parseFloat
val = parseInt('100.30'); // 100
val = parseFloat('100.30'); // 100.30
```

## Type Coersion

```
const val1 = String(5);
const val2 = 6;
const sum = val1 + val2; // 56, string
----------------
const num1 = 100;
const num2 = 200;
let val;

val = num1 + num2 // 300

Math.PI;
Math.E;
Math.round(2.8);
Math.ceil(2.4); // 3
Math.floor(2.9); //2
Math.sqrt(64);
Math.abs(-12);
Math.pow(8, 2); //64
Math.min(1,2,33);
Math.max(1,2,3);
Math.random();

```
## String

```
firstName.concat(' ', lastName);
firstName.toUpperCase();
firstName.toLowerCase();
// indexOf()
firstName.indexOf('l'); // 3 in William
firstName.lastIndexOf('l'); // 3 in William

// charAt
firstName.charAt('2')
// Get last char
val = firstName.chatAt(firstName.length - 1);

// substring()
firstName.substring(0,4); // Will in William

// slice()
firstName.slice(0,4); // Will in William
firstName.slice(-3); // iam in William

// split()
const str = "Hello there my name is William";
val = str.split(' ');// ["Hello", "there", "my", "name", "is", "William"];
val = str.split(','); 

// replace()
str.replace('William', 'Jack');

// includes()
val = str.includes('Hello'); // true

```

## ES5 vs ES6
```
const age = 28;

// without template string
html = '<ul>' +
       '<li>Age: ' + age + '</li>' +
       ...

// with template strings
html = `
  <ul>
    <li>Age: ${age}</li>
    <li>${2+2}</li>    // insert operation
    <li>${func()}</li> // insert function
    <li>${age > 30 ? 'Over 30' : 'Under 30'}</li> // conditional 
    ...
`;
```

## Array

```
const numbers = [];
const numbers = new Array();

numbers.length;
Array.isArray(numbers); // true
```

## Date()

```
const today = new Date();
let birthday = new Date('9-10-1980 11:25:00');

val = today.getMonth();
val = today.getDate(); // 9
val = today.getDay(); // sunday...
val = today.getFullYear() // 2018
val = today.getHours();
val = today.getMinutes();
val = today.getSeconds();
val = today.getMilliseconds();
val = today.getTime(); // time stamps


```




