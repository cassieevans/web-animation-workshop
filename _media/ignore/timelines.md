---
title: Tweens <!-- {docsify-ignore} -->
---

## Resources

[Timelines - GSAP docs](https://greensock.com/docs/v3/GSAP/Timeline)

## Snippets

```js
// define your timeline
const tl = gsap.timeline();

// add your tweens to the timeline
tl.from('#ufo', { duration: 1, x: -700 });
tl.from('#beam', { duration: 1, scaleX: 0 });
```

### A Timeline is a powerful sequencing tool.

It acts as a container for tweens and other timelines, making it possible to control them as a whole and precisely manage their timing.

When you place tweens in a timeline, tweens have relationships and awareness of each other

By default tweens will follow one after another. But we can overlap or delay tweens by using the position parameter.

```js
tl.from('#ufo', { duration: 1, x: -700 });
// this tween will start 0.5s before the first tween ends
tl.from('#beam', { duration: 1, scaleX: 0 }, '-=0.5');
```

```js
tl.from('#ufo', { duration: 1, x: -700 });
// this tween will start 2s after the first tween ends
tl.from('#beam', { duration: 1, scaleX: 0 }, '+=2');
```

You can also position tweens at an absolute time.

```js
tl.from('#ufo', { duration: 1, x: -700 });
tl.from('#beam', { duration: 1, scaleX: 0 }, 3);
```

Or hang them off a label.

```js
tl.addLabel('myLabel', 0.5);

tl.from('#ufo', { duration: 1, x: -700 });
tl.from('#beam', { duration: 1, scaleX: 0 }, 'myLabel');
```

## Exercise

Following your animation plan: Add a timeline to your pen, and add some tweens to the timeline.

Play around with different position parameters.
