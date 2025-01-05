## Variable

**Value** is the smallest unit we have in a javascript
we can use it over and over again in a variable by storing in a variable

> variable is like a box

- You can start variable with a dollar sign.
- we should not start variable with uppercase letter
  it is a convention.
- if a real constant than name variable in uppercase

```javascript
let PI = 3.14;
```

## Datatypes

Every value in javascript is either an object or a primitive
There are seven primitive datatypes in javascript
value taken by a variable that is not yet defined - Undefined

```Javascript
let children;
```

### Javascript is dynamic typing

when you create a variable in javascript you don't need to
define its datatype. this is called dynamic typing.

### Mutating a Variable

```javascript
let age = 30;
// mutating a variable
age = 31;
```

### let, var and const in Javascript

`let` is block scoped and `var` is function scoped.
You should never use `var`
If we dont use let or const or var while declaring a variable, javascript will not show any error. Instead, It will create property on global object.

## Type Conversion and Coercion

Type conversion is when we manually convert from one type to another while type coercion is when javascript automatically converts behind the scene for us.

### Type Conversion

Let's see Type Conversion in action using a code that calculate age

```javascript
const myBirthYear = "1991";
const now = 2025;
const myAge = now - Number(myBirthYear);
console.log(`My age is ${myAge}`); // My age is 34
```

### Type Coercion

When we input two different datatypes values then javascript converts one of the value to the same type as the other one to match the type. In this example when we do `+` operation on a string and a number, first it converts number into string and then do the operation and the end result is a string. Let's take an example below

```javascript
const inputYear = "1991"; // '1991' here is a string
console.log(inputYear + 10); // '199110'
console.log(typeof inputYear); // string
```

`console.log(inputYear + 10) ` is same as `console.log(inputYear + '10')` both gives the same output `'199110'` the only difference is that in the former code example javascript is doing type coercion on its own behind the scene.

If we perform `-` `*` `/` operation on a string and a number then javascript converts the string to a number then perform the operation. Let's take a look at the code below

```javascript
const myBirthYear = "1991"; // '1991' is a string
const now = 2025; // 2025 is a number
const myAge = now - myBirthYear; // '1991' => 1991
console.log(`My age is ${myAge}`); // My age is 34
// Multiplication on string numbers
console.log("23" * "3"); // 69
// Division on string numbers
console.log("23" / "4"); // 5.75
```

Type conversion of a string that has no numeric value gives NaN

```javascript
console.log(Number("Priyavrat")); // NaN - Not a number
```

NaN is a number but not a valid number.

```javascript
console.log(typeof NaN); // Number
```

## Strict Equality Operator `===`

This operator does not do type coercion behind the scene.

```Javascript
console.log(18 === '18'); // false
console.log(18 === 18); //true
```

## Functions

It is a piece of code that we can use over and over again. It is little bit like variable but whole chunk of code.

**Note:** _Variable_ can hold a value but _Function_ can hold lines of code

```javascript
// defining the function
function logger() {
  console.log("My name is Priyavrat");
}
// calling / invoking
logger();
```
