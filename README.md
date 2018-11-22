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

<<<<<<< HEAD
## Asynchronous Programming

Most Async code you work with will be part of a API or library

* XMLHttpRequest & Fetch
* jQuery Ajax, Axios, other HTTP libraries
* Node.js filesystem module

There ara a few ways to work with Async code

* Callbacks
* Promises
* Async/Await

## What is Ajax

* Asynchronous JavaScript & XML
* Set of web technologies
* Send & Receive data asynchronously
* Does not interfere with the current page
* JSON has replaced XML for the most part

### Diagram of Ajax

  * Make async requests in the background
  * No page reload/refresh
  * Fetch data
  * Very interactive
=======
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

## Keyboard Input Events, Form Event

```
const form = document.querySelector('form');
const taskInput = document.getElementById('task');

// Clear input
taskInput.value = '';

form.addEventListener('submit', runEvent);

// key events
taskInput.addEventListener('keydown', runEvent);
taskInput.addEventListener('keyup', runEvent);
taskInput.addEventListener('keypress', runEvent);
// focus
taskInput.addEventListener('focus', runEvent);
// blur
taskInput.addEventListener('blur', runEvent);
// cut
taskInput.addEventListener('cut', runEvent);
// paste
taskInput.addEventListener('paste', runEvent);
// input - copy, paste, cut
taskInput.addEventListener('input', runEvent);
// change event
select.election.addEventListener('change', runEvent);

function runEvent(e){
    console.log(`EVENT TYPE: ${e.type}`);

    // get input value
    console.log(taskInput.value);

    e.preventDefault();

    // typewirte effect
    console.log(e.target.value);
    el.innterText = e.target.value;
}
```

## Event Bubbling Delegation

```
// Event Bubbling - to all parent

document.querySelector('.card-title').addEventListener('click', function() {
    console.log('card title'); 
});

// Event Delegation - to all children

const delItem = document.querySelector('.delete-item');

delItem.addEventListener('click', deleteItem);

document.body.addEventListener('click', deleteItem);

function deleteItem(e) {
    
    console.log('e.target');
    // if(e.target.className === 'delete-item'){
    //     console.log('delete item');
    // }

    // remove parent item(li tag)
    if(e.target.classList.contains('delete-item')){
        console.log('delete item');
        e.target.parentElement.remove();
    }
}

```

## Local Sesstion Storage

```
HTML -----

<div class="container">
    <div class="row">
      <div class="col s12">
        <div id="main" class="card">
          <div class="card-content">
            <span class="card-title">Task List</span>
            <div class="row">
              <form action="index.php" id="task-form">
                <div class="input-field col s12">
                    <input class="input-field col s12"><input type="text" name="task" id="task" value="">
                    <label for="task">New Task</label>
                </div> 
            </div><!--.row-->
            <button id="add" class="btn">Add</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>

JS -------------------------
// set session storage item - disapear browser closed
sessionStorage.setItem('name', 'Beth');

// set local storage item
localStorage.setItem('name', 'John');
localStorage.setItem('age', '30');

// remove from local storage item
localStorage.removeItem('name');

// get from storage
const name = localStorage.getItem('name');
const name = localStorage.getItem('age');

// clear local storage
localStorage.clear(); // value to null

// submit event
document.querySelector('form').addEventListener('submit', function(e) {
    const task = document.getElementById('task').value;

    let tasks;

    if(localStorage.getItem('tasks')=== null){
        tasks = [];
    } else {
        tasks = JSON.parse(localStorage.getItem('tasks'));
    }

    tasks.push(task);

    localStorage.setItem('tasks', JSON.stringify(tasks));

    alert('Task saved');

    e.preventDefault();
});

const tasks = JSON.parse(localStorage.getItem('tasks'));

tasks.forEach(function(task) {
    console.log(task);
});


```
>>>>>>> 614925facd7ab3bde1f9b2f78ef8b7a4a78d7a7f


## Error Handling with try...catch

Various form of errors and handling

```
const user = {email: 'jhon@gmail.com'};

try {
  // Produce a ReferenceError
  // myFunction();

  // Produce a TypeError
  // null.myFunction();

  // Produce a SyntacError
  // eval('Hello World');

  // Produce a URIError
  // decodeURIComponent("%");

  if(!user.name){
    // throw 'User has no name';
    throw new SyntacError('User has no name');
  }

} catch(e){
  console.log(e);
  // console.log(e.message);
  // console.log(e.name);
  // console.log(e instanceof ReferenceError);
} finally {
  console.log('Finally runs regardless of result...');
}

console.log('program continue..');

```

## Regular Expression

```
let re;
// re = /hello/; 
re = /hello/i; // i = case insensitive
// re = /hello/g; // global search

// console.log(re);
// console.log(re.source);

// exec() - Return result in an array or null
//---------------------------------------------------------------------
// const result = re.exec('don hello world');

// console.log(result);
// console.log(result[0]);
// console.log(result.index);
// console.log(result.input);

// test() - Return true or false 
//----------------------------------------------------------------------
// const result = re.test('Hello');
// console.log(result);

// match() - return result array or null 
//----------------------------------------------------------------------
// const str = 'Hello there';
// const result = str.match(re);
// console.log(result);

// search() - Return index of the first match if not found returns -1 
//----------------------------------------------------------------------
// const str = "Don, Hello There";
// const result = str.search(re);
// console.log(result);

// replace() - Return new string with some or all matches of a pattern
//---------------------------------------------------------------------
// const str = 'Hello There';
// const newStr = str.replace(re, 'Hi');
// console.log(newStr);

```

REGEX

```
let re;
// Literal Characters
re = /hello/i;

// Metacharacter Symbols
re = /^h/i;         // Must starts with
re = /world$/i;     // Must ends with
re = /^hello$/i;    // Must begin and end with
re = /h.llo/i;      // Matches any ONE character - one character wild card
re = /h*llo/i;      // Matches any character 0 or more times - wild card
re = /gre?a?y/i;    // Optional character
re = /gre?a?y\?/i;  // Escape character

// Brackets [] - Character Sets
re = /gr[ae]y/i;    // Must be an a or e
re = /[GF]ray/i;    // Must be an G or F
re = /[^GF]ray/i;   // Match anything except G or F
re = /[A-Z]ray/;    // Match any uppercase letter
re = /[a-z]ray/;    // Match any lowercase letter
re = /[A-Za-z]ray/;    // Match any letter
re = /[0-9][0-9]ray/;    // Match any digit

// Braces {} - Quantifiers
re = /Hello/i;
re = /Hel{2}o/i;    // Must occur exactly {m} amount of times;
re = /Hel{2,4}o/i;  // Must occur between {m,n} amount of times;
re = /Hel{2,}o/i;   // Must occur at least {m} times;

// Parentheses () - Grouping
re = /([0-9]x){3}/
 
//Shorthand Character Classes
re = /\w/;        // Word character - alphanumeric or _
re = /\w+/;       // + = one or more character - alphanumeric or _
re = /\W/;        // Non-Word character
re = /\d/;        // Match any digit
re = /\d+/;       // Match any digit 0 or more times
re = /\D/;        // Non-digit
re = /\D+/;       // Non-digit 0 or more times
re = /\s/;        // Match whitespace char
re = /\S/;        // Non-whitespace char
re = /Hell\b/i;     // Word boundary


// Assertions
re = /x(?=y)/;    // Match x only if followed by y
re = /x(?!y)/;    // Match x only if NOT followed by y


// String to match 
const str = 'xye';


// Log results
const result = re.exec(str);
console.log(result);

function reTest(re, str) {
  if(re.test(str)) {
    console.log(`${str} matches ${re.source}`);
  } else {
    console.log(`${str} does not match ${re.source}`);
  }
}

reTest(re, str);

```

## Create form using REGEX

Form Validation
```
<form>
  <div class="form-group">
    <label>Name</label>
    <input type="text" class="form-control" id="name" placeholder="Name">
    <div class="invalid-feedback">
      Name must be between 2 and 10 characters
    </div>
  </div>
  <div class="form-group">
    <label>Zipcode</label>
    <input type="text" class="form-control" id="zip" placeholder="Zipcode">
    <div class="invalid-feedback">
      Enter a valid zipcode
    </div>
  </div>
  <div class="form-group">
    <label>Email</label>
    <input type="text" class="form-control" id="email" placeholder="Email">
    <div class="invalid-feedback">
      Enter a valid email
    </div>
  </div>
  <div class="form-group">
    <label>Phone Number</label>
    <input type="text" class="form-control" id="phone" placeholder="Phone Number">
    <div class="invalid-feedback">
      Enter a valid phone
    </div>
  </div>
  <input type="submit" value="Submit" class="btn btn-primary btn-block">
</form>
```

js

```
// Form Blur event listeners
document.getElementById('name').addEventListener('blur', validateName);
document.getElementById('zip').addEventListener('blur', validateZip);
document.getElementById('email').addEventListener('blur', validateEmail);
document.getElementById('phone').addEventListener('blur', validatePhone);

function validateName() {
  const name = document.getElementById('name');
  const re = /^[a-zA-Z]{2,10}$/;

  if(!re.test(name.value)) {
    name.classList.add('is-invalid');
  } else {
    name.classList.remove('is-invalid');
  }
}

function validateZip() {
  const zip = document.getElementById('zip');
  const re = /^[0-9]{5}(-[0-9]{4})?$/;

  if(!re.test(zip.value)) {
    zip.classList.add('is-invalid');
  } else {
    zip.classList.remove('is-invalid');
  }
}

function validateEmail() {
  const email = document.getElementById('email');
  const re = /^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,6})$/;

  if(!re.test(email.value)) {
    email.classList.add('is-invalid');
  } else {
    email.classList.remove('is-invalid');
  }
}

function validatePhone() {
  const phone = document.getElementById('phone');
  const re = /^\(?\d{3}\)?[-., ]?\d{3}[-., ]?\d{4}$/;

  if(!re.test(phone.value)) {
    phone.classList.add('is-invalid');
  } else {
    phone.classList.remove('is-invalid');
  }
}
```


## Iterators and Generators

```
// Iterator Exmple
//--------------------------------------------------------------------
function nameIterator(names) {
  let nextIndex = 0;

  return {
    next: function() {
      return nextIndex < names.length ? 
      { value: names[nextIndex++], done: false } :
      { done: true }
    }
  }
}

// Create an array of names
const namesArr = ['Jack', 'Jill', 'John'];

// init iterator and pass in the names array
const names = nameIterator(namesArr);

console.log(names.next().value);

// Generator Example
//--------------------------------------------------------------------
function* sayNames() {
  yield 'Jack';
  yield 'Jill';
  yield 'John';
}

const name = sayNames();

console.log(name.next().value);
console.log(name.next().value);
console.log(name.next().value);

// ID Creator ----------------
function* createIds() {
  let index = 0;

  while (true){
    yield index++;
  }
}

const gen = createIds();

console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value);
console.log(gen.next().value);

```

## Profile Scroll using iterator for real application

```
// HTML

<div class="container">
  <div class="row">
    <div class="col-md-6 mx-auto text-center">
      <h1 class="mb-3">Profile Scroller</h1>
      <div id="imageDisplay"></div>
      <br>
      <div id="profileDisplay"></div>
      <br>
      <button id="next" class="btn btn-dark btn-block">Next</button>
    </div>
  </div>
</div>

// app.js
const data = [
  {
    name: 'John Doe',
    age: 32,
    gender: 'male',
    lookingfor: 'female',
    location: 'Boston MA',
    image: 'https://randomuser.me/api/portraits/men/82.jpg'
  },
  {
    name: 'Jane Doe',
    age: 26,
    gender: 'female',
    lookingfor: 'male',
    location: 'Pittsburge PA',
    image: 'https://randomuser.me/api/portraits/women/82.jpg'
  },
  {
    name: 'Paul Doe',
    age: 28,
    gender: 'male',
    lookingfor: 'female',
    location: 'New York NY',
    image: 'https://randomuser.me/api/portraits/men/72.jpg'
  },
  {
    name: 'Sarah Doe',
    age: 30,
    gender: 'female',
    lookingfor: 'male',
    location: 'Miami FL',
    image: 'https://randomuser.me/api/portraits/women/72.jpg'
  }
];

const profiles = profileIterator(data);

// call initial profile
nextProfile();

// Next event
document.getElementById('next').addEventListener('click', nextProfile);

// Next profile display
function nextProfile() {
  const currentProfile = profiles.next().value

  if(currentProfile !== undefined) {
    document.getElementById('profileDisplay').innerHTML = `
      <ul class="list-group">
        <li class="list-group-item">Name: ${currentProfile.name}</li>
        <li class="list-group-item">Age: ${currentProfile.age}</li>
        <li class="list-group-item">Gender: ${currentProfile.gender}</li>
        <li class="list-group-item">Looking for: ${currentProfile.lookingfor}</li>
        <li class="list-group-item">Location: ${currentProfile.location}</li>
      </ul>
    `;

    document.getElementById('imageDisplay').innerHTML = `<img src="${currentProfile.image}">`;
  } else {
    // No more profiles
    window.location.reload();
  }
}

// Profile Iterator

function profileIterator(profiles) {
  let nextIndex = 0;

  return {
    next: function() {
      return nextIndex < profiles.length ?
        { value: profiles[nextIndex++], done: false } :
        { done: true };
    }
  };
}
```

## Symbol()

```
// Create a symbol --------------------------------
// const sym1 = Symbol();
// const sym2 = Symbol('sym2');

// console.log(sym1);

// console.log(`Hello ${sym1.toString()}`);

// Unique Object Keys -----------------------------
const KEY1 = Symbol();
const KEY2 = Symbol('sym2');

const myObj = {};

myObj[KEY1] = 'Prop1';
myObj[KEY2] = 'Prop2';
myObj.key3 = 'Prop3';
myObj.key4 = 'Prop4';

// console.log(myObj[KEY1]);


// Symbols are not enumerable in for...in loops ------
// for(let i in myObj){
//   console.log(`${i}: ${myObj[i]}`);
// }

// Symbols are ignored by JSON.stringify -------------
console.log(JSON.stringify({key: 'prop'}));
console.log(JSON.stringify({[Symbol('sym1')]: 'prop'}));

```

## Destructuring

```
// Destructuring Assignment

let a, b;
[a, b] = [100, 200];

// Rest pattern
[a, b, c, ...rest] = [100, 200, 300, 400, 500];

({ a, b } = { a: 100, b: 200, c: 300, d: 400, e: 500 });
({ a, b, ...rest } = { a: 100, b: 200, c: 300, d: 400, e: 500 });

// Array Destructuring ----------------------------------------------

// const people = ['John', 'Jill', 'Mike'];

// const [person1, person2, person3] = people;

// console.log(person1, person2, person3);

// Parse array returned from function ---------------------------------
// function getPeople() {
//   return ['John', 'Jill', 'Mike'];
// }

// let person1, person2, person3;
// [person1, person2, person3] = getPeople();
// console.log(person1, person2, person3);

// Object Destructuring ----------------------------------------------
const person = {
  name: 'John Doe',
  age: 26,
  city: 'Miami',
  gender: 'Male',
  sayHello: function() {
    console.log('Hello');
  }
}

// Old ES5
// const name = person.name,
//       age = person.age,
//       city = person.city;

// New ES6
const {name, age, city, sayHello} = person;

console.log(name, age, city);

sayHello();

```


#3 Maps


```
// MAPS = key-value paris - can use ANY type as a key or value

const map1 = new Map();

// set keys
const key1 = 'some string',
      key2 = {},
      key3 = function() {};

// set map values by key
map1.set(key1, 'Value of key1');
map1.set(key2, 'Value of key2');
map1.set(key3, 'Value of key3');

// get values by key
// console.log(map1.get(key1), map1.get(key2), map1.get(key3));

// count values
// console.log(map1.size);

// Iteratino maps - Loop using for...of to get keys and values
// for(let [key, value] of map1){
//   console.log(`${key} = ${value}`);
// }

// iterate keys only
// for(let key of map1.keys()){
//   console.log(key);
// }

// iterate values only
// for(let value of map1.values()){
//   console.log(value);
// }

// Loop with forEach
// map1.forEach(function(value, key){
//   console.log(`${key} = ${value}`);
// });

// Convert to Arrays

// create an array of the key value pairs
// const keyValArr = Array.from(map1);
// console.log(keyValArr);

// create an array of the values
// const valArr = Array.from(map1.values());
// console.log(valArr);

// create an array of the keys
const keyArr = Array.from(map1.keys());
console.log(keyArr);
```