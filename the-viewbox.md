---
title: The ViewBox {docsify-ignore}
---

## Resources
[Check out this article
<img src="https://s3.amazonaws.com/media-p.slid.es/uploads/762606/images/6894144/Screen_Shot_2019-12-15_at_14.19.15.png">](https://wattenberger.com/guide/scaling-svg)


## SVG space

> SVG space is like a massive bit of graph paper that you can plot graphic elements on. It stretches for infinity in all directions. The viewbox & viewport are like windows into infinite SVG space.

### viewBox? viewport? What's the difference?

- The viewport & viewBox are **BOTH** like windows you look through to see an SVG’s content. You can see the viewBox __*through*__ the viewport.
- The viewBox can be smaller or bigger than the viewport, and it can be fully or partially visible inside the viewport.


&nbsp; 


![viewport vs viewbox](https://s3.amazonaws.com/media-p.slid.es/uploads/762606/images/6943388/5ad707f2c1abe_viewboxviewport.jpg.d07987b374c7d524e5373efd2057fabe.jpg")

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

### The viewport

- The viewport is the SVG bounding box itself, and the visible area of the SVG image.
- The viewport can be sized with width and height parameters on the SVG itself, or with CSS.
- If you only specify a height *or* width on the SVG, the SVG's viewport with take on the aspect ratio specified in the viewBox






## Exercise

Oh no! We're on a mission and we've lost our astronaut in deep space.

Luckily we can use [element.getBBox()](https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/getBBox) to find her co-ordinates and rescue him.

Fork the codepen below. Either set the new coordinate in the viewbox attribute, or update the variables in JS to animate her into view.

Don't worry about what the GSAP tween is doing, we'll cover that soon enough!

[Open codepen](https://codepen.io/svganimationworkshop/pen/qBdjPpR?editors=1010)