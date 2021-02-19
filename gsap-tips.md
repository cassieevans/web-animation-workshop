!> When using from() tweens you can end up with annoying flashes of your SVG as the HTML loads before your JS kicks in.

## FOUC

(Flash of unstyled content)

set() is essentially a zero-duration to() tween.

[View set() GSAP docs](<https://greensock.com/docs/v3/GSAP/gsap.set()>)

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

## keyframes

Keyframes are great if you're changing values of the same element in succession.

A common use case is to quickly show an element, do something to it, and then hide it again.

```js
gsap.to('.ufo', {
  keyframes: [
    { opacity: 1, duration: 0.01 },
    { rotation: -360, duration: 1 },
    { opacity: 0, duration: 0.01 },
  ],
});
```

<!--
## registerEffect

[View registerEffect() GSAP docs](<https://greensock.com/docs/v3/GSAP/gsap.registerEffect()>)

```js
// register the effect with GSAP:
gsap.registerEffect({
  name: 'spin',
  defaults: { duration: 1, rotate: 360 }, //defaults get applied to the "config" object
  effect: (targets, config) => {
    return gsap.to(targets, {
      duration: config.duration,
      rotate: config.rotate,
      ease: 'power2.inOut',
      transformOrigin: 'center',
    });
  },
});

// now we can use it like this:
gsap.effects.spin('#ufo');

// Or override the defaults:
gsap.effects.spin('#ufo', { rotate: 90 });
```

## quickSetter() & gsap.ticker

[View quickSetter() GSAP docs](<https://greensock.com/docs/v3/GSAP/gsap.quickSetter()>)

[View gsap.ticker GSAP docs](https://greensock.com/docs/v3/GSAP/gsap.ticker)

quickSetter is a restricted form of .set() that’s more performant, it's especially useful for things that run every tick - like mouse reactive animation.

```js
//reduced example code

var xSet = gsap.quickSetter('#ufo', 'x', 'px');
var ySet = gsap.quickSetter('#ufo', 'y', 'px');

window.addEventListener('mousemove', (e) => {
  mouse.x = e.x;
  mouse.y = e.y;
});

// gsap.ticker is gsap's requestAnimationFrame
gsap.ticker.add(() => {
  xSet(mouse.x);
  ySet(mouse.y);
});
```

### working demo

<iframe height="500" style="width: 100%;" scrolling="no" title="Spaceship - quickSetter" src="https://codepen.io/svganimationworkshop/embed/oNLLLzJ?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/oNLLLzJ'>Spaceship - quickSetter</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe> -->
