---
title: Morphing {docsify-ignore}
---

## Resources and snippets

[Morph SVG plugin](https://greensock.com/docs/v3/Plugins/MorphSVGPlugin)

> MorphSVGPlugin morphs SVG paths by animating the data inside the d attribute

You hand greensock the start shape and the destination shape and it does all the really complicated calculations for you.

Remember to hide the destination shape with opacity. Because we're just using the path data to morph the initial shape, we don't need the destination shape visible in the svg

```html
<svg viewBox="0 0 100 100">
  <path id="circle" d="M1365.412..." />
  <path id="hippo" opacity="0" d="M1313...." />
</svg>
```

### GSAP motion path plugin - Free plugin

```js
gsap.registerPlugin(MorphSVGPlugin);

gsap.to("#circle", {
  duration: 2,
  morphSVG: {
    shape: "#hippo"
  }
});
```

## Exercise

Usiong the same pen as last time, find the black hole in your orbit pen and make an explosion using morph svg.

[starter pen](https://codepen.io/cassie-codes/pen/qBdEvKv?editors=1010)
