## transform-origin

Transform origin sets the center of rotation.

It's an important part of animation, but it's implemented differently in SVG world than it is with HTML elements.

The default origin for HTML DOM elements is at in the middle of the element & for SVG it's the top left corner.

The tricky part with SVG is whether the origin is being measured relative to the element or viewBox.

<iframe height="500" style="width: 100%;" scrolling="no" title="transform-origin " src="https://codepen.io/cassie-codes/embed/507ad4584e018f977e4fb671315831a9?height=265&theme-id=default&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/cassie-codes/pen/507ad4584e018f977e4fb671315831a9'>transform-origin </a> by Cassie Evans
  (<a href='https://codepen.io/cassie-codes'>@cassie-codes</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

The rectangle in the pen below is rotating around the origin `200px 50px`
The pink line is showing the origin being measured relative to the element itself.
The purple line is showing the origin being measured relative to the SVG viewBox.

We can solve this inconsistency in all browsers but IE with [transform-box](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-box)

## transform-box

[current support](https://caniuse.com/?search=transform-box)

### fill-box

The object bounding box is used as the reference box.

### view-box

The nearest SVG viewport is used as the reference box.

```css
.element {
  transform-box: fill-box / view-box;
}
```

> I recommend using CSS animation as progressive enhancement and not animating in IE.

### Progressive enhancement

```css
@supports (transform-box: fill-box) {
  /*animation code here*/
}
```

## Chaining

There's no way to chain animations in CSS.
We can fake chaining with delays, but this is only a comfortable solution for short sequences of around four animations or less. (Depending on your patience.)

```css
:root {
  --first-duration: 3s;
}

.element {
  animation-name: first-animation;
  animation-duration: var(--first-duration);
}

/* animation will play after first animation ends */
.element2 {
  animation-name: second-animation;
  animation-duration: 2s;
  animation-delay: var(--first-duration);
}
```
