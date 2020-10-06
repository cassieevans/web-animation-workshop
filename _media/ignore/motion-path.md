---
title: Motion Path Animation <!-- {docsify-ignore} -->
---

## Resources and snippets

[Motion Path Plugin - docs](https://greensock.com/docs/v3/Plugins/MotionPathPlugin)
[Motion Paths – Past, Present and Future](https://tympanus.net/codrops/2019/12/03/motion-paths-past-present-and-future/)

### CSS motion path module

!> Experimental technology, browser support is patchy still.

```css
.rocket {
  transform-box: fill-box;
  offset-anchor: 50% 50%;
  offset-rotate: auto;
  offset-path: path('M20.2....');
  animation: move 10s forwards linear;
}

@keyframes move {
  to {
    offset-distance: 100%;
  }
}
```

### GSAP motion path plugin - Free plugin

```js
//register the plugin
gsap.registerPlugin(MotionPathPlugin);

// animate the rocket along the path
gsap.to(".rocket", {
 motionPath: {
  path: "#path",
 },
 duration: 2,
});

advanced options
gsap.to('.rocket', {
  motionPath: {
    path: "#path", // animate along the path with this ID
    align: "#path", // align element with the path
    alignOrigin:[0.5, 0.5], // align with the center of the element
    autoRotate: true, // rotate along the path
    start: 0.5, // start halfway along the path
    end: 1 // end at the end of the path
  },
  duration: 2,
  repeat: -1,
  immediateRender: true, // avoid the element 'jumping' to start position
});
```

## Exercise

Motion path time!

Try to rotate the planets around their orbits.

[starter pen](https://codepen.io/svganimationworkshop/pen/WNvOXEQ)
