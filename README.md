# Website Optimization

My challenge with this project wass to optimize this online portfolio for speed! In particular, to optimize the critical rendering path and make this page render as quickly as possible by applying the techniques I picked up in Udacity's Critical Rendering Path course.

## Get started

* Clone or download this repo
* Open index.html in a web browser

[Demo](https://popshift.net/optimize)


## My Optimizations

1. Removed Google Analytics (not so much for performance as much as it's just unused)
2. Implemented [WebFontLoader](https://github.com/typekit/webfontloader) for asyncronous loading of Google Web Fonts
3. Added media=print to non-critical print CSS file
4. Pizzaria - Removed the determineDx function and refactored the changePizzaSizes function to adjust pizza images via percentage widths
5. Pizzaria - Moved scrollTop definition outside of loop in updatePositions.
6. Pizzaria - Moved actual positioning of background pizzas to it's own function (setPositions) that doesn't calculate scrollTop so that a forced reflow doesn't happen on page load. Function setPositions is called from updatePositions on scrolling.
7. Pizzaria - Changed number of background pizzas to 32.
8. Pizzaria - Resized main image and pizza image to be the max displayed size

#### Initial Performance (Pizzaria)
* Average time to resize pizzas: ~100ms
* Average scripting time to generate 10 frames: ~20ms
* Average scrolling framerate: ~30 fps

#### Final Performance (Pizzaria)
* Average time to resize pizzas: ~1.5ms
* Average scripting time to generate 10 frames: ~0.7ms
* Average scrolling framerate: ~60 fps

#### Initial PageSpeed scores (mobile/desktop):
* Index: 89/92
* Pizza: 62/96
* Project 2048: 99/100
* Project Mobile: 98/100
* Project WebPerf: 99/100

#### Final PageSpeed scores (mobile/desktop):
* Index: 100/100
* Pizza: 100/100
* Project 2048: 100/100
* Project Mobile: 100/100
* Project WebPerf: 100/100