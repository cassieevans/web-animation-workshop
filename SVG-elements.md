# SVG Elements

> Number garbage.
> -- <cite>S. Drasner</cite>

## Resources

[MDN Element reference](https://developer.mozilla.org/en-US/docs/Web/SVG/Element)

[SVG Path syntax - CSS tricks](https://css-tricks.com/svg-path-syntax-illustrated-guide/)

[Anthony Dugois​ path editor](https://cdpn.io/anthonydugois/debug/mewdyZ/GnAnbOWQYgPA)

[JXNBLK PATHS](https://jxnblk.github.io/paths/)

## Why should I care?

- Optimising
- Performance
- Time saving and tweaks
- More control over animation
- Casually typing out SVG code will make you look v smart.

## Basic shapes.

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

## Structural elements.

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

## Graphics Elements.

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

## Path Manipulation.

Manipulating a path using only one control point.

<iframe height="400px" style="width: 100%;" scrolling="no" title="Morphing an SVG path" src="https://codepen.io/cassie-codes/embed/LYEpZzx?height=265&theme-id=default&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/cassie-codes/pen/LYEpZzx'>Morphing an SVG path</a> by Cassie Evans
  (<a href='https://codepen.io/cassie-codes'>@cassie-codes</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise time!

Fork this codepen and make some shapes and paths.

Go ahead and style them with CSS or inline styles.

We'll be animating them next so if you're feeling adventurous, try and make a scene or a face.

(bonus points for making use of `<use>` or linear gradients.)

[Open codepen](https://codepen.io/cassie-codes/pen/9726d1bd9e783e61fb31c6d91ef5788b?editors=1010)
