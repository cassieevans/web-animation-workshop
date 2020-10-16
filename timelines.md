### A Timeline is a powerful sequencing tool.

It acts as a container for tweens and other timelines, making it possible to control them as a whole and precisely manage their timing.

When you place tweens in a timeline, tweens have relationships and awareness of each other

By default tweens will follow one after another. But we can overlap or delay tweens by using the position parameter.


### fork this and code along

<iframe height="500" style="width: 100%;" scrolling="no" title="Timeline Demo - code along" src="https://codepen.io/svganimationworkshop/embed/ExyKWaq?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/ExyKWaq'>Timeline Demo - code along</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

[Timelines - GSAP docs](https://greensock.com/docs/v3/GSAP/Timeline)

## Snippets

```js
// define your timeline
const tl = gsap.timeline();

// add your tweens to the timeline...

gsap.from('#ufo', { duration: 1, x: -450 });
// becomes
tl.from('#ufo', { duration: 1, x: -450 });
```


```js
tl.from('#ufo', { duration: 1, x: -450 });
// this tween will start 0.5s before the first tween ends
tl.from('#beam', { duration: 1, scaleX: 0 }, '-=0.5');
```

```js
tl.from('#ufo', { duration: 1, x: -450 });
// this tween will start 2s after the first tween ends
tl.from('#beam', { duration: 1, scaleX: 0 }, '+=2');
```

You can also position tweens at an absolute time.

```js
tl.from('#ufo', { duration: 1, x: -450 });
tl.from('#beam', { duration: 1, scaleX: 0 }, 3);
```

Use pointers

```js
tl.from('#ufo',{ duration: 1, x: -450 })
tl.from('#beam',{ duration: 1, scaleX: 0 }, "<")
```
Or hang them off a label.

```js
tl.addLabel('myLabel', 0.5);

tl.from('#ufo', { duration: 1, x: -450 });
tl.from('#beam', { duration: 1, scaleX: 0 }, 'myLabel');
```

## Exercise

Following your animation plan: Add a timeline to the pen you were working on yesterday, and add some tweens to it!

Play around with different position parameters.
