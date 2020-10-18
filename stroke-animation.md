
SVG line animation is a really visually pleasing technique, and, luckily, it's also quite an accessible technique to grasp!
### Resources

[SVG stroke animation with CSS](https://css-tricks.com/svg-line-animation-works/)

[Draw SVG](https://greensock.com/docs/v3/Plugins/DrawSVGPlugin)

### Using CSS <!-- {docsify-ignore} -->

> Instead of calculating the length of the path with path.getTotalLength() you can set the pathLength attribute to 1. This doesn't change what the path looks like. But the underlying maths of the path itself is now based on a value of 1.

```html
<svg viewBox="0 0 100 100">
  <path class="squiggle" pathLength="1" d="M14.2...." />
</svg>
```

```css
.squiggle {
  stroke-dasharray: 1;
  stroke-dashoffset: 1;
  animation: draw 2s linear forwards;
}

@keyframes draw {
  to {
    stroke-dashoffset: 0;
  }
}
```

### Using GSAP's draw SVG plugin <!-- {docsify-ignore} -->

!> This a bonus plugin for Club GreenSock members. (But it's free on codepen)

```HTML
<script src='https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/DrawSVGPlugin3.min.js'></script>
```

```js
// register plugin
gsap.registerPlugin(DrawSVGPlugin);

// simple path tween
gsap.from('.squiggle', {
  duration: 2,
  drawSVG: '0%',
});

// more control over start and end positions
gsap.fromTo(
  '.squiggle',
  {
    duration: 2,
    drawSVG: '10%',
  },
  {
    drawSVG: '80%',
  }
);

// move a small part of the line along the path
gsap.fromTo(
  '.squiggle',
  {
    duration: 1.5,
    drawSVG: '0 5%',
  },
  {
    drawSVG: '95% 100%',
  }
);

// draw line in and then out again
 gsap.set(".squiggle", {
   drawSVG:"0%",
 }

 gsap.to(".squiggle", {
   duration: 7, 
   keyframes: [
     {
       drawSVG: "0% 0%"
     },
     {
       drawSVG: "0% 100%"
     },
     {
       drawSVG: "100% 100%"
     }
   ]
 })
```

## Exercise

Give stroke animation & staggering a go.

Feel free to use CSS or GSAP.

[starter pen](https://codepen.io/svganimationworkshop/pen/yLJJYNM)
