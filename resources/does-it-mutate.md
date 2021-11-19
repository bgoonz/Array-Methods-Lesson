# 💱 Does It Mutate¿

**What does the term "mutability" mean in programming?**

* "Mutability" refers to an object's ability to undergo change. Mutable objects can be modified, while immutable objects cannot be changed after they are created.

***

** Identify which of the following JavaScript data types are mutable: number, string, boolean, array**

* Arrays are mutable.
* Numbers, strings, and booleans are all immutable.

***

## .concat​

no mutation

#### Description

The concat() method is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.

```
Array.prototype.concat ( [ item1 [ , item2 [ , … ] ] ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/concat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/concat)

#### Example

```
let array1 = ['a', 'b', 'c'];
let array2 = ['d', 'e', 'f'];

console.log(array1.concat(array2));
// expected output: Array ["a", "b", "c", "d", "e", "f"]
```

## .copyWithin()

mutates

#### Description

The copyWithin() method shallow copies part of an array to another location in the same array and returns it, without modifying its size.

```
arr.copyWithin(target)
arr.copyWithin(target, start)
arr.copyWithin(target, start, end)
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/copyWithin](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/copyWithin)

#### Example

```
let array1 = ['a', 'b', 'c', 'd', 'e'];

// copy to index 0 the element at index 3
console.log(array1.copyWithin(0, 3, 4));
// expected output: Array ["d", "b", "c", "d", "e"]

// copy to index 1 all elements from index 3 to the end
console.log(array1.copyWithin(1, 3));
// expected output: Array ["d", "d", "e", "d", "e"]
```

## .entries()

no mutation

#### Description

The entries() method returns a new Array Iterator object that contains the key/value pairs for each index in the array.

```
a.entries()
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/entries](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/entries)

#### Example

```
let array1 = ['a', 'b', 'c'];

let iterator1 = array1.entries();

console.log(iterator1.next().value);
// expected output: Array [0, "a"]

console.log(iterator1.next().value);
// expected output: Array [1, "b"]
```

## .every

no mutation

#### Description

The every() method tests whether all elements in the array pass the test implemented by the provided function.

```
Array.prototype.every ( callbackfn [ , thisArg ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/every](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/every)

#### Example

```
function isBelowThreshold(currentValue) {
  return currentValue < 40;
}

let array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// expected output: true
```

## .fill()

mutates

#### Description

The fill() method fills all the elements of an array from a start index to an end index with a static value.

```
arr.fill(value)
arr.fill(value, start)
arr.fill(value, start, end)
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/fill](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/fill)

#### Example

```
let array1 = [1, 2, 3, 4];

// fill with 0 from position 2 until position 4
console.log(array1.fill(0, 2, 4));
// expected output: [1, 2, 0, 0]

// fill with 5 from position 1
console.log(array1.fill(5, 1));
// expected output: [1, 5, 5, 5]

console.log(array1.fill(6));
// expected output: [6, 6, 6, 6]
```

## .filter

no mutation

#### Description

The filter() method creates a new array with all elements that pass the test implemented by the provided function.

```
Array.prototype.filter ( callbackfn [ , thisArg ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/filter)

#### Example

```
let words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```

## .find()

no mutation

#### Description

The find() method returns a value of the first element in the array that satisfies the provided testing function. Otherwise undefined is returned.

```
arr.find(callback[, thisArg])
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/find](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/find)

#### Example

```
let array1 = [5, 12, 8, 130, 44];

let found = array1.find(function(element) {
  return element > 10;
});

console.log(found);
// expected output: 12
```

## .findIndex()

no mutation

#### Description

The findIndex() method returns an index of the first element in the array that satisfies the provided testing function. Otherwise -1 is returned.

```
arr.findIndex(callback[, thisArg])
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/findIndex](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/findIndex)

#### Example

```
let array1 = [5, 12, 8, 130, 44];

function isLargeNumber(element) {
  return element > 13;
}

console.log(array1.findIndex(isLargeNumber));
// expected output: 3
```

## .flat

no mutation

#### Description

The flat() method creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.

```
let newArray = arr.flat([depth]);
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/flat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/flat)

#### Example

```
let arr1 = [1, 2, [3, 4]];
arr1.flat(); 
// [1, 2, 3, 4]

let arr2 = [1, 2, [3, 4, [5, 6]]];
arr2.flat();
// [1, 2, 3, 4, [5, 6]]

let arr3 = [1, 2, [3, 4, [5, 6]]];
arr3.flat(2);
// [1, 2, 3, 4, 5, 6]

let arr4 = [1, 2, [3, 4, [5, 6, [7, 8, [9, 10]]]]];
arr4.flat(Infinity);
// [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

## .forEach

no mutation

#### Description

The forEach() method executes a provided function once per array element.

```
Array.prototype.forEach ( callbackfn [ , thisArg ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/forEach](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/forEach)

#### Example

```
let array1 = ['a', 'b', 'c'];

array1.forEach(function(element) {
  console.log(element);
});

// expected output: "a"
// expected output: "b"
// expected output: "c"
```

## .includes()

no mutation

#### Description

The includes() method determines whether an array includes a certain element, returning true or false as appropriate.

```
arr.includes(searchElement)
arr.includes(searchElement, fromIndex)
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/includes)

#### Example

```
let array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true

let pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// expected output: true

console.log(pets.includes('at'));
// expected output: false
```

## .indexOf

no mutation

#### Description

The indexOf() method returns the first index at which a given element can be found in the array, or -1 if it is not present.

```
Array.prototype.indexOf ( searchElement [ , fromIndex ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/indexOf)

#### Example

```
let beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// expected output: 1

// start from index 2
console.log(beasts.indexOf('bison', 2));
// expected output: 4

console.log(beasts.indexOf('giraffe'));
// expected output: -1
```

## .join

no mutation

#### Description

The join() method joins all elements of an array into a string.

```
Array.prototype.join (separator)
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/join](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/join)

#### Example

```
let elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// expected output: "Fire,Air,Water"

console.log(elements.join(''));
// expected output: "FireAirWater"

console.log(elements.join('-'));
// expected output: "Fire-Air-Water"
```

## .keys()

no mutation

#### Description

The keys() method returns a new Array Iterator that contains the keys for each index in the array.

```
arr.keys()
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/keys](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/keys)

#### Example

```
let array1 = ['a', 'b', 'c'];
let iterator = array1.keys(); 
  
for (let key of iterator) {
  console.log(key); // expected output: 0 1 2
}
```

## .lastIndexOf

no mutation

#### Description

The lastIndexOf() method returns the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched backwards, starting at fromIndex.

```
Array.prototype.lastIndexOf ( searchElement [ , fromIndex ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/lastIndexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/lastIndexOf)

#### Example

```
let animals = ['Dodo', 'Tiger', 'Penguin', 'Dodo'];

console.log(animals.lastIndexOf('Dodo'));
// expected output: 3

console.log(animals.lastIndexOf('Tiger'));
// expected output: 1
```

## .map

no mutation

#### Description

The map() method creates a new array with the results of calling a provided function on every element in this array.

```
Array.prototype.map ( callbackfn [ , thisArg ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/map)

#### Example

```
let array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
```

## .pop

mutates

#### Description

The pop() method removes the last element from an array and returns that element. This method changes the length of the array.

```
Array.prototype.pop ( )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/pop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/pop)

#### Example

```
let plants = ['broccoli', 'cauliflower', 'cabbage', 'kale', 'tomato'];

console.log(plants.pop());
// expected output: "tomato"

console.log(plants);
// expected output: Array ["broccoli", "cauliflower", "cabbage", "kale"]

plants.pop();

console.log(plants);
// expected output: Array ["broccoli", "cauliflower", "cabbage"]
```

## .push

mutates

#### Description

The push() method adds one or more elements to the end of an array and returns the new length of the array.

```
Array.prototype.push ( [ item1 [ , item2 [ , … ] ] ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/push](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/push)

#### Example

```
let animals = ['pigs', 'goats', 'sheep'];

console.log(animals.push('cows'));
// expected output: 4

console.log(animals);
// expected output: Array ["pigs", "goats", "sheep", "cows"]

animals.push('chickens');

console.log(animals);
// expected output: Array ["pigs", "goats", "sheep", "cows", "chickens"]
```

## .reduce

no mutation

#### Description

The reduce() method applies a function against an accumulator and each value of the array (from left-to-right) to reduce it to a single value.

```
Array.prototype.reduce ( callbackfn [ , initialValue ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/Reduce)

#### Example

```
const array1 = [1, 2, 3, 4];
const reducer = (accumulator, currentValue) => accumulator + currentValue;

// 1 + 2 + 3 + 4
console.log(array1.reduce(reducer));
// expected output: 10

// 5 + 1 + 2 + 3 + 4
console.log(array1.reduce(reducer, 5));
// expected output: 15
```

## .reduceRight

no mutation

#### Description

The reduceRight() method applies a function against an accumulator and each value of the array (from right-to-left) has to reduce it to a single value.

```
Array.prototype.reduceRight ( callbackfn [ , initialValue ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/ReduceRight](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/ReduceRight)

#### Example

```
const array1 = [[0, 1], [2, 3], [4, 5]].reduceRight(
  (accumulator, currentValue) => accumulator.concat(currentValue)
);

console.log(array1);
// expected output: Array [4, 5, 2, 3, 0, 1]
```

## .reverse

mutates

#### Description

The reverse() method reverses an array in place. The first array element becomes the last, and the last array element becomes the first.

```
Array.prototype.reverse ( )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/reverse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/reverse)

#### Example

```
let array1 = ['one', 'two', 'three'];
console.log('array1: ', array1);
// expected output: Array ['one', 'two', 'three']

let reversed = array1.reverse(); 
console.log('reversed: ', reversed);
// expected output: Array ['three', 'two', 'one']

/* Careful: reverse is destructive. It also changes
the original array */ 
console.log('array1: ', array1);
// expected output: Array ['three', 'two', 'one']
```

## .shift

mutates

#### Description

The shift() method removes the first element from an array and returns that element. This method changes the length of the array.

```
Array.prototype.shift ( )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/shift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/shift)

#### Example

```
let array1 = [1, 2, 3];

let firstElement = array1.shift();

console.log(array1);
// expected output: Array [2, 3]

console.log(firstElement);
// expected output: 1
```

## .slice

no mutation

#### Description

The slice() method returns a shallow copy of a portion of an array into a new array object selected from begin to end (end not included). The original array will not be modified.

```
Array.prototype.slice (start, end)
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/slice)

#### Example

```
let animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]
```

## .some

no mutation

#### Description

The some() method tests whether some element in the array passes the test implemented by the provided function.

```
Array.prototype.some ( callbackfn [ , thisArg ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/some)

#### Example

```
let array = [1, 2, 3, 4, 5];

let even = function(element) {
  // checks whether an element is even
  return element % 2 === 0;
};

console.log(array.some(even));
// expected output: true
```

## **.sort**

mutates

#### Description

The sort() method sorts the elements of an array in place and returns the array. The sort is not necessarily stable. The default sort order is according to string Unicode code points.

```
Array.prototype.sort (comparefn)
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/sort](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/sort)

#### Example

```
let months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);
// expected output: Array ["Dec", "Feb", "Jan", "March"]

let array1 = [1, 30, 4, 21, 100000];
array1.sort();
console.log(array1);
// expected output: Array [1, 100000, 21, 30, 4]
```

## .splice

mutates

#### Description

The splice() method changes the content of an array by removing existing elements and/or adding new elements.

```
Array.prototype.splice (start, deleteCount [ , item1 [ , item2 [ , … ] ] ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/splice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/splice)

#### Example

```
let months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// inserts at 1st index position
console.log(months);
// expected output: Array ['Jan', 'Feb', 'March', 'April', 'June']

months.splice(4, 1, 'May');
// replaces 1 element at 4th index
console.log(months);
// expected output: Array ['Jan', 'Feb', 'March', 'April', 'May']
```

##

## .toString

no mutation

#### Description

The toString() method returns a string representing the specified array and its elements.

```
Array.prototype.toString ( )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/toString](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/toString)

#### Example

```
let array1 = [1, 2, 'a', '1a'];

console.log(array1.toString());
// expected output: "1,2,a,1a"
```

## .unshift

mutates

#### Description

The unshift() method adds one or more elements to the beginning of an array and returns the new length of the array.

```
Array.prototype.unshift ( [ item1 [ , item2 [ , … ] ] ] )
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/unshift](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/unshift)

#### Example

```
let array1 = [1, 2, 3];

console.log(array1.unshift(4, 5));
// expected output: 5

console.log(array1);
// expected output: Array [4, 5, 1, 2, 3]
```

## .values()

no mutation

#### Description

The values() method returns a new Array Iterator object that contains the values for each index in the array.

```
arr.values()
```

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/values](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array/values)

#### Example

```
const array1 = ['a', 'b', 'c'];
const iterator = array1.values();

for (const value of iterator) {
  console.log(value); // expected output: "a" "b" "c"
}
```

\\
