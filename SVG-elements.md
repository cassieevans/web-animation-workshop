## Resources

[MDN Element reference](https://developer.mozilla.org/en-US/docs/Web/SVG/Element)

[SVG Path syntax - CSS tricks](https://css-tricks.com/svg-path-syntax-illustrated-guide/)

[Anthony Dugois​ path editor](https://codepen.io/anthonydugois/full/mewdyZ)

[JXNBLK PATHS](https://jxnblk.github.io/paths/)

## Why? <!-- {docsify-ignore} -->

- Optimising
- Performance
- Time saving and tweaks
- More control over animation
- Casually typing out SVG code will make you look v smart.

## Basic shapes. <!-- {docsify-ignore} -->

```html
<svg viewBox="0 0 200 200">
  <circle fill="#dc6fa3" cx="100" cy="100" r="50" />
</svg>
```

<svg width="200px" viewBox="0 0 200 200">
  <circle fill="#dc6fa3" cx="100" cy="100" r="50"/>
</svg>

```html
<svg viewBox="0 0 200 200">
  <ellipse cx="100" cy="100" rx="70" ry="40" />
</svg>
```

<svg width="200px" viewBox="0 0 200 200">
  <ellipse fill="#dc6fa3" cx="100" cy="100" rx="70" ry="40" />
</svg>

```html
<svg viewBox="0 0 200 200">
  <line x1="10" y1="90" x2="190" y2="10">
  <line x1="10" y1="150" x2="190" y2="150">
</svg>
```

<svg width="200px" viewBox="0 0 200 200">
    <line stroke-width="5px" stroke="#dc6fa3" x1="20" y1="90" x2="180" y2="20"></line>
    <line stroke-width="5px" stroke="#dc6fa3" x1="20" y1="150" x2="180" y2="150"></line>
</svg>

```html
<svg viewBox="0 0 200 200">
  <polygon points="20,180 100,20 190,180">
</svg>
```

<svg width="200px" viewBox="0 0 200 200">
    <polygon fill="#dc6fa3" points="20,180 100,20 190,180"></polygon>
</svg>

```html
<svg viewBox="0 0 200 200">
  <polyline points="10,190 100,50 100,150 190,10" />
</svg>
```

<svg width="200px" viewBox="0 0 200 200">
    <polyline points="10,190 100,50 100,150 190,10" fill="none" stroke-width="4px" stroke="#dc6fa3"></polyline>
</svg>

```html
<svg viewBox="0 0 350 200">
  <rect x="50" y="50" width="100" height="100" />
  <rect x="50" y="50" width="100" height="100" rx="20" />
</svg>
```

<svg width="500px" viewBox="0 0 350 200">
    <rect x="50" y="50" width="100" height="100" fill="#dc6fa3"></rect>
    <rect x="200" y="50" width="100" height="100" rx="20" fill="#dc6fa3"></rect>
</svg>

## Structural elements. <!-- {docsify-ignore} -->

```html
<svg viewBox="0 0 350 200">
  <g fill="#dc6fa3">
    <rect id="myRect" x="50" y="50" width="100" height="100" />
    <rect id="myRect" x="200" y="50" width="100" height="100" rx="20" />
  </g>
</svg>
```

<svg width="500px" viewBox="0 0 350 200">
    <g fill="#dc6fa3">
    <rect id="myRect" x="50" y="50" width="100" height="100" />
    <rect id="myRect" x="200" y="50" width="100" height="100" rx="20" />
  </g>
</svg>

```html
<svg viewBox="0 0 400 200">
  <rect id="myRect" x="50" y="50" width="100" height="100" fill="#dc6fa3" />
  <use
    href="#myRect"
    x="200"
    stroke="#dc6fa3"
    fill="#6fdcbf"
    stroke-width="3"
  />
</svg>
```

<svg viewBox="0 0 400 200" width="500px">
    <rect id="myRect" x="50" y="50" width="100" height="100" fill="#dc6fa3"></rect>
    <use href="#myRect" x="200" stroke="#dc6fa3" fill="#6fdcbf" stroke-width="3"></use>
</svg>

## Graphics Elements. <!-- {docsify-ignore} -->

Paths - Letters are commands. Numbers are co-ordinates.

```html
<svg viewBox="0 0 100 100">
  <path d="M 10,30 A 20,20 0,0,1 50,30 A 20,20 0,0,1 90,30 Q 90,60 50,90 Q
  10,60 10,30 z">
</svg>
```

<svg width="200px" viewBox="0 0 100 100">
    <path fill="#dc6fa3" d="M 10,30
           A 20,20 0,0,1 50,30
           A 20,20 0,0,1 90,30
           Q 90,60 50,90
           Q 10,60 10,30 z"></path>
</svg>

## Exercise

Fork this pen and decorate your potato.

The best way to get comfortable with SVG markup is by getting stuck in.

_**Ideas**_

- Add and remove opacity="0" to show and hide different SVG elements.
- Play around with stroke width and fill colors.
- What happens when you change path coordinates?
- Can you spot any SVG shapes... or make your own?

[Open codepen](https://codepen.io/svganimationworkshop/pen/WNwBqGG)
