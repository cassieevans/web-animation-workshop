---
title: Filters {docsify-ignore}
---

> Filter primitives live inside a filter element and create different graphic effects that can be applied to both SVG and HTML elements

They work a bit like filters in photoshop or other graphics programs.

Graphic effects can be applied to either a source graphic or source alpha and can also be passed into the input of another filter primitive. It's a bit like audio processing in that the output of one filter can be passed to the next.

This 'chaining' allows for infinite types of effects.

## Resources

[The Gooey effect](https://css-tricks.com/gooey-effect/)

[Squigglevision](https://css-tricks.com/squigglevision-in-css-and-svg/)

## Snippets

Filter applied in an SVG

```html
<svg>
  <defs>
    <filter id="gooey" height="130%">
      <feGaussianBlur in="SourceGraphic" stdDeviation="15" result="blur" />
      <feColorMatrix in="blur" mode="matrix" values="..." result="goo" />
    </filter>
  </defs>

  <g filter="url(#gooey)">
    stuff that's got a filter applied to it
  </g>
</svg>
```

Filter applied with CSS

```css
.element {
  filter: url(#gooey);
}
```
