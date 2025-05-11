# Javascript - Array 
[Array Methods (W3School)](https://www.w3schools.com/js/js_array_methods.asp#mark_splice)

[Complete guide](https://javascript.info/array-methods)

[Great Tutorial for `map`, `sort`, `reduce`,`filter`](https://www.youtube.com/watch?v=HB1ZC7czKRs)

[Another great tutorial - `some`, `every`, `find`, `findIndex`](https://www.youtube.com/watch?v=QNmRfyNg1lw&ab_channel=WesBos)

## Add to array
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];

fruits.push["Kiwi"]; // add 'kiwi' to the end of the array
fruits.unshift["Kiwi"]; // add 'kiwi' to the start of the array

// add array(s) to the first array (DOESN'T CHANGE the existing array - returns a new array)
let newFruits = fruits.concat(<array1>,<array2>,...); 

// add the new element(s) at 'x', and remove the 'y' numbers of elements
fruits.splice(x,y,"Lemon","Kiwi");
```

## Remove from array
> [!CAUTION]
> Do not use `delete()` as it leaves undefined holes in the array\
> use `pop()` or `shift()` instead
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];

fruits.pop(); // ["Banana","Orange","Apple"] (remove last element)
fruits.shift(); // ["Orange", "Apple", "Mango"] (remove first element)

// without new elements, it can remove elements
fruits.splice(0,2); // ["Apple","Mango"]

// DOESN'T CHANGE original array
const newFruits = fruits.slice(3); // newFruits = ["Mango"]

// toSpliced(x,y) - similar to splice but DOESN'T CHANGE original array
const months = ["Jan", "Feb", "Mar", "Apr"];
const spliced = months.toSpliced(1, 1); // ["Jan","Mar","Apr"]
```

```js
// remove multiple items from array
const removeFromArray = function(array, ...removeItem) {
  let i = 0;
  while (i<removeItem.length) {
    array = array.filter(matchItem);
    i++;
  }
  return array;

  function matchItem(item) {
    return item !== removeItem[i];
  }
};
```

## Manipulate the array [:link:](https://www.theodinproject.com/lessons/foundations-object-basics)
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.toString(); // ["Banana,Orange,Apple,Mango"]

// convert a multi dimensional array into a 1D array
const myArr = [[1,2],[3,4],[5,6]];
const newArr = myArr.flat(); // newArr = [1,2,3,4,5,6];
```

### `map` - iterate the whole array
`map` is a easy way to iterate array, it expects `callback` as an argument:
```js
array.map(()=> {
  ...
});
```

For example:
```js
const arr = [1, 2, 3, 4, 5];
const mappedArr = arr.map((num) => num + 1);
console.log(mappedArr); // Outputs [2, 3, 4, 5, 6]
```

### `filter` - iterate and return with conditions
similar to `map`, it goes through every item in an array, and only spits out those are `true`, for example:
```js
function isOdd(num) {
  return num % 2 !== 0;
}
const arr = [1, 2, 3, 4, 5];
const oddNums = arr.filter(isOdd);
console.log(oddNums); // Outputs [1, 3, 5];
console.log(arr); // Outputs [1, 2, 3, 4, 5], original array is not affected
```

### `reduce` - iterate and return a single value (reduce from an array to a point)
It iterates items one by one, and spits them into one piece. The [syntax](https://www.w3schools.com/jsref/jsref_reduce.asp): 
```js
array.reduce(function(total, currentValue, currentIndex, arr), initialValue)
```
For example:
```js
const arr = [1, 2, 3, 4, 5];
const productOfAllNums = arr.reduce((total, currentItem) => {
  return total * currentItem;
}, 1); // initialValue = 1
console.log(productOfAllNums); // Outputs 120;
console.log(arr); // Outputs [1, 2, 3, 4, 5]
```
