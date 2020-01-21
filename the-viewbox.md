---
title: The Viewbox
---

# The Viewbox

> SVG space is like a massive bit of graph paper, stretching for infinity in all directions that you can plot graphic elements on.

```html
<svg viewBox="0 0 400 300">
  <!-- ..elements -->
</svg>
```

- viewBox is a string, four numbers separated by spaces
- x and y set the position of the top, left corner of our view box.
- width and height set the number of "units" that are visible

Like a window into infinite SVG space.
[Or... like a telescope](https://wattenberger.com/guide/scaling-svg)

##### You can even animate a viewbox!

<iframe height="400" style="width: 100%;" scrolling="no" title="Animated Flow Chart to demo animating viewBox" src="https://codepen.io/sdras/embed/preview/VjvGJM?height=265&theme-id=default&default-tab=html,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/sdras/pen/VjvGJM'>Animated Flow Chart to demo animating viewBox</a> by Sarah Drasner
  (<a href='https://codepen.io/sdras'>@sdras</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise time

Oh no! We're on a space mission and we've lost an astronaut in deep space.

Luckily we can use [element.getBBox()](https://developer.mozilla.org/en-US/docs/Web/API/SVGGraphicsElement/getBBox) to find his co-ordinates and rescue him.

Fork the codepen below. Either set the new coordinate inline in the svg attribute, or use the GSAP tween I have set up to animate him into view.

Don't worry too much about what the GSAP tween is doing, we'll cover that soon!

For now just fill the viewbox variable out with the co-ordinates

[Open codepen](https://codepen.io/cassie-codes/pen/79a66762d1264bb8b3c0e2a0ab2a773e?editors=1010)
