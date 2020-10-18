
### Resources

[Morph SVG plugin](https://greensock.com/docs/v3/Plugins/MorphSVGPlugin)

MorphSVGPlugin morphs SVG paths by animating the data inside the d attribute

You hand greensock the start shape and the destination shape and it does all the complicated calculations for you.

> Remember to hide the destination shape with opacity. Because we're just using the path data to morph the initial shape, we don't need the destination shape visible in the svg

```html
<svg viewBox="0 0 100 100">
  <path id="startingShape" d="M1365.412..." />
  <path id="destinationShape" opacity="0" d="M1313...." />
</svg>
```

### GSAP motion path plugin - Free plugin

```js
gsap.registerPlugin(MorphSVGPlugin);

gsap.to('#startingShape', {
  duration: 2,
  morphSVG: {
    shape: '#destinationShape',
  },
});
```

### Linear vs Rotational morphs

Rotational morphs can look smoother than linear ones.

<iframe height="600" style="width: 100%;" scrolling="no" title="MorphSVG type:&quot;rotational&quot; for more natural morphs" src="https://codepen.io/GreenSock/embed/vvjOGq?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/GreenSock/pen/vvjOGq'>MorphSVG type:&quot;rotational&quot; for more natural morphs</a> by GreenSock
  (<a href='https://codepen.io/GreenSock'>@GreenSock</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise

Usiong the same pen as last time, find the black hole in your orbit pen and make an explosion using morph svg.

[starter pen](https://codepen.io/svganimationworkshop/pen/WNvOXEQ)
