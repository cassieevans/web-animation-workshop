### When to use CSS?

- Your animation has 3 or less steps.
- You don't want the additional weight of a JS library.
- You're animating transforms & opacity.
- You're doing a simple stroke animation.
- You don't mind having no animation in IE.
- You're having fun and you love CSS.

### Keyframes

Keyframes hold what styles the element will have at certain times.

you can use percentages

```css
@keyframes spin-and-grow {
  0% {
    transform: rotate(0);
  }
  50% {
    transform: rotate(360deg);
  }
  100% {
    transform: scale(2);
  }
}
```

Or `to` and `from`

```css
@keyframes spin-and-grow {
  to {
    transform: rotate(0);
  }
  from {
    transform: scale(2);
  }
}
```

We bind the animation keyframes to an element (or multiple elements) by it's name

### Animation properties

```css
.element {
  animation-name: spin-and-grow; /* the name of the animation keyframes */
  animation-duration: 2s; /* the length of the animation */
  animation-delay: 0s; /* the time before the animation starts */
  animation-iteration-count: 1 / infinite; /* how many times the animation will play*/
  animation-direction: normal/reverse/alternate/alternate-reverse; /* which direction it will run it*/
  animation-play-state: paused/running; /* playing or paused*/
  animation-fill-mode: forwards/backwards/none/both; /* what effect the animation styles will have on the element outside of the animation*/
  animation-timing-function: ease; /* the ease of the animation*/
}
```

### Animation shorthand

> Any order will work, but delay must be after duration.

```css
.element {
  animation: spin-and-grow 3s infinite alternate both ease 2s;
}
```

### Some commonly animated properties to play with

translations can be set as pixel values which will be read as SVG units, or percentages.

| Property                     | Value                                                        |
| ---------------------------- | ------------------------------------------------------------ |
| transform: translateX(100px) | translateY(100px) or translateY(100%)                        |
| transform: translateY(100px) | translateY(100px) or translateY(100%)                        |
| transform: scale()           | numeric value e.g. scale(2)                                  |
| transform: scaleX()          | numeric value e.g. scaleX(2)                                 |
| transform: scaleY()          | numeric value e.g. scaleY(2)                                 |
| transform: rotate()          | degrees from 0 to 360 e.g. rotate(90deg)                     |
| transform: rotateX()         | degrees from 0 to 360 e.g. rotateX(90deg)                    |
| transform: rotateY()         | degrees from 0 to 360 e.g. rotateY(90deg)                    |
| transform-origin:            | percentages or named values e.g. - 50% 100% or center bottom |
| fill:                        | color value e.g. - hsl(324, 98%, 78%)                        |
| stroke-color:                | color value e.g. - hsl(324, 98%, 78%)                        |
| opacity:                     | number from 0 to 1 - e.g. 0.5                                |

### Animation fill mode demo

<iframe height="400" style="width: 100%;" scrolling="no" title="Animation fill mode demo" src="https://codepen.io/svganimationworkshop/embed/xxGrXjR?height=265&theme-id=default&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/xxGrXjR'>Animation fill mode demo</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise

Using CSS, experiment with adding an animation to your potato critter.

The original [is here if you need it.](https://codepen.io/svganimationworkshop/pen/WNwBqGG)
