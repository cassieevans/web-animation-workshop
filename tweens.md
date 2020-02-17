---
title: Tweens {docsify-ignore}
---

## Resources

[Tweens - GSAP docs](https://greensock.com/docs/v3/GSAP/Tween)

## What's a tween?   {docsify-ignore}

> A Tween does all the animation work - think of it like a high-performance property setter.

Animation on the web basically boils down to changing property values a lot of times per second. A greensock tween takes a starting value, an ending value and then interpolates between them 60 times per second.


The GSAP object has three methods for creating a tween.


A tween is made up of -

* __The method__ -
 ```gsap.from()```
 ```gsap.to()```
 or ```gsap.fromTo()```

* __The Target(s)__ - the object(s) whose properties you want to animate. This can be selector text like ".class", "#id", etc. Or it can be direct references to elements,  generic objects, or even an array of objects
* __And lastly the variables__ - an object containing all the properties/values you want to animate, along with any special properties like ease, duration, delay, or onComplete

![tween infographic](_media/tween.png)


## Exercise

Time to animate your SVG!

Take a look at your animation plan and create the first tween.

You'll need your SVG starter pen from the last exercise.

## Snippets

``` js
// Good for exits
gsap.to('#ufo', { duration: 1, x: -700})

// Good for entrances
gsap.from('#ufo', { duration: 1, x: -700})

// Good for more control
gsap.fromTo('#ufo',{ x: -700},{ x: 700, duration: 2})
```