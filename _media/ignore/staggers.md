---
title: Staggers <!-- {docsify-ignore} -->
---

## Resources and snippets

[Advanced staggers with GSAP](https://codepen.io/GreenSock/pen/vYBRPbO)

### Staggers with CSS <!-- {docsify-ignore} -->

```css
.dot {
  animation: up 0.7s ease-in-out alternate infinite;
}

.dot:nth-child(2) {
  animation-delay: 100ms;
}

.dot:nth-child(3) {
  animation-delay: 200ms;
}

.dot:nth-child(4) {
  animation-delay: 300ms;
}

.dot:nth-child(5) {
  animation-delay: 400ms;
}
```

### Staggers with GSAP <!-- {docsify-ignore} -->

```js
// simple stagger
gsap.to('circle', {
  duration: 0.7,
  y: -50,
  stagger: 0.2
})

// more complex staggers
gsap.to('circle', {
  duration: 0.7,
  y: -50,
  stagger: {
    stagger: {
    grid: [7,15],
    from: "edges",
    amount: 1.5
  }
})
```
