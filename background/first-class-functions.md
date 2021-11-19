# First Class Functions

## First-class Function

A programming language is said to have **First-class functions** when functions in that language are treated like any other variable. For example, in such a language, a function can be passed as an argument to other functions, can be returned by another function and can be assigned as a value to a variable.

### [Example | Assign a function to a variable](https://developer.mozilla.org/en-US/docs/Glossary/First-class\_Function#example\_assign\_a\_function\_to\_a\_variable) <a href="example_assign_a_function_to_a_variable" id="example_assign_a_function_to_a_variable"></a>

#### [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/First-class\_Function#javascript) <a href="javascript" id="javascript"></a>

```
const foo = function() {
   console.log("foobar");
}
foo(); // Invoke it using the variable
// foobar
```

Copy to Clipboard

We assigned an **Anonymous Function** in a [Variable](https://developer.mozilla.org/en-US/docs/Glossary/Variable), then we used that variable to invoke the function by adding parentheses `()` at the end.

**Note:** **Even if your function was named,** you can use the variable name to invoke it. Naming it will be helpful when debugging your code. _But it won't affect the way we invoke it._

### [Example | Pass a function as an Argument](https://developer.mozilla.org/en-US/docs/Glossary/First-class\_Function#example\_pass\_a\_function\_as\_an\_argument) <a href="example_pass_a_function_as_an_argument" id="example_pass_a_function_as_an_argument"></a>

#### [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/First-class\_Function#javascript\_2) <a href="javascript_2" id="javascript_2"></a>

```
function sayHello() {
   return "Hello, ";
}
function greeting(helloMessage, name) {
  console.log(helloMessage() + name);
}
// Pass `sayHello` as an argument to `greeting` function
greeting(sayHello, "JavaScript!");
// Hello, JavaScript!
```

Copy to Clipboard

We are passing our `sayHello()` function as an argument to the `greeting()` function, this explains how we are treating the function as a **value**.

**Note:** The function that we pass as an argument to another function, is called a [**Callback function**](https://developer.mozilla.org/en-US/docs/Glossary/Callback\_function). _`sayHello` is a Callback function._

### [Example | Return a function](https://developer.mozilla.org/en-US/docs/Glossary/First-class\_Function#example\_return\_a\_function) <a href="example_return_a_function" id="example_return_a_function"></a>

#### [JavaScript](https://developer.mozilla.org/en-US/docs/Glossary/First-class\_Function#javascript\_3) <a href="javascript_3" id="javascript_3"></a>

```
function sayHello() {
   return function() {
      console.log("Hello!");
   }
}
```

Copy to Clipboard

In this example; We need to return a function from another function - _We can return a function because we treated function in JavaScript as a **value**._

**Note:** A function that returns a function is called a **Higher-Order Function**.

Back to our example; Now, we need to invoke `sayHello` function and its returned `Anonymous Function`. To do so, we have two ways:
