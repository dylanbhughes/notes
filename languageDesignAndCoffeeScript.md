# Sprint Introduction

* Pt. 1: Mini-sprint on ES6
  * Lecture
    * New Features
  * Should wrap up by dinner
* P2. 2: Prompt or Free
  * If you get an email, follow instructions
  * If you do not, go do CoffeeScript or go back and revisit material
* Plan for the next 48 hours to SF.Communications by lunchtime
  * Break it down into milestones
  * MKS will hold you accountable


## ES6/ES2015

* History
  * 1995: "Mocha" aka Livescript
  * ES1-1997- Standardized
  * ES2-1998- Minor update
  * ES3-1999- Most major Features
    * Google was really responsible for a resurgence
    * Gmail, google maps, etc. made JS popular and proved the power of JS
  * ????
  * ES5-2009-
  * ES6-2015- big new feature update
    * (EcmaScript vs JavaScript)
      * JS name is technically owned by Oracle
      * So standards use EcmaScript

## So What is ES2015?

* Three Goals
  * Complex applications
  * Interoperability
    * Added "de-facto" features
  * Simple Versioning

## let

  * "let is the new var"
  * Block scoped
  * No hoisting
  * Temporal Dead Zone

* Example 1
```js
var doStuff = function() {
  var x = 42;
  if (false) {
    let x = "cookies";
    console.log("I love " + x);
  }
  console.log("The meaning of life is " + x);
}

doStuff();
```

* Example 2
```js
"use strict";

var doStuff = function() {
  if (false) {
    let x = 42;
  }
  console.log("The meaning of life is " + x);
}

doStuff();
```

* Example 3
```js
for(let i=0; i< 5; i++) { // if you were to use this thing with var it would break
  setTimeout(function() {
    console.log(i);
  }, 300 * i);
}
```
## const

* Like let
* True constant
*

```js
const PI = {value : 3.145};

PI.value = "pie";
PI.tasty = "mmm";

console.log(PI);

// throws error
// cannot change value of PI once set
```

## Default Parameters

```js
function doStuff(x=7) {
  console.log(x);
}

doStuff(); // 7
doStuff(21); // 21
```
* Only responds to undefined

## Destructuring

* Break down object/array
* Simplifies a lot of common patterns
* You're going to see this a lot

```js
let [x, y] = [4,5];
console.log("x: " + x); // x: 4
console.log("y: " + y); // y: 5

let x = 4;
let y = 5;

[x, y] = [y, x];
console.log("x: " + x); // x: 5
console.log("y: " + y); // y: 4

let array = [1,2,3,4,5];
let [,,,x, y] = array;
console.log("x: " + x); // x: 4
console.log("y: " + y); // y: 5


let {
  firstName: first,
  twitter: twit
} = {
  //block of JSON containing some of these things as values
}

function doStuff(x,y) {
  return {
    firstName: "Chris",
    twitter: "crhoton"
  };
}

let {
  firstName: first,
  twitter: twit
} = doStuff();

console.log("First name: " + first); // First name: Chris
console.log("Twitter: " + twit); // Twitter: crhorton
```

* Named variables
```js

function doStuff({username, pass}) {
  console.log(username);
  console.log(pass);
}

doStuff({pass: "pass", username: "chris"});
// chris
// pass
```

* mind blown noise
```js
let {length} = [1,2,3,4,5];
console.log(length);
// 5
```

## Rest Parameters

```js
// the '...' is the operator
let sum = funciton(...operands) {
  let result = 0;
  for(let i = 0; i < operands.length; i++) {
    result += operands[i];
  }
  return result;
}

console.log(sum(1,2,3,4,5)); // 15

let sum = funciton(a,b,...operands) {
  let result = 0;
  for(let i = 0; i < operands.length; i++) {
    result += operands[i];
  }
  return result;
}

console.log(sum(1,2,3,4,5)); // 12
//WHAAAAAA


let x = [4,5,6];
let y = [1,2,3,...x];
console.log(y); // 1,2,3,4,5
```

## String Interpolation

```js
let first = "Chris";
let last = "is Amazing!";
console.log(`${first} ${last}!`);

// Chris is Amazing!
```

## Arrow Functions

```js
let add = (x, y) => x + y;
console.log(add(1,2)); // 3

let square = x => x*x;
console.log(square(4));
```

* Warning: arrow function's "this" often take their parents "this"

## Classes

```js
class Point {
  constructor(x,y) {
    this.x = x;
    this.y = y;
  }
  toString {
    return '(' + this.x + ',' + this.y +  ')';
  }
}

console.log(typeof Point); // function
var point = Point(3,5); // Cannot call a class as a function
console.log(point.toString());

class ColorPoint extends Point {
  constructor(x,y,color) {
    super(x,y);
    this.color = color;
  }
  toString() {
    return '(' + this.color + ', ' + this.x + ', ' + this.y +  ')';
  }
}
```
