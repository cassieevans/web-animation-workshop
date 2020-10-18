[GSAP timelines - docs ](https://greensock.com/docs/v3/GSAP/Timeline)

## Control methods

Timelines have methods for more finite control.

```js
timeline.pause()
timeline.resume()
timeline.seek(1.5)
timeline.reverse()
timeline.timeScale(0.5)

// Slow timeline down to half speed and play it in reverse.
timeline.timeScale(0.5).reverse()
```

## Special properties

Add these to your vars object to give your animation special powers:

```js
const tl = gsap.timeline({ repeat: 3, yoyo: true });
```

| property    |                        |
| ----------- | ---------------------- |
| delay       | number                 |
| paused      | boolean                |
| repeat      | number / -1 (infinite) |
| repeatDelay | number                 |
| yoyo        | boolean                |
| timeScale   | number                 |

## Defaults

You can also pass in 'defaults' in order for the child tweens to inherit the settings from the timeline.

```js
const tl = gsap.timeline({defaults: { duration: 1, ease: 'elastic' }});

// these tweens will all have a duration of 1 and an elastic ease
tl.to('.tween1', { rotation: -270 })
  .to('.tween2', { rotation: -360 })
  .to('.tween3', { rotation: -180 });
```

## Callbacks

You can fire callbacks, and pass in parameters to those callbacks.

```js
const tl = gsap.timeline({
  onComplete: logMessage,
  onCompleteParams: ['banana'],
});

function logMessage(message) {
  console.log(message);
}
```

or fire off functions from your animation code

```js
const tl = gsap.timeline();

tl.to('.tween1', { rotation: -270 })
  .to('.tween2', { rotation: -360 })
  .call(logMessage, ['banana'], '<0.5')
  .to('.tween3', { rotation: -180 });

function logMessage(message) {
  console.log(message);
}
```

Here's an audio library and some sounds if you want a play!

```
https://cdnjs.cloudflare.com/ajax/libs/howler/2.2.0/howler.min.js

```
```js
var sound = new Howl({
  src: ['https://assets.codepen.io/756881/TFTank-Drive.wav']
});

sound.play()

// https://assets.codepen.io/756881/Potato.wav
// https://assets.codepen.io/756881/SciFiAmbience_S08SF.89_01.wav
// https://assets.codepen.io/756881/RubberBandSnap_S08FO.2219.wav
// https://assets.codepen.io/756881/SciFiRobotWalk_S08SF.435.wav
// https://assets.codepen.io/756881/SciFiLaser_S08SF.346_01.wav
// https://assets.codepen.io/756881/EspressoBubbles_S08HS.482.wav
```

## Nesting timelines

Nest timelines within timelines as deeply as you want. This lets you modularize your code and make it more maintainable

```js
function intro() {
  const tl = gsap.timeline();
  //...add animations here...
  return tl;
}

function end() {
  const tl = gsap.timeline();
  //...add animations here...
  return tl;
}

// stitch them together in a master timeline...
const master = gsap.timeline();
master.add(intro())
master.add(middle(), '+=2')
```
