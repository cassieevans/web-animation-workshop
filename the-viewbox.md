> SVG space is like an infinite bit of graph paper that you can plot graphical elements on. The viewbox determines what area of that graph paper you can see.

![viewport vs viewbox](https://s3.amazonaws.com/media-p.slid.es/uploads/762606/images/6943388/5ad707f2c1abe_viewboxviewport.jpg.d07987b374c7d524e5373efd2057fabe.jpg")

### viewBox? viewport? What's the difference?

- The viewport is the outer SVG region - (like a browser viewport)
- The viewBox defines the portion of the inner coordinate system that is visible.
- The viewBox can be smaller or bigger than the viewport, and it can be fully or partially visible inside the viewport.

&nbsp;

## Viewbox Article demo

[Check out the demo at the bottom...](https://wattenberger.com/guide/scaling-svg)

### The viewBox

```html
<svg viewBox="0 0 400 300">
  <!-- ..elements go here -->
</svg>
```

- The viewBox coordinates are adjusted using the viewBox attribute.
- viewBox is a string, four numbers separated by spaces
- x and y set the position of the top, left corner of our view box.
- width and height set the number of "units" that are visible
- it can be _animated_

### The viewport

- The viewport is the SVG bounding box itself, and the visible area of the SVG image.
- The viewport can be sized with width and height parameters on the SVG itself, or with CSS.
- If you only specify a height _or_ width on the SVG, the SVG's viewport with take on the aspect ratio specified in the viewBox

## Exercise

Oh no! We're on a mission and we've lost an astronaut in deep space.

Luckily she's sent us her co-ordinates using [element.getBBox()](https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/getBBox).

Fork the codepen below to launch a rescue mission!

(Don't worry about what the GSAP tween is doing, we'll cover that soon enough!)

[Open codepen](https://codepen.io/svganimationworkshop/pen/qBdjPpR?editors=1010)
