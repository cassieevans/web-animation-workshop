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
