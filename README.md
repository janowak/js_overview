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

**Question 2:** What is the result of ```typeof null```

* ```string```
* ```number```

  Only floats ! ```0.1 + 0.2``` is problematic

* ```boolean```
* ```null``` and ```undefined```
  
  undefined vs null vs Reference Error
 
* ```object``` - dictionary for Java Developer but
  
  All keys are automatically converted to string. Support so called prototypical inheritance

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

### Passing data between function

All data is passed by **copy**

### Comparision

```==``` vs ```===``` e.g ```"abc" == new String("abc")```

Complex types are always different (as references are different) - this also works for functions (even if body is exactly the same)

### Truthy & Falsy

Everything in js is an expression so it needs to return something.
If used in if statements values are coersed to true/false concept e.g.

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

Conpept of so called environment - each function definition creates new environment that has access to variables definied in this environment plus parent environments. 

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

Closures introduce a way to create private variables in javascript

### Modules

There was no conpect of modules to begin with. Community asnwered this problem with:
* IIFEs
  ```
  (function IIFE(){

    var a = 3;
    console.log( a ); // 3

})();
  ```

* AMD
* CommonJS

in ECMA6 module definition and ```import``` and ```export``` statement was introduced

### this keyword

### prototypes

### program flow 

### web workers

### new features of ECMA6

* let and const statement
  ```
  for (let i=0; i<10; i++) {
    console.log( i );
}

console.log( i ); // ReferenceError
  ```

* arrow functions
* Promises
* generators

### Transpiling and pollyfyling


























