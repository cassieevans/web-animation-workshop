## In your graphics editor.

- The less path data you have, the better.
- Make sure there's enough room on your artboard for your elements to move without being cut off.
- Group elements you want to animate together.
- Make sure your layers are labelled.
- Delete any unnecessary elements outside of the artboard.

[This article](https://css-tricks.com/high-performance-svgs/) by Sarah Drasner is a great deep dive.

## Post export optimising.

[SVG OMG](https://jakearchibald.github.io/svgomg/)

### do

- Reduce precision to lessen the number of path points. This can save a lot of size but can also visually regress your SVG. Keep an eye on it to make sure you don't push it too far
- Move styles to attributes and sort attrs. It will keep your styles tidy and easy to override.
- Round/rewrite paths to reduce decimal points.
- Remove xmlns & xml instructions if your SVG is going to be inline.

### don't

- Clean ID's or you'll lose your layer names!
- Merge paths, you may end up merging shapes together that you intended to move independantly.
- Collapse useless groups, you may have grouped elements to animate them together.

### Get rid of duplicate gradients with Jake's tool -

[check it out on codepen](https://codepen.io/jakealbaugh/full/OVrQXY/)

### Convert mixed relative/absolute paths -

Lea's tool uses snapSVG functionality to convert path data to relative or absolute.
[check it out on codepen](https://codepen.io/leaverou/pen/RmwzKv?editors=1010)
