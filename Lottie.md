### We're not going into Lottie as it's a _whole_ thing in itself. But here's a little overview.

When to use Lottie?

- You (or your team) has After Effects experience rather than coding skills.
- You're not just animating on the web - you have android or IOS apps too. (this is the main reason)
- You're doing complex character animation that needs rigging.

pros

- Lots of gorgeous, free, ready made animations on the Lottie site ready to use.
- Enables motion designers to animate vectors for the web.
- You can export to canvas for more performant animations.

cons

- Performance is bad for web. It's basically a sprite player, rendering path data changes as 'frames' in quick succession. Because of this it's heavy on memory and there's no hardware acceleration. In a lot of cases you might be better off using a video.
- It uses a bunch of pre-generated data, so you can't change it at runtime, meaning it can't be dynamic.
- The Lottie player itself is quite heavy to load on web.
- Only a subset of After Effects features [are supported](https://airbnb.io/lottie/#/supported-features).
- Because it works with frames the animations don't have the same 'fluidity' as CSS or GSAP transitions. Slowly scroll [this demo](https://lottiefiles.com/interactivity?url=https%3A%2F%2Fassets8.lottiefiles.com%2Fpackages%2Flf20_tr1pjkop.json) to see what I mean - you can cleary see the frames playing one by one.
- Canvas exports are even more limited in terms of useable After effects features.
