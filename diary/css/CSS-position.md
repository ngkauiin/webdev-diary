## BOX model
Generally, reset the default box sizing to the follow:
```css
* {
  padding: 0;
  margin: 0;

  /* box-sizing default as content-box */
  box-sizing: border-box;
}
```
`border-box` is useful when you want the width and height of the element to be exactly what you input (excluding margin size). [More explanation](https://www.youtube.com/watch?v=rIO5326FgPE&ab_channel=WebDevSimplified). 

E.g. if `height:100px; width:100px`, the size of the box is actually `100px`x`100px` including padding and border size. Without setting `border-box`, the size will be <b> `100px`+`100px`+the size of padding and border</b>, which add complication to styling as you have to do the math.

