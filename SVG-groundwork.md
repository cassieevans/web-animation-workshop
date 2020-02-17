---
title: SVG Groundwork  {docsify-ignore-all}
---

## What is SVG?

> SVG is like an alternate universe version of HTML. Focused on graphics instead of documents.
> -- <cite>Richard Westenra</cite>

- Scalable Vector Graphic.
- Image format and a markup language. (it has a DOM!)
- It can be manipulated with CSS & JS.
- SVG can be made accessible.
- Small file size. (if they're made & optimised well)

## Some ways to include an SVG.

### Just like you would a normal image.

😊 Responsive and sharp on retina displays

😢 No access to the DOM, they'll behave like normal images.

```HTML
<img src="myAwesomeSVG.svg" alt="my awesome SVG">
```

```css
.element {
  background-image: url(myAwesomeSVG.svg);
}
```

### Data URI's.

😊 Like Background image but without the additional HTTP request

```css
.element {
  background-image: url("data:image/svg+xml,...");
}
```

### Inline.

😊 All the benefits, animation, interactivity, accessibility!

😢 No caching though.

```HTML
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 323.231 295.836">
  <g id="sky"></g>
  <g id="planet"></g>
  <g opacity="0" id="star"></g>
</svg>
```

## MAGIC!

This is an animated background image. 🤯

<div class="magic"></div>