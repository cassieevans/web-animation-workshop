Interaction is **by far** the coolest bit about animating on the web.

Being able to factor in external interaction encourages an extra level of playfulness and unlocks a whole world of creativity and possibilities that you don't get with traditional methods of animation.

Interactivity is largely about listening for some sort of interaction and then using control methods to alter a the state of that animation.

## Event Listeners

```js
// useful methods
tl.timeScale()
tl.reverse()
tl.pause()
tl.resume()
tl.reverse
tl.play()
tl.seek()

let container = document.querySelector('#container');

// listen for mouse events on the container and adjust timeline
container.addEventListener('mouseenter', () => tl.timeScale(2).reverse());
container.addEventListener('mouseleave', () => tl.play());
```

## Reversing a timeline

```js

//flips the orientation (if it's forward, it will go backward, if it is backward, it will go forward):
if (tl.reversed()) {
  tl.play();
} else {
  tl.reverse();
}

//flips the orientation using the reversed() method instead (shorter version of the code above):
tl.reversed( !tl.reversed() );

```

## Code along with me!

<iframe height="400" style="width: 100%;" scrolling="no" title="Spaceship - Interaction" src="https://codepen.io/svganimationworkshop/embed/eYzzzmE?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/eYzzzmE'>Spaceship - Interaction</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

But we're not limited to just playing or pausing timelines on events, we have all sorts of stuff to play with in the browser! Scroll, webcam interaction, mouse movement. The sky's the limit!

### Here's some inspiration!

[animated house with sliders](https://codepen.io/knekk/pen/BOjRbE)

[dancing robot](https://codepen.io/joshbader/pen/ZqNqqm)

[webcam colour chameleon](https://codepen.io/cassie-codes/pen/ZjErdL)

## Animating on mouse movement

[animated avatar](https://codepen.io/svganimationworkshop/pen/qBqxPGd)

[Here's an article I wrote](https://www.cassie.codes/posts/making-a-lil-me-part-1/)

### quickSetter() & gsap.ticker

[View quickSetter() GSAP docs](<https://greensock.com/docs/v3/GSAP/gsap.quickSetter()>)

[View gsap.ticker GSAP docs](https://greensock.com/docs/v3/GSAP/gsap.ticker)

quickSetter is a restricted form of .set() that’s more performant, it's especially useful for things that run every tick - like mouse reactive animation.

```js
//reduced example code

var xSet = gsap.quickSetter('#ufo', 'x', 'px');
var ySet = gsap.quickSetter('#ufo', 'y', 'px');

window.addEventListener('mousemove', (e) => {
  mouse.x = e.x;
  mouse.y = e.y;
});

// gsap.ticker is gsap's requestAnimationFrame
gsap.ticker.add(() => {
  xSet(mouse.x);
  ySet(mouse.y);
});
```

### working demo

<iframe height="500" style="width: 100%;" scrolling="no" title="Spaceship - quickSetter" src="https://codepen.io/svganimationworkshop/embed/oNLLLzJ?height=265&theme-id=light&default-tab=result" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/svganimationworkshop/pen/oNLLLzJ'>Spaceship - quickSetter</a> by SVG-workshops
  (<a href='https://codepen.io/svganimationworkshop'>@svganimationworkshop</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>
