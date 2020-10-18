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
  '(prefers-reduced-motion: no-preference)'
).matches;

if (animationIsOk) {
  // do all the animation.
}
```