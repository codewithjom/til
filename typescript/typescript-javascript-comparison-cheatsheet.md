# TypeScript JavaScript Comparison Cheatsheet

source: [ChatGPT](https://openai.com)

## Types

TypeScript has built-in support for type annotations, while JavaScript does not.

```typescript
// TypeScript
let myString: string;
let myNumber: number;
let myBoolean: boolean;

// JavaScript
let mystring;
let myNumber;
let myBoolean;
```

## Classes

TypeScript has classes and interfaces, while JavaScript has constructor functions and prototypes.

```typescript
// TypeScript
class MyClass {
  constructor(public myProp: string) {}
}

const myInstance = new MyClass("hello");
console.log(myInstance.myProp); // "hello"

// JavaScript
function MyClass(myProp) {
  this.myProp = myProp;
}

const myInstance = new MyClass("hello");
console.log(myInstance.myProp);
```

## Generics

TypeScript has built-in support for generics, while JavaScript does not.

```typescript
// TypeScript
function identity<T>(arg: T): T {
  return arg;
}

let output = identity<string>("myString"); // type of output will be 'string'

// JavaScript
function identity(arg) {
  return arg;
}

let output = identity("myString"); // type of output will be 'any'
```

## Enums

TypeScript has enumerations, while JavaScript does not.

```typescript
// TypeScript
enum Direction {
  Up,
  Down,
  Left,
  Right,
}

let left = Direction.Left;

// JavaScript
const Direction = {
  Up: 0,
  Down: 1,
  Left: 2,
  Right: 3,
};

let left = Direction.Left;
```

These are just a few examples of the differences between TypeScript and JavaScript. I would suggest to dig more in the documentation for more features and differences.

TypeScript is a superset of JavaScript, so any valid JavaScript code is also valid TypeScript code. However, TypeScript adds several features that can help you catch mistakes and improve the readability and maintainability of your code.

# Youtube Tutorials

- [The Net Ninja](https://www.youtube.com/watch?v=2pZmKW9-I_k&list=PL4cUxeGkcC9gUgr39Q_yD6v-bSyMwKPUI)
