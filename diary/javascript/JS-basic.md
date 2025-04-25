# JAVASCRIPT
[common data type](https://javascript.info/types)

[Built-in string methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)

## Comparisons[:link:](https://javascript.info/comparison)
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

## Logical operation [:link:](https://javascript.info/logical-operators)
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

## Conditionals
[Great practical examples about if & switch statements](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Conditionals) 

### Ternary operator
```js
condition ? run this code : run this code instead`
```