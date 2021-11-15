---
cover: ../.gitbook/assets/reduce (2).png
coverY: 0
---

# 💩 Array.reduce()

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}

### reduce() <a href="64d0" id="64d0"></a>

```
const array = [1, 2, 3, 4]const result = array.reduce((accumulator, current) => (   accumulator + current), 10)// array = [1, 2, 3, 4]// result = 20
```

**`reduce`** method will take in `reducer` function and initial value as arguments. The `reducer` function can take up to 4 arguments: `accumulator`, `element`, `index`, and `array`. The reducer function will be executed for each iteration and the returned value of each iteration will be used for the next iteration.

`Note`: reduce method returns a single value not an array.
