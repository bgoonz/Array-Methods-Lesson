# Array Methods Explained In Emojis

## Array Methods Explained As Emojis

### 1. `Array.push()` <a href="62c7" id="62c7"></a>

Adds one or more elements to the end of an array. Or grows a farm.

````js
let livestock = ["🐷", "🐮", "🐔"];livestock.push("🐴", "🐮");// console.log(livestock);// ["🐷", "🐮", "🐔", "🐴", "🐮"]

```js

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/push)

## 2. `Array.from()` <a href="d4a8" id="d4a8"></a>

Creates a new array from an array-like or iterable object. Or separates some wild animals.


```js
const wild  = "🐻🐯🦁";const tamed = Array.from(wild);// console.log(tamed);// ["🐻", "🐯", "🦁"]
````

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/from)

### 3. `Array.concat()` <a href="d75d" id="d75d"></a>

Merges two or more arrays into a single new one. Or brings different worlds together.

```js
const dogs = ["🐶", "🐶"];const cats = ["🐱", "🐱", "🐱"];const pets = dogs.concat(cats);// console.log(pets);// ["🐶", "🐶", "🐱", "🐱", "🐱"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/concat)

### 4. `Array.every()` <a href="8409" id="8409"></a>

Checks if all elements of an array pass the test. Or detects intruders.

```js
const visitors   = ["🧑", "👽", "🧑", "🧑", "🤖"];const isHuman    = e => e === "🧑";const onlyHumans = visitors.every(isHuman);// console.log(onlyHumans);// false
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/every)

### 5. `Array.fill()` <a href="e15c" id="e15c"></a>

Replaces the elements of an array from start to end index with a given value. Or grows some trees.

```js
let seeds = ["🌱", "🌱", "🌱", "🌱", "🌱"];seeds.fill("🌳", 1, 4);// console.log(seeds);// ["🌱", "🌳", "🌳", "🌳", "🌱"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/fill)

### 6. `Array.filter()` <a href="1368" id="1368"></a>

Creates a new array containing all elements passing the test. Or predicts your relationship status.

```js
const guests  = ["👩👨", "👩👩", "👨", "👩", "👨👨"];const singles = guests.filter(g => g.length/2 === 1); // *// console.log(singles);// ["👨", "👩"]
```

_\* You might wonder, why the string length is divided by two here. The reason is that emojis actually are represented by a pair of code points, also known as a surrogate pair._\
_Try `"👩".length` in your console and see for yourself. More information in _[_this article_](https://thekevinscott.com/emojis-in-javascript/)_._

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/filter)

### 7. `Array.flat()` <a href="b047" id="b047"></a>

Creates a new array containing all elements from all sub-arrays up to a given depth. Or cracks any safe.

```js
const savings = ["💵", ["💵", "💵"], ["💵", "💵"], [[["💰"]]]];const loot    = savings.flat(3)// console.log(loot);// ["💵", "💵", "💵", "💵", "💵", "💰"];
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/flat)

### 8. `Array.includes()` <a href="2183" id="2183"></a>

Checks if an array contains a specific element. Or finds the secret sweet tooth.

```js
const food   = ["🥦", "🥬", "🍅", "🥒", "🍩", "🥕"];const caught = food.includes("🍩");// console.log(caught);// true
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/includes)

### 9. `Array.join()` <a href="4d6a" id="4d6a"></a>

Concatenates all array elements to one single string, using an optional separator. Or builds local area networks.

```js
const devices = ["💻", "🖥️", "🖥️", "💻", "🖨️"];const network = devices.join("〰️");// console.log(network);// "💻〰️🖥️〰️🖥️〰️💻〰️🖨️"
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/join)

### <mark style="background-color:red;">10.</mark> <mark style="color:red;">`Array.map()`</mark> <a href="d50b" id="d50b"></a>

Calls a function on each array element and returns the result as new array. Or feeds all hungry monkeys.

```js
const hungryMonkeys = ["🐒", "🦍", "🦧"];const feededMonkeys = hungryMonkeys.map(m => m + "🍌");// console.log(feededMonkeys);// ["🐒🍌", "🦍🍌", "🦧🍌"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/map)

### 11. `Array.reverse()` <a href="3068" id="3068"></a>

Reverses the order of elements in an array. Or decides the outcome of a race.

```js
let   rabbitWins   = ["🐇", "🦔"];const hedgehogWins = rabbitWins.reverse();// console.log(hedgehogWins);// ["🦔", "🐇"]
```

_Note that this method is destructive, it modifies the original array. So after line 2 of this example `rabbitWins` and `hedgehogWins` both have the value_ `["🦔", "🐇"]`

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/reverse)

### 12. `Array.slice()` <a href="06be" id="06be"></a>

Creates a new array from copying a portion of an array defined by start and end index. Or cheats in an exam.

```js
const solutionsOfClassmates = ["📃", "📑", "📄", "📝"];const myOwnSolutionReally   = solutionsOfClassmates.slice(2, 3);// console.log(myOwnSolutionReally);// ["📄"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/slice)

### 13. `Array.some()` <a href="d5da" id="d5da"></a>

Tests if at least one element of an array passes the test. Or finds if some participants of your meeting forgot to mute their mic.

```js
const participants = ["🔇", "🔇", "🔊", "🔇", "🔊"];const isLoud       = p => p === "🔊";const troubles     = participants.some(isLoud);// console.log(troubles);// true
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/some)

### 14. `Array.sort()` <a href="ac6a" id="ac6a"></a>

Sorts all elements of an array. Or organizes your bookshelf again.

```js
let books = ["📕", "📗", "📕", "📒", "📗", "📒"];books.sort();// console.log(books);// ["📒", "📒", "📕", "📕", "📗", "📗"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/sort)

### 15. `Array.splice()` <a href="37a2" id="37a2"></a>

Removes, replaces or adds elements to an array. Or changes the weather.

```js
let weather = ["☁️", "🌧️", "☁️"];weather.splice(1, 2, "☀️");// console.log(weather);// ["☁️", "☀️"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/splice)

### 16. `Array.unshift()` <a href="f157" id="f157"></a>

Adds one or more elements to the beginning of an array. Or couples a loco.

```js
let train = ["🚃", "🚃", "🚃", "🚃"];train.unshift("🚂");// console.log(train);// ["🚂", "🚃", "🚃", "🚃", "🚃"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/unshift)
