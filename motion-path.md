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

```html
<script src="https://unpkg.com/gsap@3/dist/MotionPathPlugin.min.js" />
```

```js
//register the plugin
gsap.registerPlugin(MotionPathPlugin);

// animate the planet along the path with ID of orbit-outer
gsap.to('#planet', {
  motionPath: {
    path: '#orbit-outer',
  },
  duration: 2,
});

// advanced options
gsap.to('#planet', {
  motionPath: {
    path: '#orbit-outer', // animate along the path with this ID
    align: '#orbit-outer', // align element with the path
    alignOrigin: [0.5, 0.5], // align with the center of the element
    autoRotate: true, // rotate along the path
    start: 0, // start halfway along the path
    end: 1, // end at the end of the path
  },
  duration: 5,
  repeat: -1,
  immediateRender: true, // avoid the element 'jumping' to start position
  ease: 'none',
});
```

## Code along

<iframe height="400" style="width: 100%;" scrolling="no" title="Motion path plugin - orbits &amp; morphing" src="https://codepen.io/svganimationworkshop/embed/WNvOXEQ?height=265&theme-id=light&default-tab=html,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/WNvOXEQ'>Motion path plugin - orbits &amp; morphing</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
