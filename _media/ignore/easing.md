---
title: Debugging <!-- {docsify-ignore} -->
---

Easing is one of the most important things in motion design. It's the best way to breathe life and personality into an animation.

## Resources and snippets

### Easing with CSS <!-- {docsify-ignore} -->

With CSS, we're limited to two bezier handles for customisation of our easing curves.

[This site](https://cubic-bezier.com/#.17,.67,.83,.67) is a good place to play with easing.

You can also tweak easing right in chrome dev tools!

![easing in chrome dev tools](_media/ease.png)

### Easing with GSAP <!-- {docsify-ignore} -->

Greensock uses SVG path syntax for easing curves so we get a lot more flexibility.
We can create more complex effects like bouncing, elastic eases, wiggles, or jerky eases.

Here are some GSAP eases with their corresponding CSS syntax

| GSAP                 | CSS                                    |
| -------------------- | -------------------------------------- |
| ease: "none"         | animation-timing-function: linear      |
| ease: "power1.inOut" | animation-timing-function: ease-in-out |
| ease: "power1.in"    | animation-timing-function: ease-in     |
| ease: "power1.Out"   | animation-timing-function: ease-out    |

Check out the ease visualizer for more interesting easing equations:
[GSAP ease visualizer](https://greensock.com/docs/v3/Eases)

### Extra eases with easepack <!-- {docsify-ignore} -->

These eases aren't included in the core and need to be loaded in seperately with easepack. This is a free plugin.

"SlowMo", "RoughEase", "ExpoScaleEase"

```html
<script src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/EasePack3.min.js"></script>
```

```js
// register the plugin
gsap.registerPlugin(EasePack);
```

## Exercise

Time to add some easing to your timeline!

Try to think about the animation principles.

Can you show anticipation or mimic more realistic movement?
