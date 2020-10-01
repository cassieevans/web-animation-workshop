This is a wonderful article that goes into a ton of detail.

[Accessible SVG's - CSS tricks](https://css-tricks.com/accessible-svgs/)

But here's a TLDR...

We can add title's and descriptions to our SVG's for screenreader accessibility

!> A title and description will be enough for most cases. But there are bugs in firefox so for now, to be safe use aria-labelledby.

```html
<svg viewBox="0 0 720 800" aria-labelledby="galaxyTitle galaxyDesc" role="img">
  <title id="galaxyTitle">Fred</title>
  <desc id="galaxyDesc">Fred is a sad potato</desc>
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
