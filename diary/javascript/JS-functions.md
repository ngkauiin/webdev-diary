# Practical Reuseable Functions

## Rounds number to any decimal places
[reference](https://stackoverflow.com/questions/7342957/how-do-you-round-to-one-decimal-place-in-javascript)
```js
function roundNumberTo(num, precision) {
let multiplier = Math.pow(10, precision || 0);
return Math.round(num*multiplier)/multiplier;
}
```