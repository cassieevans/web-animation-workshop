### Code along with these pens

<iframe height="500" style="width: 100%;" scrolling="no" title="Staggers - code along" src="https://codepen.io/svganimationworkshop/embed/MWeyjQM?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/MWeyjQM'>Staggers - code along</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<iframe height="500" style="width: 100%;" scrolling="no" title="Advanced staggers - code along" src="https://codepen.io/svganimationworkshop/embed/eYzZdrY?height=265&theme-id=light&default-tab=,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/eYzZdrY'>Advanced staggers - code along</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### Resources

[GSAP docs - staggering](https://greensock.com/docs/v3/Staggers)

[Advanced staggers with GSAP - codepen demo ](https://codepen.io/GreenSock/pen/vYBRPbO)

## Staggers with CSS

```css
.rect {
  animation: down 1s ease-in-out alternate infinite;
}

.rect:nth-child(2) {
  animation-delay: 100ms;
}

.rect:nth-child(3) {
  animation-delay: 200ms;
}

.rect:nth-child(4) {
  animation-delay: 300ms;
}

.rect:nth-child(5) {
  animation-delay: 400ms;
}

@keyframes down {
  to {
    transform: scaleY(0.2);
  }
}

```

## Staggers with GSAP

```js

// simple stagger
gsap.to('.rect', {
  duration: 1,
  ease: 'sine.inOut',
  scaleY: 0.4,
  transformOrigin: 'center bottom',
  yoyo: true,
  repeat: -1,
  stagger: 0.2,
})

// with stagger object
gsap.to('.rect', {
  duration: 1,
  ease: 'sine.inOut',
  scaleY: 0.4,
  transformOrigin: 'center bottom',
  stagger: {
    each: 0.2,
    yoyo: true,
    repeat: -1,
  }
})

// grid staggers
gsap.from('circle', {
  duration: 1,
  scale: 0,
  ease: "sine.inOut",
  stagger: {
     yoyo: true,
     repeat: -1,
     amount: 1,
     grid: [width, height],
     from: 'center',
  }
})
```
