# JAVASCRIPT Basic
[common data type](https://javascript.info/types)

[Built-in string methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

# Comparisons[:link:](https://javascript.info/comparison)
Special rules about `null` and `undefined`
```js
alert( null === undefined ); // false
alert( null == undefined ); // true
```
> [!NOTE]
> `null/undefined` are converted to numbers: `null` becomes `0`, while `undefined` becomes `NaN`.

### Key things to remember
* When values of different types are compared, they get converted to numbers (with the exclusion of a strict equality check).
* Treat any comparison with `undefined/null` except the strict equality `===` with exceptional care.

* Don’t use comparisons `>= > < <=` with a variable which may be `null/undefined`, unless you’re really sure of what you’re doing. If a variable can have these values, check for them separately.

# Logical operation [:link:](https://javascript.info/logical-operators)
### OR `||`
* Evaluates operands from left to right.
* For each operand, converts it to boolean. If the result is `true`, stops and returns the original value of that operand.
* If all operands have been evaluated (i.e. all were `false`), returns the last operand.

#### Interesting example:
```js
alert( alert(1) || 2 || alert(3) );
```
>alert `1` first, then alert `2` as `alert(1)` return `undefined` so falsy.

### NOT `!`
A double NOT `!!` is possible
```js
alert( !!"non-empty string" ); // true
alert( !!null ); // false
```

# Conditionals
[Great practical examples about if & switch statements](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Conditionals) 

### Ternary operator
```js
condition ? run this code : run this code instead`
```

# Function [:link:](https://javascript.info/function-basics)
A function should do exactly what is suggested by its name, no more.

Two independent actions usually deserve two functions, even if they are usually called together (in that case we can make a 3rd function that calls those two).

>[!TIP]
> **Functions == Comments**\
> Functions can be created even if we don’t intend to reuse them. They structure the code and make it readable.

### Function expressions 
Function is a value, Callback functions/Callbacks.
[Explanation](https://javascript.info/function-expressions)

**Function Decalaration** and **Function Expression** example:
```js
// Function Declaration
function sum(a, b) {
  return a + b;
}

// Function Expression
let sum = function(a, b) {
  return a + b;
};
```

> [!NOTE]
> In strict mode, when a **Function Declaration** is within a code block, it’s visible everywhere inside that block. But **not outside of it**.\
> To use it outside of block - use **Function Expression** and assign that outside of the block first.

### Arrow Function
Arrow Functions are function expressions
```js
// arrow functions
let func = (arg1, arg2, ..., argN) => expression;

// full version of the above arrow functions
let func = function(arg1, arg2, ..., argN) {
  return expression;
};
```
[Another example: ](https://javascript.info/arrow-functions-basics)
```js
// full version
ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);

// arrow function of above
ask(
  "Do you agree?",
  () => alert("You agreed."), // arrow function
  () => alert("You canceled the execution.") // arrow function
);
```

### Function Call Stack
*empty*

### Optional Arguments
```js
// ...optArg are stored as an array with any number of arguments 
function func_1(...optArg) {
  return optArg;
}

func_1(3,2); // returns [3,2]
```

# LOOP [:link:](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Loops)
### The for... of loop
```js
const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

for (const cat of cats) {
  console.log(cat);
}
```

### map() and filter()
`map()` example: 
```js
function toUpper(string) {
  return string.toUpperCase();
}

const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const upperCats = cats.map(toUpper);

console.log(upperCats);
// [ "LEOPARD", "SERVAL", "JAGUAR", "TIGER", "CARACAL", "LION" ]
```
`filter()` exmaple:
```js
function lCat(cat) {
  return cat.startsWith("L");
}

const cats = ["Leopard", "Serval", "Jaguar", "Tiger", "Caracal", "Lion"];

const filtered = cats.filter(lCat);

console.log(filtered);
// [ "Leopard", "Lion" ]
```
