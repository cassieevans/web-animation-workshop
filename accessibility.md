We can add title's and descriptions to our SVG's for screenreader accessibility

!> A title and description will be enough for most cases. But there are bugs in firefox so for now, to be safe use aria-labelledby.

```html
<svg viewBox="0 0 720 800" aria-labelledby="galaxyTitle galaxyDesc" role="img">
  <title id="galaxyTitle">Spud</title>
  <desc id="galaxyDesc">Spud is a sad potato</desc>
</svg>
```

For simple animations and images set role="img" so that the SVG innards aren't traversed by browsers.

For infographics you can make the SVG DOM traversable by using role="group".

Any text elements inside your SVG will be read out by default, you can also use aria labels inside the SVG to indicate what the user is looking at.

This is a wonderful article that goes into a ton of detail.

[Accessible SVG's - CSS tricks](https://css-tricks.com/accessible-svgs/)

```
<svg viewBox="0 0 720 800" aria-labelledby="graphTitle graphDesc" role="group">
  <title id="graphTitle">Infographic</title>
  <desc id="graphDesc">An important infographic.</desc>
  <g id="chart" role="list" aria-label="bar graph">
    <g role="listitem">
      <rect x="50" y="50" width="100" height="400" />
    </g>
  </g>

  <text>Read me</text>
  <text role="presentation" aria-hidden=”true”>Do not read me</text>
</svg>
```
