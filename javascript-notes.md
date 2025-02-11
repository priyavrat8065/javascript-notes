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
  // function body
  console.log("My name is Priyavrat");
}
// calling / invoking / running the function
logger();
```

### Parameters

Parameters are like variables that are specific only to that function. In this example _oranges_ and _apples_ are the parameters of the function `fruitProcessor()`

```javascript
function fruitProcessor(apples, oranges) {
  console.log(apples, oranges);
  const juice = `Juice with ${apples} apples and ${oranges} oranges.`;
  return juice;
}
```

## Short-circuiting in OR Operator

In the case of an OR Operator short-circuiting means if the first value is a truthy value, it will immediately return that first value. In the example below since `3` is a truthy value so it is returned immediately.

```javascript
console.log(3 || "Jonas"); // 3
```

If the first value is truthy value then javascript doesn't even look at the remaining values.
If the first value is the falsy then it looks at the next value and so on until either it reaches the last value or it encounters the first truthy value. If there is no truthy value in the circuit then it returns the last value even if it is a falsy value.

```javascript
console.log("" || null || undefined); // undefined
```

In the above code, since all the value in the circuit are falsy, it returns the last value, which is, `undefined`

```javascript
console.log("" || null || undefined || 23 || false); // 23
```

In the above code, this it returns the first truthy value it encountered and short-circuiting the rest of the evaluation.

### Use Case

Let's say there is a property called `numGuest` on the `restaurant` object but we don't know if it exists, however we want define a number of guests variable based on this property. then we can use OR operator to set that variable a default value in case `restaurant.numGuest` property doesn't exist.

```javascript
restaurant1 = {
  name: "Shiv Dhaba",
  owner: "Parminder Singh",
};
const guests = restaurant1.numGuest || 10;
// otherwise we would achieve the same result using ternary operator
const guests1 = restaurant1.numGuest ? restaurant1.numGuest : 10;
```

If `restaurant2.numGuest` exists, then the default value will be ignored.

```javascript
restaurant2 = {
  name: "Green Valley",
  numGuest: 23,
};
const guests2 = restaurant2.numGuest || 10; // 23
```

## Nullish coalescing operator

Suppose there is another object that has `restaurant3.numGuest` property is equal to zero. In that case since zero is a falsy value
it won't short-circuit the evaluation and it returns the default value. So how to deal with that problem? We use Nullish coalescing operator `??` instead. This operator only short-circuit when either there is null or undefined value. All other values are truthy value for that operator.

```javascript
restaurant3 = {
  name: "Doab Vilas",
  numGuest: 0,
};
const guest4 = restaurant3.numGuest || 10; // 10
// how to fix this?
const guest5 = restaurant3.numGuest ?? 10; // 0
```
