assertFunction
==============

A simple function that lets you easily assert the arguments passed to you function/method

### Why use it
When developing, especially TDD, it is very nice to be able to secure what arguments your function/method accepts with
a simple function. Often bugs appear due to one function passing a wrongly passed argument to an other function,
by asserting arguments it will be a lot easier to debug your code.

### How to use
```javascript
var myFunction = function () {
  assertFunction(arguments); // Will throw errors if any arguments are passed
}

var myFunction = function (myArg) {
  // Will throw errors if the first argument is missing or if it is not a string
  assertFunction(arguments, 'string'); 
}

var myFunction = function (myArg) {
  // Will throw errors if the first argument is something else than a string, 
  // but not throw error if it is lacking
  assertFunction(arguments, '?string'); 
}

var myFunction = function (myArg) {
  // Will throw error if first argument is missing or is not of type string or number
  assertFunction(arguments, 'string:number');
}

var myFunction = function (myArg) {
  // Will throw errors if the first argument is something else than a string or number, 
  // but not throw error if it is lacking
  assertFunction(arguments, '?string:number'); 
}

var myFunction = function (myStringArg, myNumberArg) {
  // Can pass any number of expected types
  assertFunction(arguments, 'string', 'number'); 
}

var myFunction = function (myStringArg, myNumberArg) {
  // Optional types can be passed after required types
  assertFunction(arguments, 'string', '?number'); 
}

var myFunction = function () {
  // Verify that all passed arguments are of type string, give error if no arguments are passed
  assertFunction(arguments, ['string']); 
}

var myFunction = function () {
  // Verify that all passed arguments are of type string and allow no arguments to be passed
  assertFunction(arguments, ['?string']); 
}

var myFunction = function () {
  // Verify that all passed arguments are of type string or number and allow no arguments to be passed
  assertFunction(arguments, ['?string:number']); 
}
```

### Types
- string
- number
- boolean
- array
- object
- null
- function
