---
title: CSS animation {docsify-ignore}
---

### Animation properties

```css
.element {
  animation-name: myanimation;
  animation-duration: 2s;
  animation-delay: 0s;
  animation-iteration-count: 1 / infinite;
  animation-direction: normal/reverse/alternate/alternate-reverse;
  animation-play-state: paused/running;
  animation-fill-mode: forwards/backwards/none/both;
  animation-timing-function: ease;
}
```

### Animation shorthand & keyframes

> Any order will work, but delay must be after duration.

```css
.element {
  animation: move 3s infinite alternate both ease 2s;
}

@keyframes move {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(2);
  }
  100% {
    transform: scale(0);
  }
}
```

### Animation fill mode demo

<iframe height="400" style="width: 100%;" scrolling="no" title="Animation fill mode demo" src="https://codepen.io/svganimationworkshop/embed/xxGrXjR?height=265&theme-id=default&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/xxGrXjR'>Animation fill mode demo</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise

Use CSS to animate the SVG elements you made in the previous exercise.
