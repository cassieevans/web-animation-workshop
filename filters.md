> Filter primitives live inside a filter element and create different graphic effects that can be applied to both SVG and HTML elements

They work a bit like filters in photoshop or other graphics programs.

Graphic effects can be applied to either a source graphic or source alpha and can also be passed into the input of another filter primitive. It's a bit like audio processing in that the output of one filter can be passed to the next.

This 'chaining' allows for infinite types of effects.

## Resources

[MDN web docs](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)

[SVG filters 101](https://tympanus.net/codrops/2019/01/15/svg-filters-101/)

[SVG filters GUI](https://svgfilters.com/)

[The Gooey effect](https://css-tricks.com/gooey-effect/)

[Squigglevision](https://tympanus.net/codrops/2016/03/21/animated-animals-css-svg/)

## Snippets

Filter applied in an SVG

```html
<svg>
  <defs>
    <filter id="gooey" height="150%" width="150%" x="-25%" y="-25%">
      <feGaussianBlur in="SourceGraphic" stdDeviation="15" result="blur" />
      <feColorMatrix in="blur" mode="matrix" values="..." result="goo" />
    </filter>
  </defs>

  <g filter="url(#gooey)">
    <!-- stuff with a filter applied to it -->
  </g>
</svg>
```

Filter applied with CSS

```css
.element {
  filter: url(#gooey);
}
```

Squigglevision filter

```html
<svg>
  <filter id="sketchy">
    <feTurbulence
      id="turbulence"
      baseFrequency="0.05"
      numOctaves="3"
      result="noise"
      seed="0"
    />
    <feDisplacementMap
      id="displacement"
      in="SourceGraphic"
      in2="noise"
      scale="1"
    />
  </filter>

  <g filter="url(#sketchy)">
    <!-- stuff with a filter applied to it -->
  </g>
</svg>
```

## Demo pens

<iframe height="500" style="width: 100%;" scrolling="no" title="Displacement" src="https://codepen.io/svganimationworkshop/embed/jOqgewd?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/jOqgewd'>Displacement</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<iframe height="500" style="width: 100%;" scrolling="no" title="Flowers" src="https://codepen.io/cassie-codes/embed/eYmXozM?height=265&theme-id=light&default-tab=css,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/cassie-codes/pen/eYmXozM'>Flowers</a> by Cassie Evans
  (<a href='https://codepen.io/cassie-codes'>@cassie-codes</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

## Exercise

Play around with the morphology filter to distort an image in this pen!

If you feel adventurous, swop out this filter for other from the docs, have a play!

[codepen link](https://codepen.io/svganimationworkshop/pen/abZzGga)
