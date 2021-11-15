---
cover: ../.gitbook/assets/map.png
coverY: 0
---

# Array.map()

### `Array.map()` <a href="d50b" id="d50b"></a>

Calls a function on each array element and returns the result as new array. Or feeds all hungry monkeys.

```javascript
const hungryMonkeys = ["🐒", "🦍", "🦧"];
const feededMonkeys = hungryMonkeys.map(m => m + "🍌");
console.log(feededMonkeys);// ["🐒🍌", "🦍🍌", "🦧🍌"]
```

\_Documentation on \_[_MDN_](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global\_Objects/Array/map)

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}
