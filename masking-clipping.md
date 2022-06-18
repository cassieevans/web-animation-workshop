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

[Calligraphy text masking tutorial](https://www.motiontricks.com/svg-calligraphy-handwriting-animation/)

```html
<svg>
  <defs>
    <!-- gradient -->
    <linearGradient id="gradient" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="50%" stop-color="black" />
      <stop offset="100%" stop-color="white" />
    </linearGradient>

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

applied with CSS

```css
.element {
  clip-path: url('#myClip');
  /* or */
  mask: url('#myMask');
}
```

[Masking vs. Clipping: When to Use Each](https://css-tricks.com/masking-vs-clipping-use/)

### Demo pen <!-- {docsify-ignore} -->

<iframe height="400" style="width: 100%;" scrolling="no" title="Masking and Clipping" src="https://codepen.io/svganimationworkshop/embed/qBZeMmG?height=265&theme-id=default&default-tab=html,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/qBZeMmG'>Masking and Clipping</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise

[Generate some SVG paths from a google font](https://danmarshall.github.io/google-font-to-svg-path/) of your choice.

Choose a [GIF](https://giphy.com/) and play around with clipping!

[codepen link](https://codepen.io/svganimationworkshop/pen/dyMBdMR)

** alternative / bonus exercise **

Play with some SVG-masking collage in this pen

[codepen link](https://codepen.io/svganimationworkshop/pen/QWEwxbv)
