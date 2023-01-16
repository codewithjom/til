# Function signatures

[https://youtu.be/TZNbzyY6hMU?list=PL4cUxeGkcC9gUgr39Q_yD6v-bSyMwKPUI](https://youtu.be/TZNbzyY6hMU?list=PL4cUxeGkcC9gUgr39Q_yD6v-bSyMwKPUI)

## Example 1

```tsx
let greet: (a: string, b: string) => void;

greet = (name: string, greeting: string) => {
  console.log(`${name} says ${greeting}`);
};
```

## Example 2

```tsx
let calc: (a: number, b: number, c: string) => number;

calc = (numOne: number, numTwo: number, action: string) => {
  if (action === 'add') {
    return numOne + numTwo;
  } else {
    return numOne - numTwo;
  }
};
```

## Example 3

```tsx
let logDetails: (obj: { name: string; age: number }) => void;

logDetails = (ninja: { name: string; age: number }) => {
  console.log(`${ninja.name} is ${ninja.age} years old`);
};
```

**or**

```tsx
let logDetails: (obj: { name: string; age: number }) => void;

type person = { name: string; age: number };

logDetails = (ninja: person) => {
  console.log(`${ninja.name} is ${ninja.age} years old`);
};
```
