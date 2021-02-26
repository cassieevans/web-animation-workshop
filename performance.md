## Game break

[Jank Invaders](https://jakearchibald.github.io/jank-invaders/)

## Composite properties

Animating composite properties allows the browser to avoid repaints and layout calculations. Instead it can just move existing, painted pixels around the screen.

There are four key styles that a browser can animate cheaply:

- Translation, i.e., transform: translate
- Scale, i.e., transform: scales
- Rotation, i.e., transform: rotate
- Opacity

```css
.noice {
  transform: translateX(-30px);
  transform: scale(2);
  transform: rotate(20deg);
  opacity: 0;
}
```

## Canvas vs SVG <!-- {docsify-ignore} -->

|        | PROS                                                                                                                                                                          | CONS                                                                                       |
| ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| SVG    | Easy to get started<br><br>Easier to register user interactions<br><br>Easier to debug (It has a DOM)<br><br>Can be made accessible<br><br>Can use both CSS and JS to animate | Potentially extensive and complex DOM<br><br>Not performant for a large number of elements |
| CANVAS | Very Performant<br><br>Animate tons of objects<br><br>Great for games or immersive stuff                                                                                      | Much steeper learning curve<br><br>Breaks to nothing without JS<br><br>Inaccessible        |

## Should we just use canvas then? <!-- {docsify-ignore} -->

In short, it depends. There's a payoff with SVG for the ease of use, accessibility and interactivity. When using SVG animate mindfully, and to be aware of the limitations.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">One extremely basic way to answer it is &quot;use canvas when you cannot use svg&quot; (where &quot;cannot&quot; might mean animating thousands of objects, manipulating each pixel individually, etc.). To put it another way, SVG should be your default choice, canvas your backup plan.</p>&mdash; Benjamin De Cock (@bdc) <a href="https://twitter.com/bdc/status/1179509488803434496?ref_src=twsrc%5Etfw">October 2, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Performance tips

- Don't animate lots of elements or SVG's at once.
- Avoid looping animations & pause/kill animations when they are out of frame.
- Solid colors are better than semi-transparent ones.
- Use scaling transformations rather than changing the underlying geometry.
- Clipping is usually more efficient than masking.
- Avoid any changes that require a filter to be recalculated.

## Killing animations offscreen

Example using the [Intersection observer API.](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)

```js
function killOrPlay(entry) {
  if (entry.isIntersecting) {
    tl.resume();
  } else {
    tl.pause();
  }
}

let callback = function (entries, observer) {
  entries.forEach((entry) => {
    killOrPlay(entry);
  });
};

let observer = new IntersectionObserver(callback);
let target = document.querySelector('svg');

observer.observe(target);
```

<iframe height="500" style="width: 100%;" scrolling="no" title="Spaceship - Intersection Observer - simple" src="https://codepen.io/svganimationworkshop/embed/MWeeeNB?height=265&theme-id=light&default-tab=js,result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/MWeeeNB'>Spaceship - Intersection Observer - simple</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
