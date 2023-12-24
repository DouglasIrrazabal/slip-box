# Arrays in TypeScript
Arrays in TypeScript are a data structure that allows you to store and manipulate collections of elements. They are similar to arrays in other programming languages but come with the added benefits of static typing and additional features introduced by TypeScript.

## Declaration
In TypeScript, you can declare an array using the following syntax:
```ts
// Square Brackets
const myArray: number[] = [1, 2, 3, 4, 5];

// The 'Array' Keyword
const myArray: Array<number> = [1, 2, 3, 4, 5];
```

## Static Typing
One of the key features of TypeScript is static typing. You can specify the type of elements that the array will hold. This helps catch potential errors during development and improves code readability.
```ts
const numbers: number[] = [1, 2, 3]; // Valid
const numbers: number[] = [1, 2, "three"]; // Error: Type 'string' is not assignable to type 'number'
```

## Readonly Arrays
Arrays can be made readonly to prevent modification after initialization
```ts
const readonlyNumbers: readonly number[] = [1, 2, 3];
```

## Tuple
Allows you to express an array where the type of a fixed number of elements is known, but need not be the same.
```ts
// Function returning both a string and its length
function getStringInfo(input: string): [string, number] {
    return [input, input.length];
}

// Using the function
const result = getStringInfo("Hello, TypeScript!");

// Accessing tuple elements
const str: string = result[0];    // "Hello, TypeScript!"
const length: number = result[1];  // 18
```

## Array Methods
TypeScript supports the array methods you might be familiar with from JavaScript. These methods can be used to manipulate and iterate over arrays.

### `forEach` 🔄
Used for iterating over each element in the array and performing a specified action.
```ts
// Example
const numbers = [1, 2, 3];
numbers.forEach(num => console.log(num));
// Output: 1, 2, 3
```

### `map` 🗺️
Used for transforming each element in an array and creating a new array with the results.
```ts
// Example
const numbers = [1, 2, 3];
const doubledNumbers = numbers.map(num => num * 2);
// doubledNumbers: [2, 4, 6]
```

### `filter` 🧹
Used for creating a new array with elements that satisfy a specific condition.
```ts
// Example
const numbers = [1, 2, 3, 4, 5];
const evenNumbers = numbers.filter(num => num % 2 === 0);
// evenNumbers: [2, 4]
```

### `reduce` ➡️
Used for reducing an array to a single value by applying a function to each element.
```ts
// Example
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, num) => acc + num, 0);
// sum: 10
```

### `find` 🔍
Used for finding the first element in the array that satisfies a given condition.
```ts
// Example
const numbers = [1, 2, 3, 4, 5];
const firstEvenNumber = numbers.find(num => num % 2 === 0);
// firstEvenNumber: 2
```

### `indexOf` and `lastIndexOf` 🔍🔚
`indexOf` is used for finding the index of the first occurrence of a specified element. `lastIndexOf` is used for finding the index of the last occurrence of a specified element.
```ts
// Example
const fruits = ['apple', 'banana', 'orange', 'banana'];
const indexOfBanana = fruits.indexOf('banana');
// indexOfBanana: 1

const lastIndexOfBanana = fruits.lastIndexOf('banana');
// lastIndexOfBanana: 3
```

### `some` and `every` ✔️❌
`some` is used for checking if at least one element in the array satisfies a given condition. `every` is used for checking if all elements in the array satisfy a given condition.
```ts
// Example
const numbers = [1, 2, 3, 4, 5];
const hasEvenNumber = numbers.some(num => num % 2 === 0);
// hasEvenNumber: true

const allEvenNumbers = numbers.every(num => num % 2 === 0);
// allEvenNumbers: false
```

### `push` and `pop` ➕➖
`push` is used for adding elements to the end of an array. `pop` is used for removing the last element from an array.
```ts
// Example
const fruits = ['apple', 'banana'];
fruits.push('orange');
// fruits: ['apple', 'banana', 'orange']

const removedFruit = fruits.pop();
// removedFruit: 'orange', fruits: ['apple', 'banana']
```

### `shift` and `unshift` ⬅️➡️
`shift` is used for removing the first element from an array. `unshift` is used for adding elements to the beginning of an array.
```ts
// Example
const fruits = ['apple', 'banana'];
fruits.shift();
// fruits: ['banana']

fruits.unshift('orange');
// fruits: ['orange', 'banana']
```

### `slice` ✂️
Used for creating a shallow copy of a portion of an array.
```ts
// Example
const numbers = [1, 2, 3, 4, 5];
const slicedNumbers = numbers.slice(1, 4);
// slicedNumbers: [2, 3, 4]
```