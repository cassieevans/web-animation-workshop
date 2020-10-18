Interaction is **by far** the coolest bit about animating on the web.

Being able to factor in external interaction encourages an extra level of playfulness and unlocks a whole world of creativity and possibilities that you don't get with traditional methods of animation.

Interactivity is all about listening for some sort of interaction  and then using control methods to alter a timeline.


```js
// tl.timeScale()
// tl.reverse()
// tl.pause()
// tl.resume()
// tl.reverse
// tl.play()
// tl.seek()

let container = document.querySelector('#container');

// listen for mouse events on the container and adjust timeline
container.addEventListener("mouseenter", () => tl.timeScale(2).reverse());
container.addEventListener("mouseleave", () => tl.play());
```
