---
cover: .gitbook/assets/reduce (1).png
coverY: 0
description: 'Github Repo: https://github.com/bgoonz/Array-Methods-Lesson'
---

# Home

<mark style="color:orange;">map</mark>(\[<mark style="background-color:red;">🌽, 🐮, 🐔</mark>], <mark style="background-color:blue;">cook</mark>) => <mark style="background-color:green;">\[🍿, 🍔, 🍳]</mark>

<mark style="color:orange;">filter</mark>(\[<mark style="background-color:red;">🍿, 🍔, 🍳</mark>], <mark style="background-color:blue;">isVegetarian</mark>) => <mark style="background-color:green;">\[🍿, 🍳]</mark>

<mark style="color:orange;">reduce</mark>(\[<mark style="background-color:red;">🍿, 🍳</mark>], <mark style="background-color:blue;">eat</mark>) => <mark style="background-color:green;">💩</mark>

### <mark style="color:red;background-color:blue;">DOWNLOAD JS FILES FOR LESSON:</mark>

{% file src=".gitbook/assets/array-methods (1).zip" %}
download-js-files
{% endfile %}

{% embed url="https://bryan-guner.gitbook.io/array-methods-lesson" %}
Public Web Address
{% endembed %}

{% embed url="https://github.com/bgoonz/Array-Methods-Lesson" %}
Corresponding Github Repository
{% endembed %}

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}

<mark style="color:orange;">map</mark>(\[<mark style="background-color:red;">🌽, 🐮, 🐔</mark>], <mark style="background-color:blue;">cook</mark>) => <mark style="background-color:green;">\[🍿, 🍔, 🍳]</mark>

<mark style="color:orange;">filter</mark>(\[<mark style="background-color:red;">🍿, 🍔, 🍳</mark>], <mark style="background-color:blue;">isVegetarian</mark>) => <mark style="background-color:green;">\[🍿, 🍳]</mark>

<mark style="color:orange;">reduce</mark>(\[<mark style="background-color:red;">🍿, 🍳</mark>], <mark style="background-color:blue;">eat</mark>) => <mark style="background-color:green;">💩</mark>

![](<.gitbook/assets/Array Methods\_Instructor Position Assessment-1.png>) ![](<.gitbook/assets/Array Methods\_Instructor Position Assessment-2.png>) ![](<.gitbook/assets/Array Methods\_Instructor Position Assessment-3.png>) ![](<.gitbook/assets/Array Methods\_Instructor Position Assessment-4.png>)

## Table of contents

* [Home](https://bryan-guner.gitbook.io/array-methods-lesson/README)

### Methods

### 👨💻 Methods

* [Page 1](https://bryan-guner.gitbook.io/array-methods-lesson/methods-1/page-1)
* [Array.forEach()](https://bryan-guner.gitbook.io/array-methods-lesson/methods-1/array.foreach)
* [Array.filter()](https://bryan-guner.gitbook.io/array-methods-lesson/methods-1/array.filter)

### Aux Information

* [Array Methods Explained As Emojis](https://bryan-guner.gitbook.io/array-methods-lesson/aux-information/array-methods-explained-as-emojis)
* [Array.reduce()](https://bryan-guner.gitbook.io/array-methods-lesson/aux-information/array.reduce)
* [Array.map()](https://bryan-guner.gitbook.io/array-methods-lesson/aux-information/array.map)

### Background

* [Mutability](https://bryan-guner.gitbook.io/array-methods-lesson/background/mutability)
* [Array Basics](https://bryan-guner.gitbook.io/array-methods-lesson/background/array-basics)
* [🔙 Background](https://bryan-guner.gitbook.io/array-methods-lesson/background/background)
* [Callback Functions](https://bryan-guner.gitbook.io/array-methods-lesson/background/callback-functions)
* [Higher Order Functions](https://bryan-guner.gitbook.io/array-methods-lesson/background/higher-order-functions)
* [🧘 Difference Between Functions & Methods...](https://bryan-guner.gitbook.io/array-methods-lesson/background/difference-between-functions-and-methods...)
* [➡ Fat Arrow Syntax](https://bryan-guner.gitbook.io/array-methods-lesson/background/fat-arrow-syntax)

### 📖 Resources

* [Array Methods Explained In Emojis](https://bryan-guner.gitbook.io/array-methods-lesson/resources/array-methods-explained-in-emojis)
* [Does It Mutate¿](https://bryan-guner.gitbook.io/array-methods-lesson/resources/does-it-mutate)
* [Cheat Sheet](https://bryan-guner.gitbook.io/array-methods-lesson/resources/cheat-sheet)
* [Other Array Methods](https://bryan-guner.gitbook.io/array-methods-lesson/resources/other-array-methods)

### 👽 Miscellaneous

* [Array Methods Explained As Emojis](https://bryan-guner.gitbook.io/array-methods-lesson/miscellaneous/array-methods-explained-as-emojis)

```
// Mutating
push()      // Insert an element at the end
pop()       // Remove an element from the end
unshift()   // Inserts an element in the beginning
shift()     // Remove first element
// Iterating
forEach()   // Iterates an array
filter()    // Iterates an array and result is filtered array
map()       // Iterates an array and result is new array
reduce()    // "Reduces" the array into single value (accumulator)
// Others
slice()     // Returns desired elements in a new array
concat()    // Append one or more arrays with given array
```



#### Cheat sheet: Arrays

JavaScript Arrays are a very flexible data structure and used as lists, stacks, queues, tuples (e.g. pairs), etc. Some

**Using Arrays**

Creating Arrays, reading and writing elements:

```js
const arr = ['a', 'b', 'c']; // Array literal
assert.deepEqual(
  arr,
  [
    'a',
    'b',
    'c', // trailing commas are ignored
  ]
);
assert.equal(
  arr.length, 3 // number of elements
);
assert.equal(
  arr[0], 'a' // read (negative indices don’t work)
);
assert.equal(
  arr.at(-1), 'c' // read (negative indices work)
);
arr[0] = 'x'; // write
assert.deepEqual(
  arr, ['x', 'b', 'c']
);
```

The lengths of Arrays, adding elements:

```js
const arr = ['a'];
assert.equal(
  arr.length, 1 // number of elements
);
arr.push('b'); // add an element (preferred)
assert.deepEqual(
  arr, ['a', 'b']
);
arr[arr.length] = 'c'; // add an element (alternative)
assert.deepEqual(
  arr, ['a', 'b', 'c']
);
arr.length = 1; // remove elements
assert.deepEqual(
  arr, ['a']
);
```

Concatenating Arrays via spreading (`...`):

```js
const arr1 = ['a', 'b'];
const arr2 = ['c'];
const arr3 = ['d', 'e', 'f'];
assert.deepEqual(
  [...arr1, ...arr2, ...arr3, 'g'],
  ['a', 'b', 'c', 'd', 'e', 'f', 'g']
);
```

Clearing Arrays (removing all elements):

```js
// Affects everyone referring to the Array
const arr1 = ['a', 'b', 'c'];
arr1.length = 0;
assert.deepEqual(
  arr1, []
);

// Does not affect others referring to the Array
let arr2 = ['a', 'b', 'c'];
arr2 = [];
assert.deepEqual(
  arr2, []
);
```

Looping over elements:

```js
const arr = ['a', 'b', 'c'];
for (const value of arr) {
  console.log(value);
}

// Output:
// 'a'
// 'b'
// 'c'
```

Looping over key-element pairs:

```js
const arr = ['a', 'b', 'c'];
for (const [index, value] of arr.entries()) {
  console.log(index, value);
}

// Output:
// 0, 'a'
// 1, 'b'
// 2, 'c'
```

Creating and filling Arrays when we can’t use Array literals (e.g. because we don’t know their lengths in advance or they are too large):

```js
const four = 4;

// Empty Array that we’ll fill later
assert.deepEqual(
  new Array(four),
  [ , , , ,] // four holes; last comma is ignored
);

// An Array filled with a primitive value
assert.deepEqual(
  new Array(four).fill(0),
  [0, 0, 0, 0]
);

// An Array filled with objects
// Why not .fill()? We’d get single object, shared multiple times.
assert.deepEqual(
  Array.from({length: four}, () => ({})),
  [{}, {}, {}, {}]
);

// A range of integers
assert.deepEqual(
  Array.from({length: four}, (_, i) => i),
  [0, 1, 2, 3]
);
```

**Array methods**

Deriving a new Array from an existing Array:

```
> ['■','●','▲'].slice(1, 3)
['●','▲']
> ['■','●','■'].filter(x => x==='■') 
['■','■']

> ['▲','●'].map(x => x+x)
['▲▲','●●']
> ['▲','●'].flatMap(x => [x,x])
['▲','▲','●','●']
```

Removing an Array element at a given index:

```js
const arr = ['■','●','▲'];

assert.deepEqual(
  arr.filter((_, index) => index !== 1),
  ['■','▲']
);
assert.deepEqual(
  arr, ['■','●','▲'] // .filter() is non-destructive
);

arr.splice(1, 1); // start at 1, delete 1 element
assert.deepEqual(
  arr, ['■','▲'] // .splice() is destructive
);
```

Computing a summary of an Array:

```
> ['■','●','▲'].some(x => x==='●')
true
> ['■','●','▲'].every(x => x==='●')
false

> ['■','●','▲'].join('-')
'■-●-▲'

> ['■','●'].reduce((result,x) => result+x, '▲')
'▲■●'
> ['■','●'].reduceRight((result,x) => result+x, '▲')
'▲●■'
```

Changing all of an Array (the input Array is modified and returned):

```
> ['■','●','▲'].fill('●')
['●','●','●']
> ['■','●','▲'].reverse()
['▲','●','■']
> ['■','●','■'].sort()
['■','■','●']
```

Finding Array elements:

```
> ['■','●','■'].includes('■')
true
> ['■','●','■'].indexOf('■')
0
> ['■','●','■'].lastIndexOf('■')
2
> ['■','●','■'].find(x => x==='■')
'■'
> ['■','●','■'].findIndex(x => x==='■')
0
```

Listing elements (`Array.from()` is needed because the methods return iterables, not Arrays):

```
> Array.from(['■','●','▲'].keys())
[0,1,2]
> Array.from(['■','●','▲'].entries())
[[0,'■'],[1,'●'],[2,'▲']]
```

Adding or removing an element at either end of an Array:

```js
const arr1 = ['■','●'];
arr1.push('▲');
assert.deepEqual(
  arr1, ['■','●','▲']
);

const arr2 = ['■','●','▲'];
arr2.pop();
assert.deepEqual(
  arr2, ['■','●']
);

const arr3 = ['■','●'];
arr3.unshift('▲');
assert.deepEqual(
  arr3, ['▲','■','●']
);

const arr4 = ['▲','■','●'];
arr4.shift();
assert.deepEqual(
  arr4, ['■','●']
);
```
