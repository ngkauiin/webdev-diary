# HTML note

## VSCode built-in shortcut to generate boilerplate
just type "!" then press "Enter"/"Tab" to build the boilerplate

## Link and Image
### Opening links in a new tab
use attribute `target` to specify where the link will be opened. 

Default `target="_self"` - open in the current tab.

`target="_blank"` - open in a new tab or window (depends on browser settings)

Always pair `target="_blank"` with a `ref="noopener norreferrer` for privacy and secuity. [More explaination on rel attribute](https://www.theodinproject.com/lessons/foundations-links-and-images)

```html
<a href="https://www.theodinproject.com/about" target="_blank" rel="noopener noreferrer">About The Odin Project</a>
```

### Four main image formats
JPG - great for general photos amd images (don't allow for transparent pixels)

GIF - great for simple animations

PNG - larger than JPG but deal with opacity. great for icons, techniical diagrams, logos, etc.

SVG - great for responsive design, where the image is vector-based and can be changed to any dimensions without loss of quality. 
[More on these](https://internetingishard.netlify.app/html-and-css/links-and-images/#image-formats)

# Run JS in HTML
Run JS after the HTML is parsed so the DOM manipulation can work as desired, otherwise it won't work. One way of doing it is to add `defer`; or push the `script` after all the DOM if the code is embedded in the HTML file.
```html
<head>
  <script src="js-file.js" defer></script>
</head>
```