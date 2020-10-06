---
title: Tweens <!-- {docsify-ignore} -->
---

## Resources

[Tweens - GSAP docs](https://greensock.com/docs/v3/GSAP/Tween)

## What's a tween? <!-- {docsify-ignore} -->

> A Tween does all the animation work - think of it like a high-performance property setter.

Animation on the web basically boils down to changing property values a lot of times per second. A greensock tween takes a starting value, an ending value and then interpolates between them 60 times per second.

The GSAP object has three methods for creating a tween.

A tween is made up of -

- **The method** -
  `gsap.from()`
  `gsap.to()`
  or `gsap.fromTo()`

- **The Target(s)** - the object(s) whose properties you want to animate. This can be selector text like ".class", "#id", etc. Or it can be direct references to elements, generic objects, or even an array of objects
- **And lastly the variables** - an object containing all the properties/values you want to animate, along with any special properties like ease, duration, delay, or onComplete

![tween infographic](_media/tween.png)

## Properties:

Here's some common properties & animation commands along with their corresponding CSS syntax.

| GSAP                       | CSS                                 |
| -------------------------- | ----------------------------------- |
|                            |                                     |
| duration: 1                | animation-duration: 1s              |
| repeat: -1                 | animation-iteration-count: infinite |
| repeat: 2                  | animation-iteration-count: 2        |
| delay: 2                   | animation-delay: 2                  |
| yoyo: true                 | animation-direction: alternate      |
|                            |                                     |
| fill: '#008080'            | fill: #008080                       |
| stroke: '#008080'          | stroke-color: #008080               |
| opacity: 0.5               | opacity: 0.5                        |
| x: 100 (svg units)         | transform: translateX(100px)        |
| y:100 (svg units)          | transform: translateY(100px)        |
| z: 100 (svg units)         | transform: translateZ(100px)        |
| xPercent: 50               | transform: translateX(50%)          |
| yPercent: 50               | transform: translateY(50%)          |
| zPercent: 50               | transform: translateZ(50%)          |
| y: 100                     | transform: translateY(100px)        |
| z: 100                     | transform: translateZ(100px)        |
| scale: 2                   | transform: scale(2)                 |
| scaleX: 2                  | transform: scaleX(2)                |
| scaleY: 2                  | transform: scaleY(2)                |
| scaleZ: 2                  | transform: scaleZ(2)                |
| skew: 10                   | transform: skew(10deg)              |
| skewX: 10                  | transform: skewX(10deg)             |
| skewY: 10                  | transform: skewY(10deg)             |
| rotation: 90               | transform: rotate(90deg)            |
| rotationX: 90              | transform: rotateX(90deg)           |
| rotationY: 90              | transform: rotateY(90deg)           |
| rotationZ: 90              | transform: rotateZ(90deg)           |
| transformOrigin: '50% 50%' | transform-origin: 50% 50%           |

## Exercise

Time to animate your SVG!

Take a look at your animation plan and create the first tween.

You'll need your SVG starter pen from the last exercise.

[Alternately go ahead and use this spaceship SVG](https://codepen.io/svganimationworkshop/pen/wvaerbO?editors=1010)

## Snippets

```js
// Good for exits
gsap.to('#ufo', { duration: 1, x: -700 });

// Good for entrances
gsap.from('#ufo', { duration: 1, x: -700 });

// Good for more control
gsap.fromTo('#ufo', { x: -700 }, { x: 700, duration: 2 });
```
