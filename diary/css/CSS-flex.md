# Flexbox
flex-container basic properties:
```css
.container {
  display: flex; 
}
```

flex-item basic properties:
```css
.item {
  flex: 1;
  /* flex-item can also be a flex-container with flex-items in it using the below code*/
  /* display: flex; */
}
```
## [Flex](https://www.theodinproject.com/lessons/foundations-growing-and-shrinking) :link:
`flex` is a shorthand for `flex-gorw`, `flex-shrink`, `flex-basis`. 

`flex: <number [1,inf]>` = `flex: <number> 1 0`: grow proportionally.

`flex: initial` = `flex: 0 1 auto`: doesn't grow but can shrink.

`flex: auto` = `flex: 1 1 auto`: can grow and shrink. (fully flexible)

`flex: none` = `flex: 1 1 auto`: doesn't grow nor shrink. (fully inflexible)



[`flex` basic shorthand values](https://www.w3.org/TR/css-flexbox-1/#flex-common)

[another good explanation about `flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)

### flex-grow
`flex-grow` - specify how quick the item grows. E.g. `flex-grow: 2` means it will grow twice the size of the other.

### flex-shrink
`flex-shrink` - specify how quick the item shrink. If you don't want the item to shrink, set `flex-shrink: 0` <b>AND</b> `flex-basis: auto`, which will stop the item from <b> shrinking smaller than the <i>given width</i></b>.

### flex-basis
With the basis set to `0`, those items would ignore the item’s width, and everything would shrink evenly. Using `auto` as a `flex-basis` tells the item to check for a width declaration
