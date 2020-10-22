### Resources

[Scrolltrigger Docs](https://greensock.com/docs/v3/Plugins/ScrollTrigger)

simple example

```js
gsap.to('.box', {
  scrollTrigger: '.box', // start the animation when ".box" enters the viewport (once)
  x: 500,
});
```

advanced example

```js
gsap.registerPlugin(ScrollTrigger);

const tl = gsap.timeline({
  scrollTrigger: {
    markers: true,
    trigger: '#svg',
    start: 'center bottom',
    end: 'center top',
    scrub: 1,
    // toggleActions: "play pause resume reset"
  },
});
tl.from('.flower', {
  duration: 5,
  drawSVG: '100%',
  ease: 'power1.inOut',
});
```

<iframe height="400" style="width: 100%;" scrolling="no" title="Draw SVG - scrolltrigger" src="https://codepen.io/svganimationworkshop/embed/WNxxGZy?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/WNxxGZy'>Draw SVG - scrolltrigger</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
