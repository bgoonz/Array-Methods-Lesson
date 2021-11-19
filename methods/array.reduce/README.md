---
cover: ../../.gitbook/assets/reduce (2).png
coverY: 0
---

# 💩 Array.reduce()

## .reduce

<mark style="color:red;">no mutation</mark>

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

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}

### reduce() <a href="64d0" id="64d0"></a>

```
const array = [1, 2, 3, 4]const result = array.reduce((accumulator, current) => (   accumulator + current), 10)// array = [1, 2, 3, 4]// result = 20
```

**`reduce`** method will take in `reducer` function and initial value as arguments. The `reducer` function can take up to 4 arguments: `accumulator`, `element`, `index`, and `array`. The reducer function will be executed for each iteration and the returned value of each iteration will be used for the next iteration.

`Note`: reduce method returns a single value not an array.
