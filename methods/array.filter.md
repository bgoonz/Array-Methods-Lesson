# 🚮 Array.filter()

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}

### filter() <a href="94ae" id="94ae"></a>

```
const array = [1, 2, 3, 4]const filteredArray = array.filter(element => element%2)// array = [1, 2, 3, 4]// filteredArray = [1, 3]
```

**`filter`** method will return a brand new array with elements that returned `true`_ _from the function provided. Notice that in the example above, the function passed into the filter method returns `true` if element is odd which is why you see that `filteredArray` is `[1, 3]`.

**`Note`**: filter method doesn’t mutate the original array. It will create a new array.
