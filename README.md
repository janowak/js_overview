# JS Overview

## Javascript versioning 

**Question 1:** What is the difference between JavaScript and ECMAScript?

* ECMAScript 1 and 2 - not really wide known
* ECMAScript 3 - first well known and implemented JS spec (IE 6 -8) and Android 2.x
* ECMAScript 4 - never inroduced
* ECMAScript 5 - widespread standard for JS for the modern revolution and explosion of browsers
* ECMAScript 6 - JS for 2015
* ECMAScript 7 - JS for 2016

[Versioning according to JDKJS](https://github.com/getify/You-Dont-Know-JS/blob/master/es6%20%26%20beyond/ch1.md)

## Types

The following built-in types are available:

* ``` string ```
* ``` number ```

  Only floats ! ``` 0.1 + 0.2 ``` is problematic

* ``` boolean ```
* ``` null ``` and ``` undefined ```
  
  undefined vs null vs Reference Error
 
* ```object``` - dictionary for Java Developer but
  
  All keys are automatically converted to string. Supports prototypical inheritance

  * ```Function``` 
  
  Special as ```typeof someFunction``` returns ```"function"```  
  
  **Question:** What is a difference between 
  ```
  var destroy = function() {console.log("RamPamPam");}
  ```
  vs 
  ```
  function destroy() {console.log("RamPamPam");}
  ```
      
  * ```Array``` 
  
  Special kind of object as ```array[index]``` has different meaning  
  
  * ```Date```
  * ```RegExp```
  * boxed types for primites (string, number, boolean)
  
* ```symbol``` (new to ES6)

**Question 2:** What is the result of ```typeof null```

### Passing data between function

All data is passed by **copy**

### Comparision

```==``` vs ```===``` e.g ```"abc" == new String("abc")```

Complex types are always different (as references are different) - this also works for functions (even if body is exactly the same)

### Truthy & Falsy

Everything in js is an expression so it needs to return something.
If used in if statements values are coersed to true/false e.g.

* "" (empty string)
* 0, -0, NaN (invalid number)
* null, undefined
* false

Any value not on this list is true

### Control flow

**Question: ** what will return ```(false || "abc")```

### Scopes

* block scope
* **lexical scope**
* dynamic scope 

```
function foo() {
    console.log( a );
}

function bar() {
    var a = 3;
    foo();
}

var a = 2;

bar();
```

**Question:** What is a differenece between dynamic and lexical scope

### Hoisting

Wherever a var appears inside a scope, that declaration is taken to belong to the entire scope and accessible everywhere throughout e.g.
**Functions first**

```
myVariable = 10;
var myVariable;
console.log(myVariable);
```

Why such feature was there from begining?

Global scope polluting:

```
IAmInGlobalScope = 2;
```

### Nested scopes

Concept of 'environment' - each function definition creates new environment that has access to variables definied in this environment plus parent environments. 

### Closures

What is a closure:

```
function () {
   var a;

   return function closure() {
	return a;
   }
}
```

Closures introduce a way to create private variables in javascript and concepts related to functional programming (curring, partial application).

### Modules

There was no modules in JS to begin with. Community asnwered this problem with:
* IIFEs
  ```
  (function IIFE(){

    var a = 3;
    console.log( a ); // 3

})();
  ```

* AMD
* CommonJS
* ECMA6 module definition and ```import``` and ```export``` statement was introduced

### this keyword

When a function is invoked, an activation record, otherwise known as an execution context, is created. This record contains information about where the function was called from (the call-stack), how the function was invoked, what parameters were passed, etc. One of the properties of this record is the this reference which will be used for the duration of that function's execution.

[This resolution](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20%26%20object%20prototypes/ch2.md)

### prototypes

https://msdn.microsoft.com/en-us/magazine/ff852808.aspx

### ``` new ``` keyword

``` var a = new String("abc"); ```

1. A brand new object is created (aka, constructed) out of thin air
2. The newly constructed object is [[Prototype]]-linked
3. The newly constructed object is set as the this binding for that function call
4. Unless the function returns its own alternate object, the new-invoked function call will automatically return the newly constructed object.

### for loops in js :)

``` for (i = 0; i<10;i++) { console.log(i); }  ```

``` for (prop in obj) { console.log(obj); } ```

``` for (element of iterable) { console.log(element); } ```

``` Object.keys(obj).forEach(element => { console.log(element); } ```

### program flow 

** Event loop **

**Question:** How does node knows when to end your program?

### web workers

### new features of ECMA6

* let and const statement
  ```
  for (let i=0; i<10; i++) {
    console.log( i );
}

console.log( i ); // ReferenceError
  ```
  
  ```
  var funcs = [];
  for (let i = 0; i < 5; i++) {
    funcs.push( function(){
        console.log( i );
    } );
  }
  funcs[3]();
  ```
* arrow functions
* promises
* generators
* classes
* spread/rest operator, destructuring, default paramater value
* template strings

### Transpiling and pollyfyling

Build tools:
* gulp
* webpack

Transpilers: 
* babel

### Why JS

Used everywhere:
* WEB
* BACKEND (node.js)
* DESKTOP (electron - e.g. Spotify client)

### Materials:

http://superherojs.com/

https://developer.mozilla.org/pl/docs/Web/JavaScript/A_re-introduction_to_JavaScript

https://github.com/getify/You-Dont-Know-JS

https://leanpub.com/javascriptallongesix/read
























