### Resources

[Scrolltrigger Docs](https://greensock.com/docs/v3/Plugins/ScrollTrigger)

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.5.1/ScrollTrigger.min.js" />
```

basic example

```js
gsap.to('.box', {
  scrollTrigger: '.box', // start the animation when ".box" enters the viewport (once)
  x: 500,
});
```

with a scrolltrigger object and more settings

```js
// register scrolltrigger
gsap.registerPlugin(ScrollTrigger);

gsap.from('.flower', {
  duration: 5,
  drawSVG: '100%',
  ease: 'power1.inOut', // has no effect if scrub is in use,
  scrollTrigger: {
    trigger: '#svg',
    start: 'center 70%',
    end: 'center 30%',
    scrub: 1,
    pin: true,
    markers: true,
  },
});

// you can also add scrolltrigger to a whole timeline

const tl = gsap.timeline({
  scrollTrigger: {
    markers: true,
    trigger: '#svg',
    start: 'center bottom',
    end: 'center top',
    scrub: 1,
  },
});
```

## Code along with me

<iframe height="400" style="width: 100%;" scrolling="no" title="Draw SVG - scrolltrigger" src="https://codepen.io/svganimationworkshop/embed/WNxxGZy?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/WNxxGZy'>Draw SVG - scrolltrigger</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
