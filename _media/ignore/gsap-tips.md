---
title: GSAP tips <!-- {docsify-ignore} -->
---

!> When using from() tweens you can end up with annoying flashes of your SVG as it is in the HTML before your JS kicks in and moves it to it's initial animation state.

## FOUC

set() is essentially a zero-duration to() tween

We can use it to set initial states for our tweens.

In this case to only show the ufo once the JS has loaded and the ufo has been moved off to the left.

```html
<g id="ufo" opacity="0"></g>
```

```js
gsap.set('ufo', {
  opacity: 1,
});

gsap.from('.ufo', { duration: 1, x: -700 });
```

## transformOrigin & SVGOrigin

Greensock will use the elements bounding box as reference by default. But you can also use svgOrigin and specific coordinate values.

```js
gsap.set('ufo', {
  // set the origin to the elements center
  // (percentages or 'left' 'center etc)
  transformOrigin: '50% 50%',

  // set the origin to a specific SVG coordinate
  // (px values but using svg units)
  svgOrigin: '200px 600px',
});
```
