# Native Implementation

## ForEach



```javascript
// Some code
/*******************************************************************************
Write a function `myForEach` that accepts an array and a callback as arguments.
The function should call the callback on each element of the array, passing in the
element, index, and array itself. The function does not need to return any value.

Do not use the built in Array#forEach.

Examples:

myForEach(['a', 'b', 'c'], function (el, i) {
    console.log(el + ' is at index ' + i);
}); // prints
// a is at index 0
// b is at index 1
// c is at index 2

let test = [];
myForEach(['laika', 'belka'], function (el) {
    test.push(el.toUpperCase());
});
console.log(test); // ['LAIKA', 'BELKA']
*******************************************************************************/

function myForEach(array, cb) {
    for (let i = 0; i < array.length; i++) {
        let el = array[i];
        cb(el, i, array);
    }
}


module.exports = myForEach;
```

## Map



```
// Some code
/*******************************************************************************
Write a function `myMap` that accepts an array and a callback as arguments.
The function return an array of new elements obtained by calling the callback on
each element of the array, passing in the element.

Do not use the built in Array#map

// Examples

let result1 = myMap([100, 25, 81, 64], Math.sqrt);
console.log(result1);   // [ 10, 5, 9, 8 ]

let result2 = myMap(['run', 'Forrest'], function (el) {
    return el.toUpperCase() + '!';
});
console.log(result2);   // [ 'RUN!', 'FORREST!' ]
*******************************************************************************/

function myMap(array, cb) {
    let mapped = [];
    for (let i = 0; i < array.length; i++) {
        let ele = array[i];
        mapped.push(cb(ele));
    }
    return mapped;
}

```



## Reduce

```javascript
/*******************************************************************************
Write a function `mySimpleReduce` that accepts an array and a callback as arguments.
The function should mimic the behavior of the built in Array#reduce, utilizing the
first element of the array as the default accumulator.

In other words, the function should begin with the first element of the array as
the accumulator and call the callback for each of the remaining elements in the array,
passing in the current accumulator and current element into the callback. Upon calling the callback,
the accumulator should be set to the result of the callback.

Examples:

let result1 = mySimpleReduce([5, 3, 2, 4], function(sum, el) {
    return sum + el;
});
console.log(result1); // 14

let result2 = mySimpleReduce([4, 6, 2], function(product, el) {
    return product * el;
});
console.log(result2); // 48

let result3 = mySimpleReduce([4, 6, 2, 8, 3], function(max, el) {
    if (el > max) {
        return el;
    } else {
        return max;
    }
});
console.log(result3); // 8
*******************************************************************************/

function mySimpleReduce(array, cb) {
    let accumulator = array[0];
    array.slice(1).forEach(function (el) {
        accumulator = cb(accumulator, el);
    });
    return accumulator;
}
```





##

## Array Callback Methods Implemented With For Loops

How to implement array callback methods in JavaScript

***

#### Array Callback Methods Implemented With For Loops

**How to implement array callback methods in JavaScript**

#### Functions are called “First Class Objects” in JavaScript because:

![](https://cdn-images-1.medium.com/max/800/0\*WpKqOdTsTPhvapuW)

* <mark style="background-color:purple;">A function is an instance of the Object type</mark>
* <mark style="background-color:purple;">A function can have properties and has a link back to its constructor method</mark>
* <mark style="background-color:purple;">You can store the function in a variable</mark>
* <mark style="background-color:purple;">You can pass the function as a parameter to another function</mark>
* <mark style="background-color:purple;">You can return the function from a function</mark>

What do you think will be printed in the following:

**Anonymous callback, a named callback**

```javascript
function foo(callback) {
  console.log("grape");
  callback();
}

function bar() {
  console.log("banana");
}

const fruitBasket = function () {
  console.log("apple");
  bar();
  foo(bar);
  foo(function () {
    console.log("orange");
  });
  console.log("pear");
};

fruitBasket();
```

**Function that takes in a value and two callbacks. The function should return the result of the callback who’s invocation results in a larger value.**

```javascript
function greaterValue(value, cb1, cb2) {
  // compare cb1 invoked with value to cb2 invoked with value
  // return the greater result

  let res1 = cb1(value);
  let res2 = cb2(value);
  if (res1 > res2) {
    // if this is false, we move out of if statement
    return res1;
  }
  return res2;
}

let negate = function (num) {
  return num * -1;
};

let addOne = function (num) {
  return num + 1;
};

console.log(greaterValue(3, negate, addOne));
console.log(greaterValue(-2, negate, addOne));
```

_Note: we do not invoke_ `negate` _or_ `addOne` _(by using_ `()` _to call them), we are passing the function itself._

**Write a function, myMap, that takes in an array and a callback as arguments. The function should mimic the behavior of Array.prototype.map.**

```javascript
function myMap(arr, callback) {
  // iterate through the array, perform the cb on each element
  // return a new array with those new values
  let mapped = [];

  for (let i = 0; i < arr.length; i++) {
    // remember that map passes three args with each element.
    let val = callback(arr[i], i, arr);
    mapped.push(val);
  }

  return mapped;
}

let double = function (num) {
  return num * 2;
};
console.log(myMap([1, 2, 3], double));
```

**Write a function, myFilter, that takes in an array and a callback as arguments. The function should mimic the behavior of Array.prototype.filter.**

```javascript
function myFilter(arr, callback) {
  let filtered = [];

  for (let i = 0; i < arr.length; i++) {
    let element = arr[i];

    if (callback(element, i, arr)) {
      filtered.push(element);
    }
  }

  return filtered;
}
```

**Write a function, myEvery, that takes in an array and a callback as arguments. The function should mimic the behavior of Array.prototype.every.**

```
function myEvery(arr, callback) {
    for (let i = 0; i < arr.length; i++) {
        let element = arr[i];

        if (callback(element, i, arr) === false) {
            return false;
        }
    }
    return true;
}
```

#### Further Examples of the above concepts

```javascript
const createMeowValue = () => {
  console.log(this.name);
  let meow = function () {
    console.log(this);
    console.log(this.name + " meows");
  };
  meow = meow.bind(this);
  return meow;
};

const name = "Fluffy";

const cat = {
  name: name,
  age: 12,
  createMeow: function () {
    console.log(this.name);
    let meow = () => {
      const hello = "hello";
      console.log(this.name + " meows");
    };
    let world = "";
    if (true) {
      world = "world";
    }
    console.log(world);
    // meow = meow.bind(this);
    return meow;
  },
};

cat.newKey = function () {
  const outermostContext = this;
  const innerFunc = () => {
    secondContext = this;
    console.log(secondContext === outermostContext);
    return function () {
      innermostContext = this;
    };
  };
  return innerFunc.bind(outermostContext);
};

const meow = cat.createMeow(); // method-style invocation
meow(); // function-style invocation

console.log("-------");

const createMeow = cat.createMeow;
const globalMeow = createMeow(); // function-style
globalMeow(); // function-style

function createSmoothie(ingredient) {
  const ingredients = [ingredient];
  return ingredients;
}

// console.log(createSmoothie('banana'));
// console.log(createSmoothie('apple'));

// one parameter only
// first argument is a string
// return an array
// DO NOT USE forEach
```
