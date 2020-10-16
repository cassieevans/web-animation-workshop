## Resources

[ScrubGSAPTimeline - Chris Gannon](https://github.com/chrisgannon/ScrubGSAPTimeline)

## Quick and dirty way <!-- {docsify-ignore} -->

Use the timeline methods to seek out a part of your timeline, slow down the playback and then play

```js
// pause your timeline to start
const tl = gsap.timeline({ paused: true });

// seek a certain point of your timeline, slow it down and play
tl.seek(1.2).timeScale(0.2).play();
```

## The fun way! Chris Gannon's timeline scrubber. <!-- {docsify-ignore} -->

Just move the mouse over the window to advance and reverse the timeline.
Double click to pause scrubbing. Handy for right-click inspecting elements

```html
<script src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/35984/ScrubGSAPTimeline.js" />
```

```js
const tl = gsap.timeline();

ScrubGSAPTimeline(tl);
```

## Exercise

Have a go at debugging your animation!
