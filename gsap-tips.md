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

GreenSock will use the elements bounding box as reference by default. But you can also use svgOrigin and specific coordinate values.

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
