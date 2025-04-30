# Javascript - Array 
[Array Methods (W3School)](https://www.w3schools.com/js/js_array_methods.asp#mark_splice)

# Add to array
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];

fruits.push["Kiwi"]; // add 'kiwi' to the end of the array
fruits.unshift["Kiwi"]; // add 'kiwi' to the start of the array

// add array(s) to the first array (DOESN'T CHANGE the existing array - returns a new array)
let newFruits = fruits.concat(<array1>,<array2>,...); 

// add the new element(s) at 'x', and remove the 'y' numbers of elements
fruits.splice(x,y,"Lemon","Kiwi");
```

# Remove from array
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

# Manipulate the array
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.toString(); // ["Banana,Orange,Apple,Mango"]

// convert a multi dimensional array into a 1D array
const myArr = [[1,2],[3,4],[5,6]];
const newArr = myArr.flat(); // newArr = [1,2,3,4,5,6];
```

