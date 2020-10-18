
### Resources

[Read my codrops article on motion paths.](https://tympanus.net/codrops/2019/12/03/motion-paths-past-present-and-future/)

[Motion Path Plugin - GSAP docs](https://greensock.com/docs/v3/Plugins/MotionPathPlugin)

### CSS motion path module

!>Browser support is patchy still.

```css
#planet {
  transform-box: fill-box;
  offset-anchor: 50% 50%;
  offset-rotate: auto;
  offset-path: path('M20.2....'); // path data here
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

// animate the planet along the path with ID of orbit-outer
gsap.to("#planet", {
 motionPath: {
  path: "#orbit-outer",
 },
 duration: 2,
});

// advanced options
gsap.to('#planet', {
  motionPath: {
    path: "#orbit-outer", // animate along the path with this ID
    align: "#orbit-outer", // align element with the path
    alignOrigin:[0.5, 0.5], // align with the center of the element
    autoRotate: true, // rotate along the path
    start: 0, // start halfway along the path
    end: 1 // end at the end of the path
  },
  duration: 2,
  repeat: -1,
  immediateRender: true, // avoid the element 'jumping' to start position
  ease: 'none'
});

```

## Exercise

Motion path time!

Try to rotate the planets around their orbits.

[starter pen](https://codepen.io/svganimationworkshop/pen/WNvOXEQ)
