# ➡ Fat Arrow Syntax

{% embed url="https://replit.com/@bgoonz/array-methods#index.js" %}



## Arrow function expressions

An **arrow function expression** is a compact alternative to a traditional [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function), but is limited and can't be used in all situations.

**Differences & Limitations:**

* Does not have its own bindings to [`this`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) or [`super`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/super), and should not be used as [`methods`](https://developer.mozilla.org/en-US/docs/Glossary/Method).
* Does not have [`new.target`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new.target) keyword.
* Not suitable for [`call`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/call), [`apply`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/apply) and [`bind`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/bind) methods, which generally rely on establishing a [scope](https://developer.mozilla.org/en-US/docs/Glossary/Scope).
* Can not be used as [constructors](https://developer.mozilla.org/en-US/docs/Glossary/Constructor).
* Can not use [`yield`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield), within its body.

#### [Comparing traditional functions to arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#comparing\_traditional\_functions\_to\_arrow\_functions) <a href="comparing_traditional_functions_to_arrow_functions" id="comparing_traditional_functions_to_arrow_functions"></a>

Let's decompose a "traditional anonymous function" down to the simplest "arrow function" step-by-step:

**Note:** Each step along the way is a valid "arrow function".

```
// Traditional Anonymous Function
function (a){
  return a + 100;
}

// Arrow Function Break Down

// 1. Remove the word "function" and place arrow between the argument and opening body bracket
(a) => {
  return a + 100;
}

// 2. Remove the body braces and word "return" -- the return is implied.
(a) => a + 100;

// 3. Remove the argument parentheses
a => a + 100;
```

Copy to Clipboard

The { braces } and ( parentheses ) and "return" are required in some cases.

For example, if you have **multiple arguments** or **no arguments**, you'll need to re-introduce parentheses around the arguments:

```
// Traditional Anonymous Function
function (a, b){
  return a + b + 100;
}

// Arrow Function
(a, b) => a + b + 100;

// Traditional Anonymous Function (no arguments)
let a = 4;
let b = 2;
function (){
  return a + b + 100;
}

// Arrow Function (no arguments)
let a = 4;
let b = 2;
() => a + b + 100;
```

Copy to Clipboard

Likewise, if the body requires **additional lines** of processing, you'll need to re-introduce braces **PLUS the "return"** (arrow functions do not magically guess what or when you want to "return"):

```
// Traditional Anonymous Function
function (a, b){
  let chuck = 42;
  return a + b + chuck;
}

// Arrow Function
(a, b) => {
  let chuck = 42;
  return a + b + chuck;
}
```

Copy to Clipboard

And finally, for **named functions** we treat arrow expressions like variables:

```
// Traditional Function
function bob (a){
  return a + 100;
}

// Arrow Function
let bob = a => a + 100;
```

Copy to Clipboard

### [Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#syntax) <a href="syntax" id="syntax"></a>

#### [Basic syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#basic\_syntax) <a href="basic_syntax" id="basic_syntax"></a>

One param. With simple expression return is not needed:

```
param => expression
```

Copy to Clipboard

Multiple params require parentheses. With simple expression return is not needed:

```
(param1, paramN) => expression
```

Copy to Clipboard

Multiline statements require body braces and return:

```
param => {
  let a = 1;
  return a + param;
}
```

Copy to Clipboard

Multiple params require parentheses. Multiline statements require body braces and return:

```
(param1, paramN) => {
   let a = 1;
   return a + param1 + paramN;
}
```

Copy to Clipboard

#### [Advanced syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#advanced\_syntax) <a href="advanced_syntax" id="advanced_syntax"></a>

To return an object literal expression requires parentheses around expression:

```
params => ({foo: "a"}) // returning the object {foo: "a"}
```

Copy to Clipboard

[Rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) are supported:

```
(a, b, ...r) => expression
```

Copy to Clipboard

[Default parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default\_parameters) are supported:

```
(a=400, b=20, c) => expression
```

Copy to Clipboard

[Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring\_assignment) within params supported:

```
([a, b] = [10, 20]) => a + b;  // result is 30
({ a, b } = { a: 10, b: 20 }) => a + b; // result is 30
```

Copy to Clipboard

### [Description](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#description) <a href="description" id="description"></a>

#### [Arrow functions used as methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#arrow\_functions\_used\_as\_methods) <a href="arrow_functions_used_as_methods" id="arrow_functions_used_as_methods"></a>

As stated previously, arrow function expressions are best suited for non-method functions. Let's see what happens when we try to use them as methods:

```
'use strict';

var obj = { // does not create a new scope
  i: 10,
  b: () => console.log(this.i, this),
  c: function() {
    console.log(this.i, this);
  }
}

obj.b(); // prints undefined, Window {...} (or the global object)
obj.c(); // prints 10, Object {...}
```

Copy to Clipboard

Arrow functions do not have their own `this`. Another example involving [`Object.defineProperty()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Object/defineProperty):

```
'use strict';

var obj = {
  a: 10
};

Object.defineProperty(obj, 'b', {
  get: () => {
    console.log(this.a, typeof this.a, this); // undefined 'undefined' Window {...} (or the global object)
    return this.a + 10; // represents global object 'Window', therefore 'this.a' returns 'undefined'
  }
});
```

Copy to Clipboard

#### [call, apply and bind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#call\_apply\_and\_bind) <a href="call_apply_and_bind" id="call_apply_and_bind"></a>

The [`call`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/call), [`apply`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/apply) and [`bind` ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/bind)methods are **NOT suitable** for Arrow functions -- as they were designed to allow methods to execute within different scopes -- because **Arrow functions establish "this" based on the scope the Arrow function is defined within.**

For example [`call`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/call), [`apply`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/apply) and [`bind` ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function/bind)work as expected with Traditional functions, because we establish the scope for each of the methods:

```
// ----------------------
// Traditional Example
// ----------------------
// A simplistic object with its very own "this".
var obj = {
    num: 100
}

// Setting "num" on window to show how it is NOT used.
window.num = 2020; // yikes!

// A simple traditional function to operate on "this"
var add = function (a, b, c) {
  return this.num + a + b + c;
}

// call
var result = add.call(obj, 1, 2, 3) // establishing the scope as "obj"
console.log(result) // result 106

// apply
const arr = [1, 2, 3]
var result = add.apply(obj, arr) // establishing the scope as "obj"
console.log(result) // result 106

// bind
var result = add.bind(obj) // establishing the scope as "obj"
console.log(result(1, 2, 3)) // result 106
```

Copy to Clipboard

With Arrow functions, since our `add` function is essentially created on the `window` (global) scope, it will assume `this` is the window.

```
// ----------------------
// Arrow Example
// ----------------------

// A simplistic object with its very own "this".
var obj = {
    num: 100
}

// Setting "num" on window to show how it gets picked up.
window.num = 2020; // yikes!

// Arrow Function
var add = (a, b, c) => this.num + a + b + c;

// call
console.log(add.call(obj, 1, 2, 3)) // result 2026

// apply
const arr = [1, 2, 3]
console.log(add.apply(obj, arr)) // result 2026

// bind
const bound = add.bind(obj)
console.log(bound(1, 2, 3)) // result 2026
```

Copy to Clipboard

Perhaps the greatest benefit of using Arrow functions is with DOM-level methods (setTimeout, setInterval, addEventListener) that usually required some kind of closure, call, apply or bind to ensure the function executed in the proper scope.

**Traditional Example:**

```
var obj = {
    count : 10,
    doSomethingLater : function (){
        setTimeout(function(){ // the function executes on the window scope
            this.count++;
            console.log(this.count);
        }, 300);
    }
}

obj.doSomethingLater(); // console prints "NaN", because the property "count" is not in the window scope.
```

Copy to Clipboard

**Arrow Example:**

```
var obj = {
    count : 10,
    doSomethingLater : function(){
        // The traditional function binds "this" to the "obj" context.
        setTimeout( () => {
            // Since the arrow function doesn't have its own binding and
            // setTimeout (as a function call) doesn't create a binding
            // itself, the "obj" context of the traditional function will
            // be used within.
            this.count++;
            console.log(this.count);
        }, 300);
    }
}

obj.doSomethingLater();
```

Copy to Clipboard

#### [No binding of `arguments`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#no\_binding\_of\_arguments) <a href="no_binding_of_arguments" id="no_binding_of_arguments"></a>

Arrow functions do not have their own [`arguments` object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments). Thus, in this example, `arguments` is a reference to the arguments of the enclosing scope:

```
var arguments = [1, 2, 3];
var arr = () => arguments[0];

arr(); // 1

function foo(n) {
  var f = () => arguments[0] + n; // foo's implicit arguments binding. arguments[0] is n
  return f();
}

foo(3); // 3 + 3 = 6
```

Copy to Clipboard

In most cases, using [rest parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/rest\_parameters) is a good alternative to using an `arguments` object.

```
function foo(n) {
  var f = (...args) => args[0] + n;
  return f(10);
}

foo(1); // 11
```

Copy to Clipboard

#### [Use of the `new` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#use\_of\_the\_new\_operator) <a href="use_of_the_new_operator" id="use_of_the_new_operator"></a>

Arrow functions cannot be used as constructors and will throw an error when used with `new`.

```
var Foo = () => {};
var foo = new Foo(); // TypeError: Foo is not a constructor
```

Copy to Clipboard

#### [Use of `prototype` property](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#use\_of\_prototype\_property) <a href="use_of_prototype_property" id="use_of_prototype_property"></a>

Arrow functions do not have a `prototype` property.

```
var Foo = () => {};
console.log(Foo.prototype); // undefined
```

Copy to Clipboard

#### [Use of the `yield` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#use\_of\_the\_yield\_keyword) <a href="use_of_the_yield_keyword" id="use_of_the_yield_keyword"></a>

The [`yield`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/yield) keyword may not be used in an arrow function's body (except when permitted within functions further nested within it). As a consequence, arrow functions cannot be used as generators.

#### [Function body](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#function\_body) <a href="function_body" id="function_body"></a>

Arrow functions can have either a "concise body" or the usual "block body".

In a concise body, only an expression is specified, which becomes the implicit return value. In a block body, you must use an explicit `return` statement.

```
var func = x => x * x;
// concise body syntax, implied "return"

var func = (x, y) => { return x + y; };
// with block body, explicit "return" needed
```

Copy to Clipboard

#### [Returning object literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow\_functions#returning\_object\_literals) <a href="returning_object_literals" id="returning_object_literals"></a>

Keep in mind that returning object literals using the concise body syntax `params => {object:literal}` will not work as expected.

```
var func = () => { foo: 1 };
// Calling func() returns undefined!

var func = () => { foo: function() {} };
// SyntaxError: function statement requires a name
```

Copy to Clipboard

This is because the code inside braces ({}) is parsed as a sequence of statements (i.e. `foo` is treated like a label, not a key in an object literal).

You must wrap the object literal in parentheses:

```
var func = () => ({ foo: 1 });
```
