
---
title: Issues with CSS animation {docsify-ignore}
---

## Resources

[Transform-box - MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-box)

## ```transform-origin```

Transform origin is implemented differently in SVG world than it is with HTML elements.

HTML DOM elements measure transform-origin from their own top left corner, and the default origin is at in the middle of the element.

With SVG, in some browsers, transforms are measured from the SVG canvas. and in other browsers, they're measured from the element itself. The default origin is always the top left corner.
Because of this it's common to get different results for your animation in different browsers.

The rectangle in the pen below is rotating around the origin ```200px 50px```

The pink line is showing the origin being measured from the SVG element itself.

The purple line is showing the origin being measured from the SVG canvas.

<iframe height="400" style="width: 100%;" scrolling="no" title="transform-origin " src="https://codepen.io/cassie-codes/embed/507ad4584e018f977e4fb671315831a9?height=265&theme-id=default&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/cassie-codes/pen/507ad4584e018f977e4fb671315831a9'>transform-origin </a> by Cassie Evans
  (<a href='https://codepen.io/cassie-codes'>@cassie-codes</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

We can solve this in CSS with a relatively new CSS property

## ```transform-box```

### fill-box
The object bounding box is used as the reference box.

### view-box

The nearest SVG viewport is used as the reference box.

```css
.element {
  transform-box: fill-box / view-box;
}
```
It's not supported in edge or internet explorer (yet) so I would recommend using animation as progressive enhancement and not animating in those browsers.

### Progressive enhancement

```css
@supports (transform-box: fill-box){  
  /*animation code here*/
}
```

## Chaining

There's no way to chain animations in CSS, we can fake chaining with delays, but this is only a comfortable solution for short sequences of around four animations or less.


```css
:root {
  first-duration: 3s;
}

.element {
    animation-name: first-animation;
    animation-duration: var(--first-duration);
}

.element2 {
    animation-name: second-animation;
    animation-duration: 2s;
    animation-delay: var(--first-duration);
}
```