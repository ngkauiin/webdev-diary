## BOX model (no flexbox)
### Reset box default value
Generally, reset the default box sizing to the following to help avoid confusion (default padding/margin):
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

---
### Margin
`margin-left: auto` puts box to the most right (or add max margin allows on the left hand side until the right edge of the box meets the web boundary)

`margin: 0 auto` set the box <i>(display needs to be `block`)</i> in horizontally center

---

### Border
`border-style` is required for other border styling to show, otherwise the border doesn't show ANY effects.
```css
/* the below will show and have the desired width and color */
.work {
  border-color: black;
  border-width: 10px;
  border-style: solid;
}

/* the below will NOT show anything, border is not exist, like it is 0px thick and no color*/
.work {
  border-color: black;
  border-width: 10px;
}
```