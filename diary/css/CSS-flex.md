# Flexbox
[Great tips about flexbox (including min-width, auto margins)](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/)

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

`flex: initial` (Default) = `flex: 0 1 auto`: doesn't grow but can shrink.

`flex: auto` = `flex: 1 1 auto`: can grow and shrink. (fully flexible)

`flex: none` = `flex: 1 1 auto`: doesn't grow nor shrink. (fully inflexible)



[`flex` basic shorthand values](https://www.w3.org/TR/css-flexbox-1/#flex-common)

[another good explanation about `flex`](https://developer.mozilla.org/en-US/docs/Web/CSS/flex)

### flex-grow
> controls how the extra space is distributed when the items are smaller than their container

`flex-grow` - specify how quick the item grows. E.g. `flex-grow: 2` means it will grow twice the size of the other.

### flex-shrink
>controls how space is removed when the items are bigger than their container.

`flex-shrink` - specify how quick the item shrink. If you don't want the item to shrink, set `flex-shrink: 0` **AND** `flex-basis: auto`, which will stop the item from <b> shrinking smaller than the <i>given width</i></b>.

> [!TIP]
> use `min-width: 0px` to prevent content overflow when the container is too small. 

> [!CAUTION]
> But sometimes `min-width: 0px` can make things worse... Use with caution.

### flex-basis
With the basis set to `0`, those items would ignore the item’s width, and everything would shrink evenly. Using `auto` as a `flex-basis` tells the item to check for a width declaration

## Axes
[Useful flexbox cheatsheet](https://flexbox.malven.co/)

`flex-direction` defaults as `row`, which puts the <b>main axis</b> horizontal - left to right, and `column` puts the <b>main axis</b> vertical (top to bottom)

### `flex-direction` - column
`flex-basis` refers to `height` instead of `width` when `flex-direction: column`

`flex-direction: column` needs to have `flex: 1 1 auto`, `flex: 1` won't work as expected unless the parent is given a height, or to use `flex-grow: 1`. [See explanation](https://www.theodinproject.com/lessons/foundations-axes)

## Direction
`justify-content` aligns items across the <b>main axis</b>

`gap: <number>` adds a specified space between flex items, similar to adding a margin to the items themselves
