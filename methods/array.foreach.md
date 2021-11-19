# 🔗 Array.forEach()

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}

### forEach() <a href="96f8" id="96f8"></a>

```
const array = [1, 2, 3, 4]array.forEach((elemnt, index) => {   console.log(`Element ${element} at index ${index}`)}
```

\*\*`forEach` \*\*method will call the function provided once for each element in the array preserving the order. This function provided can take in 3 different arguments: `element`, `index`, `array`. Be sure that the order in which you pass these parameters follow the order.





The [`for` loop](https://alligator.io/js/for-loops/) is probably one of the first looping mechanisms you learned about when diving into JavaScript.

```
for (let i = 0; i < 5; i++) {
  console.log(i);
}

// Result:
// 0
// 1
// 2
// 3
// 4
```

The `for` loop above takes 3 statements within it:

1. `let i = 0`, which executes before the loop starts
2. `i < 5`, which is the condition for running the block of code within your loop
3. `i++`, which runs after each iteration of your loop

The result of those three statements is that the `for` loop executes the code within it, which is `console.log(i)`. Our `i` starts at 0, and as long as `i` is smaller than 5, we’ll run the code block. However, after each loop, we add 1 to our `i`, as shown by the third statement, `i++`.

Let’s dive into something a little fancier for this `for` loop. Let’s assume that we have an array with some objects in it:

```
const foodArray = [
  { name: 'Burrito' },
  { name: 'Pizza' },
  { name: 'Burger' },
  { name: 'Pasta' }
];
```

Let’s say we wanted to use a `for` loop to iterate over each object within the `foodArray`. We would alter the condition and use `i` as the numeric index to access the values within `foodArray`.

```
for (let i = 0; i < foodArray.length; i++) {
  console.log(`i value: ${i} | Food Name:`, foodArray[i]);
}

// Result:
// i value: 0 | Food Name: { name: 'Burrito' }
// i value: 1 | Food Name: { name: 'Pizza' }
// i value: 2 | Food Name: { name: 'Burger' }
// i value: 3 | Food Name: { name: 'Pasta' }
```

### What About forEach?

Like the `for` loop, the `forEach` method can also achieve the same results:

```
foodArray.forEach((food, index) => {
  console.log(`i value: ${index} | Food Name:`, food);
});

// Result:
// i value: 0 | Food Name: { name: 'Burrito' }
// i value: 1 | Food Name: { name: 'Pizza' }
// i value: 2 | Food Name: { name: 'Burger' }
// i value: 3 | Food Name: { name: 'Pasta' }
```

#### How is that possible? <a href="how-is-that-possible" id="how-is-that-possible"></a>

The `forEach` method exists within all arrays. In our case, `foodArray` is an array that inherits all of the various methods from `Array.prototype`. For the `forEach` method, we pass in a function that will be executed in each iteration.

### Which Should You Use?

It really comes down to the preference of the developer. However, here are some things to consider when choosing between a `for` loop and the `forEach` method.

#### 1. forEach keeps the variable’s scope to the block <a href="1-foreach-keeps-the-variables-scope-to-the-block" id="1-foreach-keeps-the-variables-scope-to-the-block"></a>

The good thing about `forEach` is that the callback function within it allows you to keep that variable within the `forEach`’s scope. If you’ve assigned a variable outside and re-use it within the `forEach`, the outside variable retains its value.

```
const num = 4;
const arr = [0, 1, 2];

arr.forEach(num => {
  console.log(num);
});

// Result:
// 0
// 1
// 2
console.log(num);

// Result:
// 4
```

Normally, you would try to avoid naming a variable twice like in the example above. It's just to make a point!

#### 2. Lower chance of accidental errors with forEach <a href="2-lower-chance-of-accidental-errors-with-foreach" id="2-lower-chance-of-accidental-errors-with-foreach"></a>

When using the `forEach` method, you’re calling on the `Array.prototype` method in relation to the array directly. When you use a `for` loop, you have to set up a variable to increment (`i`), a condition to follow, and the actual increment itself.

Based on the example above, let’s say that we wrote a `for` loop like this:

```
for (let i = 0; i <= foodArray.length; i++) {
  console.log(`i value: ${i} | Food Name:`, foodArray[i]);
}

// Result:
// i value: 0 | Food Name: { name: 'Burrito' }
// i value: 1 | Food Name: { name: 'Pizza' }
// i value: 2 | Food Name: { name: 'Burger' }
// i value: 3 | Food Name: { name: 'Pasta' }
// i value: 4 | Food Name: undefined
```

I changed my condition from `<` to a `<=`. Instead of ending at 3, which is less than the length of my array, it goes all the way to 4. Since there’s nothing in our array at index 4, it returns an undefined. This type of off-by-one-bug is a logic error when your iterative loop iterates one more or less than you anticipated.

Using a `forEach` loop, this can be avoided.

#### 3. forEach is easier to read <a href="3-foreach-is-easier-to-read" id="3-foreach-is-easier-to-read"></a>

Again, this is down to the discretion of the developer, but here’s why I feel that the `forEach` method is a little cleaner than the `for` loop.

In a `forEach` method, we pass each food type within that iteration into the callback. A `for` loop needs you to access the array using a temporary `i` variable. While this might not seem very messy in the beginning, it can get more cluttered when you begin to add more code.

```
for (let i = 0; i < foodArray.length; i++) {
  let food = foodArray[i];
  console.log(food);
  for (let j = 0; j < food.ingredients.length; j++) {
    let ingredient = food.ingredients[j];
    console.log(ingredient);
  }
}
```

There’s a bit going on in the code above. Having to use the temporary `i` and `j` variables can add a lot of confusion to your code. Here’s what it would look like as a `forEach` instead:

```
foodArray.forEach((food) => {
  console.log(food);
  food.ingredients.forEach((ingredient) => {
    console.log(ingredient);
  });
});
```

We’ve gotten rid of the temporary counter variables and it requires fewer lines of code!

#### 4. You can break out of a for loop earlier <a href="4-you-can-break-out-of-a-for-loop-earlier" id="4-you-can-break-out-of-a-for-loop-earlier"></a>

One main reason why I would use the `for` loop is if I needed to break out of a loop early. If you wanted to only return a certain food in your array, you could use an `if` statement to check if your criteria matches, and then break out from the loop. The `forEach` method would iterate over each food, which could lead to performance issues.

Here’s an example of what the `for` loop would look like if you broke out of it early:

```
for (let i = 0; i < foodArray.length; i++) {
  if (foodArray[i].name === 'Pizza') {
    console.log('I LOVE PIZZA');
    break;
  }
}
```

When we use the `break` keyword, we can stop the loop from continuing once we’ve found the condition we were looking for.
