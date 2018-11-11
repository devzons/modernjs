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

setMonth()
setDate()
setFullYear()
setHours()
setMinutes()
setSeconds()

```

## Window Methods / Obejects / Properties

```
alert();
prompt();
confirm();

// Outer height and width
window.outerHeight;
window.outerWidth;

//inner height and width
window.innerHeight;
window.innerWidth;

// Scroll points
window.scrollY;
window.scrollX;

// Location Object
window.location;
window.location.hostname;
window.location.port;
window.location.href;
window.location.search;

// Redirect
window.location.href ="https://google.com";

//Reload
window.location.reload(); // keep reloading

// History Object - browsing history
window.history.go(-1); // previous site
window.history.length; // 

// Navigator Object
window.navigator;
window.navigator.appName;
window.navigator.appVersion;
window.navigator.userAgent;
window.navigator.platform;
window.navigator.vendor;
window.navigator.language;

```

## Scope

```
// Global Scope
var a = 1;
let b = 2;
const c = 3;

function test() {
  // function scope
  var a = 4;
  let b = 5;
  const c = 6;
}

if(true){
  // Block Scope
  var a = 4;
  let b = 5;
  const c = 6;
}

## DOM

```
let val;

val = document;
val = document.all; // [html, head,....]
document.all.length;
document.head;
document.body;
document.doctype;
document.domain;
document.URL;
document.characterSet;
document.contentType;

document.forms;
document.forms[0];
document.forms[0].id;
document.forms[0].method;
document.forms[0].action;

document.links;
document.links[0];
document.links[0].className;
document.links[0].classList[0];

document.images;

document.scripts;
document.scripts[2].getAttribute('src');

// get all scripts src
let scripts = document.scripts;

let scriptsArr = Array.from(scripts);

scriptsArr.forEach(function(script) {
  console.log(script.getAttribute('src'));
});


```

## DOM Selectors

// getElementById()
document.getElementById('id-name');
document.getElementById('id-name').id;
document.getElementById('id-name').className;

// change style
document.getElementById('id-name').style.background = '#333';

// change content
document.getElementById('id-name').textContent = 'content';
document.getElementById('id-name').innerText = 'content';
document.getElementById('id-name').innerHTML = '<p style="color:red;">content</p>';

// querySelector()
document.querySelector('#id-name');
document.querySelector('.class-name');
document.querySelector('h1');
document.querySelector('li:last-child');
document.querySelector('li:nth-child(3)');
document.querySelector('li:nth-child(odd)'); // first odd

## DOM Selectors - Multiple elements

// getElementsByClassName()

const items = document.getElementsByClassName('class-name');
items[0];
items[0].style.color = 'red';

const liitems = document.querySelector('ul').getElementByClassName('class-name');

// getElementsByTagName();







