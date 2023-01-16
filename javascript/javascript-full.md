# Learn JavaScript

- [Link](https://roadmap.sh/javascript/)

## Introduction

### What is JavaScript?

JavaScript, often abbreviated JS, is a programming language that is one of the core technologies of the World Wide Web, alongside HTML and CSS. It lets us add interactivity to pages e.g you might have seen sliders, alerts, click interaction, popups, etc on different websites -- all of that is built using JavaScript. Apart from being used in the browser, it is also used in other non-browser environments as well such as Node.js for writing server-side code in JavaScript, Electron for writing desktop applications, React Native for mobile applications, and so on.

## All About Variables

### Variable Declarations

To use variables in JavaScript, we first need to create it i.e declare a variable. To declare variables, we use one of the `var`, `let`, or `const` keywords.

#### var keyword

The `var` statement declares a function-scoped or globally-scoped variable, optionally initializing it to a value.

```javascript
var text = 'hello world';
```

#### let keyword

The `let` declaration declares a block-scoped local variable, optionally initializing it to a value.

```javascript
let text = 'hello world';
```

#### const keyword

Constants are block-scoped, much like variables declared using the `let` keyword. The value of a constant can't be changed throught reassignment (i.e by using the assignment operator), and it can't be redeclared (i.e through a variable declaration). However, if a constant is an objector array its properties or items can be updated or removed.

```javascript
const birthday = '05-03-01';
```

### Hoisting

JavaScript Hoisting refers to the process whereby the interpreter appears to move the declaration of functions, variables, or classes to the top of their scope, prior to execution of the code.

```javascript
function codeHoist() {
  a = 10;
  let b = 50;
}
codeHoist();

console.log(a); // 10
console.log(b); // ReferenceError : b is not defined
```

```javascript
// var code (global)
console.log(name); // undefined
var name = 'John Doe';
```

### Naming Rules

A variable name should accurately identify your variable. When you create good variable names, your JavaScript code becomes easier to understand and easier to work with. Properly naming variables is really important.

### Scopes

In JavaScript, scope refers to the visibility of a variable or how it can be used after it is declared. The scope of a variable depends on the keyword that was used to declare it.

The three types of Scope are **Global Scope**, **Function Scope**, and **Block Scope**. Before ES6(2015), JavaScript had only Global Scope and Function Scope with the `var` keyword. ES6 introduced `let` and `const` which allow Block Scope in JavaScript.

- Global Scope: Variables declared outside any function or curly braces `{}` have Global Scope, and can be accessed from anywhere within the same JavaScript code. `var`, `let`, and `const` all provides this Scope.
- Function Scope: Variables declared within a fcuntion can only be used within that same function. Outside that function, they are undefined. `var`, `let`, and `const` all provide this Scope.
- Block Scope: A block is any part of JavaScript code bounded by '{}'. Variables declared within a block can not be accessed outside that block. This Scope is only provided by the `let` and `const` keywords. If you declare a variable within a block using the `var` keyword, it will NOT have Block Scope.

#### Block Scope

This scope restricts the variable that is declared inside a specific block, from access by the outside of the block. The let & const keyword facilitates the variables to be block scoped. In order to access the variables of that specific block, we need to create an object for it. Variables declared with the var keyword, do not have block scope.

```javascript
{
  let x = 2;
}
// x can NOT be used here
```

```javascript
{
  var x = 2;
}
// x CAN be used here
```

#### Function Scope

When a variable is declared inside a function, it is only accessible within that function and cannot be used outside that function.

```javascript
function myFunction() {
  var carName = 'Volvo'; // Function Scope
}
```

```javascript
function myFunction() {
  let carName = 'Volvo'; // Function Scope
}
```

```javascript
function myFunction() {
  const carName = 'Volvo'; // Function Scope
}
```

#### Global Scope

Variables declared Globally (outside any function) have Global Scope. Global variables can be accessed from anywhere in a JavaScript program. Variables declared with `var`, `let`, and `const` are quite similar when declared outside a block.

```javascript
let carName = 'Volvo';

function myFunction() {
  // code here can also use carName
}
```

```javascript
var x = 2; // Global scope
let x = 2; // Global scope
const x = 2; // Global scope
```

## Data Types

Data type refers to the type of data that a JavaScript variable can hold. There are seven primitive data types in JavaScript (Number, BigInt, String, Boolean, Null, Undefined and Symbol). Objects are non-primitives.

### Primitive Types

In JavaScript, a primitive (primitive value, primitive data type) is data that is not an object and has no methods or properties. There are 7 primitive data types:

- `string` - [link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- `number` - [link](https://developer.mozilla.org/en-US/docs/Glossary/Number)
- `bigint` - [link](https://developer.mozilla.org/en-US/docs/Glossary/BigInt)
- `boolean` - [link](https://developer.mozilla.org/en-US/docs/Glossary/Boolean)
- `undefined` - [link](https://developer.mozilla.org/en-US/docs/Glossary/Undefined)
- `Symbol` - [link](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)
- `null` - [link](https://developer.mozilla.org/en-US/docs/Glossary/Null)

### Object

JavaScript object is a data structure that allows us to have key-value pairs; so we can have distinct keys and each key is mapped to a value that can be of any JavaScript data type. Comparing it to a real-world object, a pen is an object with several properties such as color, design, the material it is made of, etc. In the same way, JavaScript objects can have properties that define their characteristics.

```javascript
let user = new Object(); // "object constructor" syntax
let user = {}; // "object literal" syntax
```

```javascript
let user = {
  // an object
  name: 'John', // by key "name" store value "John"
  age: 30, // by key "age" store value 30
};
```

```javascript
// get property values of the object:
alert(user.name); // John
alert(user.age); // 30

delete user.age; // remove a property
```

```javascript
let user = {
  name: 'John',
  age: 30,
};

let key = prompt('What do you want to know about the user?', 'name');

// access by variable
alert(user[key]); // John (if enter "name")
```

### Built-in objects

Built-in objects, or "global objects", are those built into the language specification itself. There are numerous built-in objects with the JavaScript language, all of which are accessible at the global scope. Some examples are:

- `Number`
- `Math`
- `Date`
- `String`
- `Error`
- `Function`
- `Boolean`

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects

### TypeOf Operator

You can use the typeOf operator to find the data type of a JavaScript variable.

```javascript
console.log(typeof 42); // expected output: number
console.log(typeof 'blubber'); // expected output: string
console.log(typeof true); // expected output: boolean
console.log(typeof undeclaredVariable); // expected output: undefined
```

### Prototypes

JavaScript is an object-oriented language built around a prototype model. In JavaScript, every object inherits properties from its prototype, if there are any. A prototype is simply an object from which another object inherits properties. To create complex programs using JavaScript, one has to be proficient in working with prototypes — they form the very core of OOP in the language.

```javascript
function Point(x = 0, y = 0) {
  this.x = x;
  this.y = y;

  this.setTo = function (x, y) {
    this.x = x;
    this.y = y;
  };
}
```

## Type Casting

Type conversion (or typecasting) means the transfer of data from one data type to another. Implicit conversion happens when the compiler (for compiled languages) or runtime (for script languages like [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/JavaScript)) automatically converts data types. The source code can also explicitly require a conversion to take place.

### Type Conversion vs Coercion

Type coercion is the automatic or implicit conversion of values from one data type to another (such as strings to numbers). Type conversion is similar to type coercion because they convert values from one data type to another with one key difference — type coercion is implicit. In contrast, type conversion can be either implicit or explicit.

- [Type conversion](https://developer.mozilla.org/en-US/docs/Glossary/Type_Conversion)
- [Type coercion](https://developer.mozilla.org/en-US/docs/Glossary/Type_coercion)

### Explicit Type Casting

Type casting means transferring data from one data type to another by explicitly specifying the type to convert the given data to. Explicit type casting is normally done to make data compatible with other variables. Examples of typecasting methods are `parseInt()`, `parseFloat()`, `toString()`.

### Implicit Type Casting

Implicit type conversion happens when the compiler or runtime automatically converts data types. JavaScript is loosely type language and most of the time operators automatically convert a value to the right type.

- [GeeksForGeeks](https://www.geeksforgeeks.org/javascript-type-conversion/)
- [W3Schools](https://www.w3schools.com/js/js_type_conversion.asp)

## Data Structures

A Data structure is a format to organize, manage and store data in a way that allows efficient access and modification. JavaScript has primitive (built-in) and non-primitive (not built-in) data structures. Primitive data structures come by default with the programming language and you can implement them out of the box (like arrays and objects). Non-primitive data structures don't come by default and you have to code them up if you want to use them.

### Structured data

Structured data is used by search-engines, like Google, to understand the content of the page, as well as to gather information about the web and the world in general.

It is also coded using in-page markup on the page that the information applies to.

- [Google Developers docs](https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data)

### JSON

JavaScript Object Notation (JSON) is a standard text-based format for representing structured data based on JavaScript object syntax. It is commonly used for transmitting data in web application (e.g., sending some data from the server to the client, so it can be displayed on a web page, or vice versa).

- [JSON Tutorial Video](https://www.youtube.com/watch?v=iiADhChRriM)

### Keyed Collections

Keyed collections are data collections that are ordered by key not index. They are associative in nature. Map and set objects are keyed collections and are iterable in the order of insertion.

#### Maps

A [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) object is a simple key/value map and can iterate its elements in insertion order.

Map is a collection of keyed data items, just like an `Object`. But the main difference is that `Map` allows keys of any type.

```javascript
const sayings = new Map();
sayings.set('dog', 'woof');
sayings.set('cat', 'meow');
sayings.set('elephant', 'toot');
sayings.size; // 3
sayings.get('dog'); // woof
sayings.get('fox'); // undefined
sayings.has('bird'); // false
sayings.delete('dog');
sayings.has('dog'); // false

for (const [key, value] of sayings) {
  console.log(`${key} goes ${value}`);
}
// "cat goes meow"
// "elephant goes toot"

sayings.clear();
sayings.size; // 0
```

#### Weak map

[WeakMap](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/WeakMap) is a Map-like collection of key/value pairs whose keys must be objects, it removes them once they become inaccessible by other means.

```javascript
const privates = new WeakMap();

function Public() {
  const me = {
    // Private data goes here
  };
  privates.set(this, me);
}

Public.prototype.method = function () {
  const me = privates.get(this);
  // Do stuff with private data in `me`
  // …
};

module.exports = Public;
```

#### Set

The `Set` object lets you store unique values of any type, whether [primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) values or object references. A value in the `Set` may only occur once; it is unique in the `Set`'s collection.

```javascript
const mySet = new Set();
mySet.add(1);
mySet.add('some text');
mySet.add('foo');

mySet.has(1); // true
mySet.delete('foo');
mySet.size; // 2

for (const item of mySet) {
  console.log(item);
}
// 1
// "some text"
```

#### WeakSet

`WeakSet` objects are collections of objects. Just as with `Sets`, each object in a `WeakSet` may occur only once; all objects in a `WeakSet`'s collection are unique.

```javascript
const mySet = new Set();
mySet.add(1);
mySet.add('some text');
mySet.add('foo');

mySet.has(1); // true
mySet.delete('foo');
mySet.size; // 2

for (const item of mySet) {
  console.log(item);
}
// 1
// "some text"
```

### Indexed collections

Indexed Collections are collections that have numeric indeces i.e the collections of data that are ordered by an index value. In JavaScript, an array is an indexed collection. An array is an ordered set of values that has a numeric index.

#### Arrays

Arrays are objects that store a collection of items and can be assigned to a variable. They have their methods that can perform operations on the array.

```javascript
let arr = new Array();
let arr = [];
```

```javascript
let fruits = ['Apple', 'Orange', 'Plum'];
```

```javascript
let fruits = ['Apple', 'Orange', 'Plum'];
alert(fruits[0]); // Apple
alert(fruits[1]); // Orange
alert(fruits[2]); // Plum
```

```javascript
fruits[2] = 'Pear'; // now ["Apple", "Orange", "Pear"]
```

```javascript
fruits[3] = 'Lemon'; // now ["Apple", "Orange", "Pear", "Lemon"]
```

```javascript
let fruits = ['Apple', 'Orange', 'Plum'];
alert(fruits.length); // 3
```

## Equality Comparisons

Comparison operators are used in logical statements to determine equality or difference between variables or values. Comparison operators can be used in conditional statement to compare values and take action depending on the result.

Assume that `x = 5`:

| Operator | Description                       | Comparing | Returns |
| -------- | --------------------------------- | --------- | ------- |
| ==       | equal to                          | x == 8    | false   |
| ===      | equal value and equal type        | x === 5   | true    |
| !=       | not equal                         | x != 8    | true    |
| !==      | not equal value or not equal type | x !== 5   | false   |
| >        | greater than                      | x > 8     | false   |
| <        | less than                         | x < 8     | true    |
| >=       | greater than or equal to          | x >= 8    | false   |
| <=       | less than or equal to             | x <= 8    | true    |

## Loops and Iterations

Loops offer a quick and easy way to do something repeatedly.

You can think of a loop as a computerized version of the game where you tell someone to take X steps in one direction, then Y steps in another. For example, the idea "Go five steps to the east" could be expressed this way as a loop:

```javascript
for (let step = 0; step < 5; step++) {
  // Runs 5 times, with values of step 0 through 4.
  console.log('Walking east one step');
}
```

### for statement

The `for` loop is a standard control-flow construct in many programming languages, including JavaScript. It's commonly used to iterate over given sequences or iterate a known number of times and execute a piece of code for each iteration.

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

### do...while statement

The `do...while` statement creates a loop that executes a specified statement until the test condition evaluates to `false`. The condition is evaluated after executing the statement, resulting in the specified statement executing at least once.

```javascript
let result = '';
let i = 0;

do {
  i = i + 1;
  result = result + i;
} while (i < 5);

console.log(result);
// Expected output: "12345"
```

### while statement

The `while` statement creates a loop that executes a specified statement as long as the test condition evaluates to `true`. The condition is evaluated before executing the statement.

```javascript
let n = 0;

while (n < 3) {
  n++;
}

console.log(n);
// expected output: 3
```

### for...in statement

The for...in statement iterates over all enumerable properties of an object that are keyed by strings (ignoring ones keyed by Symbols), including inherited enumerables properties

```javascript
const object = { a: 1, b: 2, c: 3 };

for (const property in object) {
  console.log(`${property}: ${object[property]}`);
}

// expected output:
// "a: 1"
// "b: 2"
// "c: 3"
```

### for...of statement

The for...of statement executes a loop that operates on a sequence of values sourced from an iterable object. Iterable objects include instances of built-ins such as Array, String, TypedArray, Map, Set, NodeList (and other DOM collections), and the arguments object, generators produced by generator functions, and user-defined iterables.

```javascript
const array1 = ['a', 'b', 'c'];

for (const element of array1) {
  console.log(element);
}

// expected output: "a"
// expected output: "b"
// expected output: "c"
```

### Break continue

`break` statement, without a label reference, can only be used to jump out of a loop or a switch block.

`continue` statement, with or without a label reference, can only be used to skip one loop iteration.

```javascript
let i = 0;

while (i < 6) {
  if (i === 3) {
    break;
  }
  i = i + 1;
}

console.log(i);
// expected output: 3
```

```javascript
let text = '';

for (let i = 0; i < 10; i++) {
  if (i === 3) {
    continue;
  }
  text = text + i;
}

console.log(text);
// expected output: "012456789"
```

### Labeled Statements

JavaScript label statements are used to prefix a label to an identifier. It can be used with `break` and `continue` statement to control the flow more precisely.

A label is simply an identifier followed by a colon `(:)` that is applied to a block of code.

```javascript
let str = '';

loop1: for (let i = 0; i < 5; i++) {
  if (i === 1) {
    continue loop1;
  }
  str = str + i;
}

console.log(str);
// expected output: "0234"
```

## Control Flow

In JavaScript, the `Control flow` is a way of how your computer runs code from top to bottom. It starts from the first line and ends at the last line unless it hits any statement that changes the control flow of the program such as loops, conditionals, etc.

We can control the flow of the program through any of these control structures:

- Sequential (default mode)
- Conditional Statements
- Exception Handling
- Loops and Iterations

### Conditional statements

When you write code, you often want to perform different actions for different decisions. You can use conditional statements in your code to do this. In JavaScript, we have three conditional statements: `if`, `if...else`, and `switch`.

```javascript
if (year == 2023) {
  alert("That's correct!");
  alert("You're so smart!");
}
```

```javascript
let shoppingDone = false;
let childsAllowance;

if (shoppingDone === true) {
  childsAllowance = 10;
} else {
  childsAllowance = 5;
}
```

```javascript
let year = prompt(
  'In which year was the ECMAScript-2015 specification published?',
  ''
);

if (year < 2015) {
  alert('Too early...');
} else if (year > 2015) {
  alert('Too late');
} else {
  alert('Exactly!');
}
```

```javascript
const expr = 'Papayas';
switch (expr) {
  case 'Oranges':
    console.log('Oranges are $0.59 a pound.');
    break;
  case 'Mangoes':
  case 'Papayas':
    console.log('Mangoes and papayas are $2.79 a pound.');
    // expected output: "Mangoes and papayas are $2.79 a pound."
    break;
  default:
    console.log(`Sorry, we are out of ${expr}.`);
}
```

### Exception Handling

In JavaScript, all exceptions are simply objects. While the majority of exceptions are implementations of the global Error class, any old object can be thrown. With this in mind, there are two ways to throw an exception: directly via an Error object, and through a custom object. (excerpt from Rollbar)

```javascript
throw new Error('Exception message');
```

```javascript
function CustomException(message) {
  const error = new Error(message);

  error.code = 'THIS_IS_A_CUSTOM_ERROR_CODE';
  return error;
}

CustomException.prototype = Object.create(Error.prototype);
```

```javascript
function CustomException(message) {
  const error = new Error(message);
  return error;
}

CustomException.prototype = Object.create(Error.prototype);
```

```javascript
throw new CustomException('Exception message');
```

#### Throw Statement

The throw statement throws a user-defined exception. Execution of the current function will stop (the statement after throw won't be executed), and control will be passed to the first catch block in the call stack. If no catch block exists among caller functions, the program will terminate.

#### Try, Catch, Finally

These are ways of handling errors in your JavaScript code. Inside the try code block we have the code to run, inside the catch block we handle the errors, and inside the finally block we have code that runs after the execution of the previous code blocks, regardless of the result.

```javascript
function myFunction() {
  const message = document.getElementById('p01');
  message.innerHTML = '';
  let x = document.getElementById('demo').value;
  try {
    if (x.trim() == '') throw 'is empty';
    if (isNaN(x)) throw 'is not a number';
    x = Number(x);
    if (x > 10) throw 'is too high';
    if (x < 5) throw 'is too low';
  } catch (err) {
    message.innerHTML = 'Error: ' + err + '.';
  } finally {
    document.getElementById('demo').value = '';
  }
}
```

#### Utilizing error objects

When a runtime error occurs, a new `Error` object is created and thrown. With this `Error` object, we can determine the type of the Error and handle it according to its type.

**Types of Errors**: Besides error constructors, JavaScript also has other core Error constructors.

- [AggregateError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError)
- [EvalError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/EvalError)
- [InternalError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/InternalError)
- [RangeError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RangeError)
- [ReferenceError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError)
- [SyntaxError](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError)

```javascript
try {
  willGiveErrorSometime();
} catch (error) {
  if (error instanceof RangeError) {
    rangeErrorHandler(error);
  } else if (error instanceof ReferenceError) {
    referenceErrorHandle(error);
  } else {
    errorHandler(error);
  }
}
```

## Expressions and Operators

At a high level, an expression is a valid unit of code that resolves to a value. There are two types of expressions: those that have side effects (such as assigning value) and those that purely evaluate. The expression `x = 7` is an example of the first type. This expression uses the `=` operator to assign the value seven to the variable x. The expression itself evaluates to 7. The expression `3 + 4` is an example of the second type. This expression uses the `+` operator to add `3` and `4` together and produces a value `7`. However, if it's not eventually part of a bigger construct (for example, a variable declaration like const `z = 3 + 4`), its result will be immediately discarded `-` this is usually a programmer mistake because the evaluation doesn't produce any effects. As the examples above also illustrate, all complex expressions are joined by operators, such as `=` and `+`.

### Assignment Operators

An assignment operator assigns a value to its self operand based on the value of its right operand. The simple assignment operator is equal (`=`), which assigns the value of its right operand to its left operand. That is, `x = f()` is an assignment expression that assigns the value of `f()` to `x`.

### Comparison Operators

Comparison operators are the operators that compare values and return true or false. The operators include: `>`, `<`, `<=`, `>=`, `==`, `===`, `!=`, and `!==`

- [W3Schools](https://www.w3schools.com/js/js_comparisons.asp)

### Arithmetic Operators

The Arithmetic operators perform addition, subtraction, multiplication, division, exponentiation, and remainder operations.

Arithmetic operators in JavaScript are as follows:

- `+` - Addition
- `-` - Subtraction
- `*` - Multiplication
- `**` - Exponentiation
- `/` - Division
- `%` - Modulus i.e. Remainder
- `++` - Increment
- `--` - Decrement

### Bitwise Operators

Bitwise operators treat arguments as 32-bits (zeros & ones) and work on the level of their binary representation. Ex. Decimal number `9` has a binary representation of `1001`. Bitwise operators perform their operations on such binary representations, but they return standard JavaScript numeric values.

Bitwise operators in JavaScript are as follows:

- `&` - AND
- `|` - OR
- `^` - XOR
- `~` - NOT
- `<<` - Left SHIFT
- `>>` - Right SHIFT
- `>>>` - Zero-Fill Right SHIFT
- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#bitwise_operators)

### Logical Operators

There are four logical operators in JavaScript: `||` OR, `&&` AND, `!` NOT, `??` Nullish Coalescing.

- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#logical_operators)

### BigInt Operators

Most operators that can be used with the `Number` data type will also work with `BigInt` values (e.g. arithmetic, comparison, etc.). However, the unsigned right shift `>>>` operator is an exception and is not supported. Similarly, some operators may have slight differences in behaviour (for example, division with `BigInt` will round towards zero).

- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#bigint_operators)

### String Operators

In addition to the comparison operators, which can be used on string values, the concatenation operator (`+`) concatenates two string values together, returning another string that is the union of the two operand strings.

The shorthand assignment operator `+=` can also be used to concatenate strings.

- [JavaScript.info](https://javascript.info/operators#string-concatenation-with-binary)

### Conditional Operators

Conditional operator also known as Ternary operator is the only JS operator that takes three operands.

The operator can have one of two values based on a condition.

**Syntax**: `condition ? val_for_true : val_for_false`

- [W3Schools](https://www.w3schools.com/js/js_comparisons.asp)

### Comma operators

The comma operator (`,`) evaluates each of its operand (from left to right) and returns the value of the last operand. This lets you create a compound expression's final value being the value of the rightmost of its member expressions. This is commonly used to provide multiple parameters to a `for` loop.

```javascript
let x = 1;

x = (x++, x);

console.log(x);
// expected output: 2

x = (2, 3);

console.log(x);
// expected output: 3
```

### Unary Operators

JavaScript Unary Operators are the special operators that consider a single operand and perform all the types of operations on that single operand. These operators include unary plus, unary minus, prefix increments, postfix increments, prefix decrements, and postfix decrements.

- [Link](https://www.educba.com/unary-operators-in-javascript/)

### Relational Operators

Relational operators are also known as comparison operators. They are used to find the relationship between two values or compare the relationship between them; on the comparison, they yield the result true or false.

- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#relational_operators)

## Functions

Functions exists so we can reuse code. They are block of code that execute whenever they are invoked. Each function is typically written to perform a particular task, like an addition function used to find the sum of two or more numbers. When numbers need to be added anywhere within your code, the addition function can be invoked as many times as necessary.

### Function Parameters

The parameter is the name given to the variable declared inside the definition of a function. There are two special kinds of syntax: default and rest parameters.

#### Default Parameters

Default function parameters allow named parameters to be initialized with default values if no value or `undefined` is passed.

```javascript
function multiply(a, b = 1) {
  return a * b;
}

console.log(multiply(5, 2));
// expected output: 10

console.log(multiply(5));
// expected output: 5
```

#### Rest Parameters

The rest parameters syntax allows a function to accept an indefinite number of arguments as an array, providing a way to represent [variadic functions](https://en.wikipedia.org/wiki/Variadic_function) in JavaScript.

```javascript
function sum(...theArgs) {
  let total = 0;
  for (const arg of theArgs) {
    total += arg;
  }
  return total;
}

console.log(sum(1, 2, 3));
// expected output: 6

console.log(sum(1, 2, 3, 4));
// expected output: 10
```

### Arrow Functions

Arrow Function is a new way of creating functions with the `=>` operator with a shorter syntax.

```javascript
hello = () => {
  return 'Hello World!';
};
```

### Built in Functions

- A JavaScript **method** is a property containing a **function definition**. In other words, when the data stored on an object is a function we call that a method.
- To differentiate between properties and methods, we can think of it this way: **A property is what an object has, while a method is what an object does**.
- Since JavaScript methods are actions that can be performed on objects, we first need to have objects to start with. There are several objects built into JavaScript which we can use.
- [Link](https://www.tutorialspoint.com/javascript/javascript_builtin_functions.htm)

## Asynchronous JavaScript

Asynchronous programming is a technique that enables your program to start a potentially long-running task and still be able to be responsive to other events while that task runs, rather than having to wait until that task has finished. Once that task has finished, your program is presented with the result.

Many functions provided by browsers, especially the most interesting ones, can potentially take a long time, and therefore, are asynchronous. For example:

- Making HTTP requests using `fetch()`
- Accessing a user's camera or microphone using `getUserMedia()`
- Asking a user to select files using `showOpenFilePicker()`

So even though you may not have to implement your own asynchronous functions very often, you are very likely to need to use them correctly.

### setTimeout

The setTimeout runs a function after the specified period expires. Times are declared in milliseconds.

```javascript
const myTimeout = setTimeout(myGreeting, 5000); // 5 seconds
```

```javascript
const myTimeout = setTimeout(myGreeting, 5000);

function myStopFunction() {
  clearTimeout(myTimeout);
}
```

### setInterval

The `setInterval()` method helps us to repeatedly execute a function after a fixed delay. It returns a unique interval ID which can later be used by the `clearInterval()` method, which stops further repeated execution of the function.

`setInterval()` is similar to setTimeout, with a difference. Instead of running the callback function once, it will run it forever, at the specific time interval you specify (in milliseconds):

- [GeeksforGeeks](https://www.geeksforgeeks.org/what-is-setinterval-in-javascript/)

### Callbacks

A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routing or action.

- [javascript.info](https://javascript.info/callbacks)

#### Callback Hell

The callback hell is when we try to write asynchronous JavaScript in a way where execution happens visually from top to bottom, creating a code that has a pyramid shape with many }) at the end.

```javascript
fs.readdir(source, function (err, files) {
  if (err) {
    console.log('Error finding files: ' + err);
  } else {
    files.forEach(function (filename, fileIndex) {
      console.log(filename);
      gm(source + filename).size(function (err, values) {
        if (err) {
          console.log('Error identifying file size: ' + err);
        } else {
          console.log(filename + ' : ' + values);
          aspect = values.width / values.height;
          widths.forEach(
            function (width, widthIndex) {
              height = Math.round(width / aspect);
              console.log(
                'resizing ' + filename + 'to ' + height + 'x' + height
              );
              this.resize(width, height).write(
                dest + 'w' + width + '_' + filename,
                function (err) {
                  if (err) console.log('Error writing file: ' + err);
                }
              );
            }.bind(this)
          );
        }
      });
    });
  }
});
```

- [Callback Hell](http://callbackhell.com/)

### Promises

Promises are much better way to work with asynchronous code in JavaScript than the old and error-prone callback approach. They were introduce into JavaScript with ECMAScript 6. Using promises, we can manage extremely complex asynchronous code with regorous error-handling setup, write code in a more or less synchronous style, and keep ourselves from running into the so-called callback hell.

- [A Detailed Introduction to Promises](https://www.codeguage.com/courses/advanced-js/promises-introduction)
- [JavaScript Promises - Basics](https://www.codeguage.com/courses/advanced-js/promises-basics)
- [JavaScript Promises - Chaining](https://www.codeguage.com/courses/advanced-js/promises-chaining)
- [JavaScript Promises - Error Handling](https://www.codeguage.com/courses/advanced-js/promises-error-handling)

#### Async/Await

`async/await` is a special syntax to work with promises in a more comfortable fashion. We use `async` keyword to declare an async function that return a Promise, and the `await` keyword makes a function wait for a Promise.

- [Async/await](https://javascript.info/async-await)
- [freecodecamp](https://www.freecodecamp.org/news/javascript-async-await-tutorial-learn-callbacks-promises-async-await-by-making-icecream/)
