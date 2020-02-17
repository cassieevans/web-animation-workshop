---
title: Optimising {docsify-ignore}
---

## In your graphics editor.  {docsify-ignore}

* Make sure there's enough room on your artboard for your elements to move without being cut off.
* Group elements you want to animate together.
* Make sure your layers are labelled.
* Delete any unnecessary elements outside of the artboard.
* simplify shapes.
* use solid colours instead of gradients or effects.


[This article](https://css-tricks.com/high-performance-svgs/) by Sarah Drasner is a great deep dive.

## Post export optimising.  {docsify-ignore}

[SVG OMG](https://jakearchibald.github.io/svgomg/)

* Reduce precision to lessen the number of path points. This can save a lot of size but can also visually regress your SVG. Keep an eye on it to make sure you don't push it too far
* Style to attributes and sort attrs will keep your styles tidy and easy to override.
* Don't clean ID's or you'll lose your labels!
* Watch out for merge paths, you may end up merging shapes together that you intended to move independantly

## Exercise

Run your SVG through SVGOMG, and copy the code into the starter pen.

[Blank starting pen](https://codepen.io/cassie-codes/pen/5a643c4a82f782d48e5d2843ee97ac76)

Alternately you can use this ready made spaceship pen.

[Starting Pen - with spaceship SVG](https://codepen.io/cassie-codes/pen/a2777ea988619c1be195d0e5a74853d1?editors=1010)