---
title: Debugging {docsify-ignore}
---

Easing is one of the most important things in motion design. It's the best way to breathe life and personality into an animation.

## Resources and snippets

### Easing with CSS {docsify-ignore}

With CSS, we're limited to two bezier handles for customisation of our easing curves.

[This site](https://cubic-bezier.com/#.17,.67,.83,.67) is a good place to play with easing.

You can also tweak easing right in chrome dev tools!

![easing in chrome dev tools](_media/ease.png)


### Easing with GSAP {docsify-ignore}

Greensock uses SVG path syntax for easing curves so we get a lot more flexibility.
We can create more complex effects like bouncing, elastic eases, wiggles, or jerky eases.


[GSAP ease visualizer](https://greensock.com/ease-visualizer/)

### extra eases with easepack  {docsify-ignore}

"SlowMo", "RoughEase", "ExpoScaleEase"

```html
<script src='https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/EasePack3.min.js'></script>
```
``` js
// register the plugin
gsap.registerPlugin(EasePack);

```


## Exercise

Time to add some easing to your timeline!

Try to think about the animation principles.

Can you show anticipation or mimic more realistic movement?