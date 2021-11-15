# Array Methods Explained As Emojis



### 1. `Array.push()`

Adds one or more elements to the end of an array. Or grows a farm.\


```
let livestock = ["🐷", "🐮", "🐔"];
livestock.push("🐴", "🐮");
// console.log(livestock);
// ["🐷", "🐮", "🐔", "🐴", "🐮"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/push)

### 2. `Array.from()`

Creates a new array from an array-like or iterable object. Or separates some wild animals.\


```
const wild  = "🐻🐯🦁";
const tamed = Array.from(wild);
// console.log(tamed);
// ["🐻", "🐯", "🦁"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/from)

### 3. `Array.concat()`

Merges two or more arrays into a single new one. Or brings different worlds together.\


```
const dogs = ["🐶", "🐶"];
const cats = ["🐱", "🐱", "🐱"];
const pets = dogs.concat(cats);
// console.log(pets);
// ["🐶", "🐶", "🐱", "🐱", "🐱"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/concat)

### 4. `Array.every()`

Checks if all elements of an array pass the test. Or detects intruders.\


```
const visitors   = ["🧑", "👽", "🧑", "🧑", "🤖"];
const isHuman    = e => e === "🧑";
const onlyHumans = visitors.every(isHuman);
// console.log(onlyHumans);
// false
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/every)

### 5. `Array.fill()`

Replaces the elements of an array from start to end index with a given value. Or grows some trees.\


```
let seeds = ["🌱", "🌱", "🌱", "🌱", "🌱"];
seeds.fill("🌳", 1, 4);
// console.log(seeds);
// ["🌱", "🌳", "🌳", "🌳", "🌱"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/fill)

### 6. `Array.filter()`

Creates a new array containing all elements passing the test. Or predicts your relationship status.\


```
const guests  = ["👩👨", "👩👩", "👨", "👩", "👨👨"];
const singles = guests.filter(g => g.length/2 === 1); // *
// console.log(singles);
// ["👨", "👩"]
```

_\* You might wonder, why the string length is divided by two here. The reason is that emojis actually are represented by a pair of code points, also known as a surrogate pair._\
_Try `"👩".length` in your console and see for yourself. More information in _[_this article_](https://thekevinscott.com/emojis-in-javascript/)_._

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/filter)

### 7. `Array.flat()`

Creates a new array containing all elements from all sub-arrays up to a given depth. Or cracks any safe.\


```
const savings = ["💵", ["💵", "💵"], ["💵", "💵"], [[["💰"]]]];
const loot    = savings.flat(3)
// console.log(loot);
// ["💵", "💵", "💵", "💵", "💵", "💰"];
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/flat)

### 8. `Array.includes()`

Checks if an array contains a specific element. Or finds the secret sweet tooth.\


```
const food   = ["🥦", "🥬", "🍅", "🥒", "🍩", "🥕"];
const caught = food.includes("🍩");
// console.log(caught);
// true
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/includes)

### 9. `Array.join()`

Concatenates all array elements to one single string, using an optional separator. Or builds local area networks.\


```
const devices = ["💻", "🖥️", "🖥️", "💻", "🖨️"];
const network = devices.join("〰️");
// console.log(network);
// "💻〰️🖥️〰️🖥️〰️💻〰️🖨️"
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/join)

### 10. `Array.map()`

Calls a function on each array element and returns the result as new array. Or feeds all hungry monkeys.\


```
const hungryMonkeys = ["🐒", "🦍", "🦧"];
const feededMonkeys = hungryMonkeys.map(m => m + "🍌");
// console.log(feededMonkeys);
// ["🐒🍌", "🦍🍌", "🦧🍌"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/map)

### 11. `Array.reverse()`

Reverses the order of elements in an array. Or decides the outcome of a race.\


```
let   rabbitWins   = ["🐇", "🦔"];
const hedgehogWins = rabbitWins.reverse();
// console.log(hedgehogWins);
// ["🦔", "🐇"]
```

_Note that this method is destructive, it modifies the original array. So after line 2 of this example `rabbitWins` and `hedgehogWins` both have the value_ `["🦔", "🐇"]`

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/reverse)

### 12. `Array.slice()`

Creates a new array from copying a portion of an array defined by start and end index. Or cheats in an exam.\


```
const solutionsOfClassmates = ["📃", "📑", "📄", "📝"];
const myOwnSolutionReally   = solutionsOfClassmates.slice(2, 3);
// console.log(myOwnSolutionReally);
// ["📄"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/slice)

### 13. `Array.some()`

Tests if at least one element of an array passes the test. Or finds if some participants of your meeting forgot to mute their mic.\


```
const participants = ["🔇", "🔇", "🔊", "🔇", "🔊"];
const isLoud       = p => p === "🔊";
const troubles     = participants.some(isLoud);
// console.log(troubles);
// true
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/some)

### 14. `Array.sort()`

Sorts all elements of an array. Or organizes your bookshelf again.\


```
let books = ["📕", "📗", "📕", "📒", "📗", "📒"];
books.sort();
// console.log(books);
// ["📒", "📒", "📕", "📕", "📗", "📗"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/sort)

### 15. `Array.splice()`

Removes, replaces or adds elements to an array. Or changes the weather.\


```
let weather = ["☁️", "🌧️", "☁️"];
weather.splice(1, 2, "☀️");
// console.log(weather);
// ["☁️", "☀️"]
```

_Documentation on _[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/splice)

### 16. `Array.unshift()`

Adds one or more elements to the beginning of an array. Or couples a loco.\


```
let train = ["🚃", "🚃", "🚃", "🚃"];
train.unshift("🚂");
// console.log(train);
// ["🚂", "🚃", "🚃", "🚃", "🚃"]
```
