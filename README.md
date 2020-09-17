# TypeScript Workshop #1
Clone this repo and run `npm install` to get started. You shouldn't have to modify `tsconfig.json` in order to complete this workshop.

## Reading TypeScript
For each of the variables below, state both the JavaScript type and the TypeScript type of the variable and explain why it is so:

```typescript
const first = 10;
const second = 100 * 20;
const third = typeof first;
const fourth = Math.random();
const fifth = fourth > 0.5;
const sixth = fifth ? 'yes' : 'no';
const seventh = () => Math.random();
const eigth = seventh;
const ninth = eigth();
const tenth = [];
const eleventh = [1, 10, 100];
const twelfth = eleventh.map(x => x.toFixed(2));

interface Person {
  firstName: string;
  lastName: string;
}
const thirteenth = {
  firstName: 'John',
  lastName: 'Smith'
};

const fourteenth: number = 'hello' as any as number;
```

## Functions

Create a TypeScript file in the `answers` directory for each of the following questions. In it, provide the implementation of the requested function. Then, write a series of `console.log` calls to test that your function is doing the right thing. While writing type annotations, please ensure that you take full advantage of TypeScript's type inference, and only write annotations where they are necessary. In addition to being correct from a JavaScript perspective, your answers shouldn't contain any TypeScript errors. To test your code, if you have a TypeScript file called e.g. `answers/first-charater.ts`, then open a terminal and execute `npx ts-node answers/first-character.ts`

* Using a **function declaration statement**, write a function called `firstCharacter` that takes a string and returns the first character of the string. Test your function on a few inputs, including the empty string.
* Using a **function expression**, write a function called `lastCharacter` that takes a string and returns the last character of the string. Test your function on a few inputs, including the empty string.
* Using an arrow function, rite a function called `sum` that takes two numbers and adds them together. Test your function on a few inputs.
* Write a function called `calculator` that takes a string, and two numbers. If the string is ‘add’, then return the sum of the numbers. If the string is ‘subtract’, return the difference. If the string is ‘mult’, return the product. If the string is ‘div’, return the ratio. Your function shouldn't accept anything other than these four strings.
* Write a function called `largestNumber` that takes an array of numbers, and returns the largest number of the array. Test your function on a few inputs.
* Write a function called `truthyValues` that takes an array of arbitrary elements, and returns a filtered array. The filtered array should only contain the truthy values from the initial array. You can use [`Array.prototype.filter`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter) to accomplish this. Test your function on a few inputs.
* Write a function called `sumArray` that takes an array of numbers, and returns the sum of all the numbers in the array.
* **Mini Challenge**: write a function called `mapNumbers` that takes an array of numbers and a function as arguments. Your function should return a new array that maps every element of the input array by passing it through the function you received as argument. You are not allowed to use `Array.map` for this challenge. In a first step, your solution should work with arrays of numbers, and a function that takes a number and returns a number. In a second step, the challenge will be to use [TypeScript Generics](https://www.typescriptlang.org/docs/handbook/generics.html) to create a similar function called `genericMap` that works with any kind of array and mapping function. Here's a "template" for the code you should be writing:

  ```typescript
  const map = /* Your code... */

  // Trying to use the numbers-only version of your function
  const numbers = [4, 8, 15, 16, 23, 42];
  const square = (n: number) => n * n;
  const numbersSquared = map(numbers, square); // The type of numbersSquared should be number[]

  const genericMap = /* Your code */
  
  // Trying to use the generic version of your function
  const elements = [-1, '5', 12, '100'];
  const convertToFixed = (el: string | number) => {
    let aNumber = el;
    if (typeof aNumber === 'string') {
      aNumber = parseFloat(aNumber);
    }

    return aNumber.toFixed(2);
  };

  const converted = genericMap(elements, convertToFixed); // The type of converted should be string[]
  ```