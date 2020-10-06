---
title: Accessibility {docsify-ignore}
---

[Accessible SVG's - CSS tricks](https://css-tricks.com/accessible-svgs/)

## Screenreaders

We can add title's and descriptions to our SVG's for screenreader accessibility

!> A title and description will be enough for most cases.But there are bugs in firefox so for now, to be safe use aria-labelledby.

```html
<svg viewBox="0 0 720 800" aria-labelledby="galaxyTitle galaxyDesc" role="img">
  <title id="galaxyTitle">SVG Galaxy</title>
  <desc id="galaxyDesc">An animated galaxy world.</desc>
</svg>
```

For infographics you can make the SVG DOM traversable by using role="group"

```
<svg viewBox="0 0 720 800" aria-labelledby="graphtitle graphDesc" role="group">
  <title id="graphTitle">Infographic</title>
  <desc id="graphDesc">An important infographic.</desc>
  <g id="chart" role="list">
  </g>
</svg>
```

## Vestibular disorders

Some people experience motion sickness when faced with certain types of animation.

We can adjust their experience with the prefers reduced motion media query.

```css
/* Remove animation for people that prefer not to see it */
@media (prefers-reduced-motion: reduce) {
  svg {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```

```js
const animationIsOk = window.matchMedia(
  "(prefers-reduced-motion: no-preference)"
);

if (animationIsOk) {
  // do all the animation.
}
```
