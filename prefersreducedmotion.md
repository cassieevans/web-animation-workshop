## Vestibular disorders

Some people experience motion sickness when faced with certain types of animation.
We can adjust their experience with the prefers reduced motion media query.

'Animations that move an object across a large amount of space are most apt to trigger a negative response for someone suffering from a vestibular disorder. The physical size of screen matters less than the size of the motion relative to the screen space available—so a small button with a 3D rotation probably won’t cause trouble, but a full-screen wipe transition covering the entire screen likely would. Animation that involves only non-moving properties, like opacity, color, and blurs, are unlikely to be problematic.'

[From this wonderful article by Val Head](https://alistapart.com/article/designing-safer-web-animation-for-motion-sensitivity/)

## CSS

```css
/* Remove animation for people that prefer not to see it */
@media (prefers-reduced-motion: reduce) {
  svg {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
  }
}
```

## JS

```js
const animationIsOk = window.matchMedia(
  '(prefers-reduced-motion: no-preference)'
).matches;

if (animationIsOk) {
  // do all the animation.
}
```
