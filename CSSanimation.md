### When to use CSS to animate SVG?

- Simple hover transitions.
- Your animation has 3 or less steps..
- You don't want the additional weight of a JS library.
- You're animating transforms & opacity.
- You're doing a simple stroke animation.

## Transitions

Transitions are great if you have one state change that you want to alter on a certain interaction - like hover.

```css
.element {
  transition-property: transform|opacity;
  transition-duration: 1s|1000ms;
  transition-timing-function: linear|ease|ease-in|ease-out|ease-in-out|cubic-bezier;
  transition-delay: 1s|1000ms;

  /* or shorthand */
  transition: transform 0.5s ease-out 0.1s;
}

.svg:hover .element {
  transform: transformY(300px);
}
```

## Transition Exercise

Add some transitions to the 'buy stuff' button.

Keep in mind the 'feel' you want to achieve when picking out eases.

Jump over to the [easing section](/easing?id=easing-with-css) if you want a deeper dive.

<iframe height="400" style="width: 100%;" scrolling="no" title="wallet - icon animation" src="https://codepen.io/svganimationworkshop/embed/xxRgYyB?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/xxRgYyB'>wallet - icon animation</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Animation

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

Or `to` and `from` which is a little more like a transition really!

```css
@keyframes spin-and-grow {
  to {
    transform: rotate(0);
  }
  from {
    /* you can stack transforms like so */
    transform: scale(2) rotate(360deg);
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

## Animation Exercise

Using CSS, experiment with a simple animation - 3 steps or less.

If you have your own SVG prepared - go ahead and use that!

If not, you can use this little robot dude or the potato critter from day 1.

<iframe height="400" style="width: 100%;" scrolling="no" title="lil robot dude - starter" src="https://codepen.io/svganimationworkshop/embed/XWNpYBP?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/XWNpYBP'>lil robot dude - starter</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
