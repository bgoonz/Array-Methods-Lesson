---
cover: ../.gitbook/assets/map.png
coverY: 0
---

# 🗺 Array.map()

### `Array.map()` <a href="d50b" id="d50b"></a>

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

Calls a function on each array element and returns the result as new array. Or feeds all hungry monkeys.

```javascript
const hungryMonkeys = ["🐒", "🦍", "🦧"];
const feededMonkeys = hungryMonkeys.map((m) => m + "🍌");
console.log(feededMonkeys); // ["🐒🍌", "🦍🍌", "🦧🍌"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/map)

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}

### map() <a href="230b" id="230b"></a>

```
const array = [1, 2, 3, 4]const mapArray = array.map(element => element * 2)// array = [1, 2, 3, 4]// mapArray = [2, 4, 6, 8]
```

**`map`** method will create a new array of elements where each element is a value returned from the function provided. The example above shows the function provided doubling each element. Hence, `mapArray` is `[2, 4, 6, 8]`.

`Note`: just like filter method, map will not mutate the original array because it will create a new array.
