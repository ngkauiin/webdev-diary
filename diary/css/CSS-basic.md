## CSS cascade
* ID selectors > class selectors > type selectors
* if other factors are the same, the <b>last</b> defined rule wins
* inheritance - for some properties, the element's desecendants win when other factors are the same.

If both has higher specificity, the one with more class selectors win.

For example - rule 2 > rule 1:
```css
/* rule 1 */
#subsection {
  background-color: yellow;
  color: blue;
}

/* rule 2 */
.main #subsection {
 color: red;
}
```
