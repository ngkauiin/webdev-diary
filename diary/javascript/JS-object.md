# Object

## Fundamental [:link:](https://javascript.info/object)
### Access key
Access keys in object using square bracket
```js

let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

let key = "likes birds";

// same as user["likes birds"] = true;
user[key] = true;
```

### Computed properties
The following is the same.
```js
let fruit = prompt("Which fruit to buy?", "apple");

let bag = {
  [fruit]: 5, // the name of the property is taken from the variable fruit
};

alert( bag.apple ); // 5 if fruit="apple"
```
```js
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {};

// take property name from the fruit variable
bag[fruit] = 5;
```
> [!NOTE]
> Most of the time, when property names are known and simple, the dot is used. And if we need something more complex, then we switch to square brackets.

### Property value shorthand
```js
function makeUser(name, age) {
  return {
    name, // same as name: name
    age, // same as age: age
    // ...other properties
  };
}

let user = makeUser("John", 30);
alert(user.name); // John
```

### Property existence test, `in` operator
This is used to check if a key exists. The syntax is:
```js
"key" in object
```

## Reference
> [!IMPORTANT]
> When you define a **primitive** variable, it will contain a **copy of the information** provided to it. When you define an **object** variable, it will contain a **reference** to the object provided to it.

The following example is an good example:
```js
function increaseCounterObject(objectCounter) {
  objectCounter.counter += 1;
}

function increaseCounterPrimitive(primitiveCounter) {
  primitiveCounter += 1;
}

const object = { counter: 0 };
let primitive = 0;

increaseCounterObject(object); // 1
increaseCounterPrimitive(primitive); // 0, unchanged
```
`increaseCounterPrimitive(primitiveCounter)` where `primitiveCounter` is pointing to another reference, unless we change the function to:
```js
function increaseCounterObject(objectCounter) {
  objectCounter.counter += 1;
}

function increaseCounterPrimitive() {
  primitive += 1; // here we directly change the variable, which will have the same reference
}

const object = { counter: 0 };
let primitive = 0;

increaseCounterObject(object); // 1
increaseCounterPrimitive()
console.log(primitive) // 1
```