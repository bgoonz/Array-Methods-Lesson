# Examples



### [concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/concat)

merge two or more arrays\


```
// example
[ 1, 2 ].concat([5], [7, 9]) // [ 1, 2, 5, 7, 9 ]
// syntax
const new_array = old_array.concat([value1[, value2[, ...[, valueN]]]])
```

***

### [copyWithin()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/copyWithin)

copies part of array to another location\


```
// example
[ 1, 2, 3, 4, 5 ].copyWithin(0,2) // [ 3, 4, 5, 4, 5 ]
// syntax
arr.copyWithin(target[, start[, end]])
```

***

### [entries()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/entries)

Array Iterator with key/value pairs for each index\


```
// example
['a', 'b', 'c'] .entries() // Array Iterator { } .next() // { value: (2) […], done: false } .value // Array [ 0, "a" ]
// syntax
arr.entries()
```

***

### [every()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/every)

tests if all elements in the array pass the test\


```
// example
[1, 30, 40].every(val => val > 0) // true
// syntax
arr.every(callback(element[, index[, array]])[, thisArg])
```

***

### [fill()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/fill)

changes elements in an array to a static value\


```
// example
[1, 2, 3, 4].fill('x', 1, 3) // [ 1, "x", "x", 4 ]
// syntax
arr.fill(value[, start[, end]])
```

***

### [filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/filter)

creates new array with elements that pass test\


```
// example
[1, 10, 5, 6].filter(val => val > 5) // [ 10, 6 ]
// syntax
let newArray = arr.filter(callback(element[, index, [array]])[, thisArg])
```

***

### [find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/find)

returns the value of the first element, that matches test\


```
// example
[1, 10, 5, 6].find(val => val > 5) // 10
// syntax
arr.find(callback(element[, index[, array]])[, thisArg])
```

***

### [findIndex()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/findIndex)

returns index of the first element, that matches test\


```
// example
[1, 4, 5, 6].findIndex(val => val > 5) // 3
// syntax
arr.findIndex(callback( element[, index[, array]] )[, thisArg])
```

***

### [flat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/flat)

creates a new array with sub-array elements flattened by specified depth.\


```
// example
[1, [2, [3, [4]]]].flat(2) // [ 1, 2, 3, [4] ]
// syntax
const new_array = arr.flat([depth]);
```

***

### [flatMap()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/flatMap)

creates a new array with sub-array elements flattened by specified depth.\


```
// example
[[2], [4], [6], [8]].flatMap(val => val/2) // [ 1, 2, 3, 4 ]
// syntax
let new_array = arr.flatMap(function callback(currentValue[, index[, array]]) {
    // return element for new_array
}[, thisArg])
```

***

### [forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/forEach)

executes provided function once for each array element\


```
// example
[ 1, 2, 3 ].forEach(val => console.log(val)) // 1 // 2 // 3
// syntax
arr.forEach(callback(currentValue [, index [, array]])[, thisArg])
```

***

### [includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/includes)

determines if array includes a certain value\


```
// example
[ 1, 2, 3 ].includes(3) // true
// syntax
arr.includes(valueToFind[, fromIndex])
```

***

### [indexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/indexOf)

returns the first index at which element can be found\


```
// example
[ 1, 2, 3 ].indexOf(3) // 2
// syntax
arr.indexOf(searchElement[, fromIndex])
```

***

### [join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/join)

returns string by concatenating all elements in array\


```
// example
[ "x", "y", "z" ].join(" - ") // "x - y - z"
// syntax
arr.join([separator])
```

***

### [keys()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/keys)

returns Array Iterator that contains keys for each index\


```
// example
['a', 'b', 'c']
    .keys() // Array Iterator { }
    .next() // { value: 0, done: false }
    .value // 0
// syntax
arr.keys()
```

***

### [lastIndexOf()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/lastIndexOf)

returns last index at which given element can be found\


```
// example
[ 1, 2, 3, 1, 0].lastIndexOf(1) // 3
// syntax
arr.lastIndexOf(searchElement[, fromIndex])
```

***

### [map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/map)

creates new array with results of provided function\


```
// example
[ 2, 3, 4 ].map(val => val * 2) // [ 4, 6, 8 ]
// syntax
let new_array = arr.map(function callback( currentValue[, index[, array]]) {
    // return element for new_array
}[, thisArg])
```

***

### [pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/pop)

removes last element from array and returns that element\


```
// example
const arr = [ 1, 2, 3 ]
arr.pop() // returns: 3 // arr is [ 1, 2 ]
// syntax
arr.pop()
```

***

### [push()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/push)

adds one or more elements to end of array and returns new length\


```
// example
const arr = [ 1, 2, 3 ]
arr.push(1) // returns: 4 // arr is [ 1, 2, 3, 4 ]
// syntax
arr.push(element1[, ...[, elementN]])
```

***

### [reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/Reduce)

executes a reducer function, resulting in single output value\


```
// example
[ 'a', 'b', 'c' ].reduce((acc, curr) => acc + curr, 'd') // "dabc"
// syntax
arr.reduce(callback( accumulator, currentValue[, index[, array]] )[, initialValue])
```

***

### [reduceRight()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/ReduceRight)

executes a reducer function from right to left, resulting in single output value\


```
// example
[ 'a', 'b', 'c' ].reduceRight((acc, curr) => acc + curr, 'd') // "dcba"
// syntax
arr.reduceRight(callback(accumulator, currentValue[, index[, array]])[, initialValue])
```

***

### [reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/reverse)

reverses an array\


```
// example
[ 1, 2, 3 ].reverse() // [ 3, 2, 1 ]
// syntax
arr.reverse()
```

***

### [shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/shift)

removes the first element from array and returns that element\


```
// example
const arr = [ 1, 2, 3 ]
arr.shift() // returns: 1 // arr is [ 2, 3 ]
// syntax
arr.shift()
```

***

### [slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/slice)

returns a copy of part of array, while original array is not modified\


```
// example
[ 1, 2, 3, 4 ].slice(1, 3) // [ 2, 3 ]
// syntax
arr.slice([begin[, end]])
```

***

### [some()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/some)

tests whether at least one element in array passes the test\


```
// example
[ 1, 2, 3, 4 ].some(val => val > 3) // true
// syntax
arr.some(callback(element[, index[, array]])[, thisArg])
```

***

### [sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/sort)

sorts the elements of array in place\


```
// example
[ 1, 2, 3, 4 ].sort((a, b) => b - a) // [ 4, 3, 2, 1 ]
// syntax
arr.sort([compareFunction])
```

***

### [splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/splice)

changes contents of array by removing, replacing and/or adding elements\


```
// example
const arr = [ 1, 2, 3, 4 ]
arr.splice(1, 2, 'a') // returns [ 2, 3 ] // arr is [ 1, "a", 4 ]
// syntax
let arrDeletedItems = array.splice(start[, deleteCount[, item1[, item2[, ...]]]])
```

***

### [toLocaleString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/toLocaleString)

elements are converted to Strings using toLocaleString and are separated by locale-specific String (eg. “,”)\


```
// example
[1.1, 'a', new Date()].toLocaleString('EN') // "1.1,a,5/18/2020, 7:58:57 AM"
// syntax
arr.toLocaleString([locales[, options]]);
```

***

### [toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/toString)

returns a string representing the specified array\


```
// example
[ 'a', 2, 3 ].toString() // "a,2,3"
// syntax
arr.toString()
```

***

### [unshift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/unshift)

adds one or more elements to beginning of array and returns new length\


```
// example
const arr = [ 1, 2, 3 ]
arr.unshift(0, 99) // returns 5 // arr is [ 0, 99, 1, 2, 3 ]
// syntax
arr.unshift(element1[, ...[, elementN]])
```

***

### [values()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/values)

returns Array Iterator object that contains values for each index in array\


```
// example
['a', 'b', 'c']
    .values() // Array Iterator { }
    .next() // { value: "a", done: false }
    .value // "a"
// syntax
arr.values()
```
