---
title: Masking and Clipping {docsify-ignore}
---

> Clipping and Masking can both be used to crop or obscure elements in an SVG.

## Clipping

- Clipping uses underlying geometry.
- Transparency isn't possible.
- Think of it like cutting out.

## Masking

- Masking uses alpha values.
- Everything under a white pixel is visible, and everything under a black pixel is hidden.
- It allows soft edges by taking transparency and grey values of the mask into account.
- Think of it more like collage

## Resources and snippets

```html
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
  <defs>
    <!-- mask -->
    <mask id="myMask">
      <circle class="mask" cx="50" cy="50" r="30" fill="url(#gradient)" />
    </mask>

    <!-- clip -->
    <clipPath id="myClip">
      <circle class="clip" cx="50" cy="50" r="30" />
    </clipPath>
  </defs>

  <g clip-path="url(#myClip)">
    <!-- stuff to be clipped -->
  </g>

  <g mask="url(myMask)">
    <!-- stuff to be masked -->
  </g>
</svg>
```

[Masking vs. Clipping: When to Use Each](https://css-tricks.com/masking-vs-clipping-use/)

### Demo pen {docsify-ignore}

<iframe height="400" style="width: 100%;" scrolling="no" title="Masking &amp; Clipping" src="https://codepen.io/svganimationworkshop/embed/jOPwaBW?height=265&theme-id=default&default-tab=html,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/jOPwaBW'>Masking &amp; Clipping</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise

Go on [Giphy](https://giphy.com/), find a black and white gif and a textured gif and give masking a go!

[codepen link ](https://codepen.io/cassie-codes/pen/YzzbVOb)
