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
```

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

```

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
let lis = document.getElementsByTagName('li');

// Convert HTMLd collection into array
lis = Array.from(lis);
lis.reverse();
lis.forEach(function(li, index){
  console.log(li.className);
  li.textContent = `${index}: Hello`;
});

// querySelectorAll();
const items = document.querySelectorAll('ul.collection li.collection-item');

items.forEach(function(item, index){
  item.textContent = `${index}: Hello';
});

liOdds = document.querySelectorAll('li:nth-child(odd)'); // all odd
liOdds.forEach(function(odd, index){
  odd.style.background = '#ccc';
});

```

## Traversing the DOM

```
const list = document.querySelector('ul.collection');
const listItem = document.querySelector('li.collection-item:first-child');

// Get child nodes
list.childNodes; // li nodes + text nodes: indentation
list.childNodes[0].nodeName; // text
list.childNodes[3].nodeType;

1   Element node
2   Attribute(derprecated)
3   Text node
8   Comment
9   Document itself
10  Doctype

// Get children element nodes
list.children;  // li nodes only

// children of children
list.children[3].children[0].id = 'id-name'; // add id

// first child
list.firstChild; // text 
list.firstElementChild; // list item

// last child
list.lastChild; // text
list.lastElementChild; // list item

// count child elements
list.childElementCount;

// get parent node
listItem.parentNode; // <ul>..
listItem.parentElement;
listItem.parentElement.parentElement;

// Get next sibling
listItem.nextSibling;
listItem.nextElementSibling.nextElementSibling;

// get prev sibling
listItem.previousSibling;
listItem.previousElementSibling;

```

## Creating Elements

```
// Create element
const li = document.createElement('li');

// Add class
li.className = 'collection-item';

// Add id
li.id = 'new-item';

// Add attribute
li.setAttribute('title', 'New Item');

// Create text node and append
li.appendChild(document.createTextNode('Hello World'));

// Create new link element
const link = document.createElement('a');
// Add classes
link.className = 'delete-item secondary-content';
// Add icon html
link.innerHTML = '<i class="fa fa-remove"></i>';

// Append link into li
li.appendChild(link);

// Append li as child to ul
document.querySelector('ul.list').appendChild(li);

console.log(li);
```

## Removing, Replacing Elements

```
// Replace h5 title to h2 title ==========

// Create Element
const newHeading = document.createElement('h2');
// Add id
newHeading.id = 'task-title';
// New Text node
newHeading.appendChild(document.createTextNode('Task List'));

// Get the old heading
const oldHeading = document.getElementById('task-title');
// Parent
const cardAction = document.querySelector('.card-action');

// Replace
cardAction.replaceChild(newHeading, oldHeading);

// Remove Element =============
const lis = document.querySelectorAll('li');
const list = document.querySelector('ul');

// remove list item
lis[0].remove();

// remove child element
list.removeChild('lis[3]');

// Classes & Arrt ==============
const firstLi = document.querySelector('li:first-child');
const link = firstLi.children[0];

let val;

val = link.className; // all class name
val = link.classList; // class name array list
val = link.classList[0]; // first class element - delete-tiem;
link.classList.add('test'); // add class
link.classList.remove('test'); // remove class

// Attribute
link.getAttribute('href');
link.setAttribute('href', 'https://google.com');
link.hasAttribute('href'); // true or false
link.removeAttribute('title');

```

## Event Listener, The Event Object

```
document.querySelector('.clear-tasks').addEventListener('click', function(event) {
    console.log('Hello World');
    // event.preventDefault();
});

document.querySelector('.clear-tasks').addEventListener('click', onClick);

function onClick(e) {

    val = e.target;
    val = e.target.id;
    val = e.target.className;
    val = e.target.classList[0];
    e.target.innerText = "Hello";

    // event type
    e.type; // click

    // Timestamp
    e.timeStamp;

    // Coords event relative to the window
    e.clientY; // from the top pixel
    e.clientX; // from the left

    // Coords event relative to the element
    e.offsetY;
    e.offsetX;

    console.log(val);
}

```

## Mouse Events

```
// Event handler

// click event
btn.addEventListener('click', runEvent);
btn.addEventListener('dblclick', runEvent);
btn.addEventListener('mousedown', runEvent);
btn.addEventListener('mouseup', runEvent);
btn.addEventListener('mouseenter', runEvent);
btn.addEventListener('mouseleave', runEvent);
btn.addEventListener('mouseover', runEvent);
btn.addEventListener('mouseout', runEvent);
btn.addEventListener('mousemove', runEvent);

function runEvent(e) {
    console.log(`EVENT TYPE: ${e.type}`);

    // change coords by mouse positions
    el.textContent = `MouseX: ${e.offsetX} MouseY: ${e.offsetY}`;

    // change background color accroding to mouse coords
    document.body.style.backgroundColor = `rgb(${e.offsetX}, ${e.offsetY}, 40)`;
}

```







