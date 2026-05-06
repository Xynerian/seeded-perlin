# perlin.js

## A JavaScript Perlin Noise Generator

This short JS library allows you to easily incorporate <a href='https://en.wikipedia.org/wiki/Perlin_noise'>perlin noise</a> into your projects with deterministic seeds.

---

### Python

Note that the python here is outdated and does not include deterministic seeds.

---

### Installation

Simply include the source in your application's HTML, no downloading required:

```html
<script src='https://github.com/Xynerian/seeded-perlin.git'></script>
```

---

### Usage

There are 2 main functions that are provided: `perlin.clearMemory` and `perlin.get`.
And a property used to determine the noise generated `perlin.seed`.
### perlin.seed
Format: 
```javascript
perlin.seed
```
The seed is used to determine what noise pattern is generated.
### perlin.get
Format:
```javascript
perlin.get(x, y)
```
where `x` and `y` are floating point numbers.

The function will return a float in the range `-1.0` to `1.0` representing the 'noise-intensity' at that point. As for the scale, the coordinate system is setup as a grid with vertexes at integer coordinates. These vertexes are the peaks and troughs of the noise. All floating point coordinates between inside cells will give smoothly interpolated values between.

### perlin.clearMemory
All that `perlin.clearMemory()` does (to be called with no arguments), is reset the stored noise so that you can generate fresh noise. On each reload of the library, this will be reset anyway, and if you were to just offset all your `perlin.get` calls away from your previous calls, you would achieve the same effect of generating new noise. However, by doing this, you are of course sacrificing some memory as the previous noise remains saved (this is negligible, but is something to bare in mind).

---

### Examples

I created a basic example of the noise being generated which you can see its source in this GitHub repository. The demo creates the most basic display of noise, but I added a heatmap-style effect to it (using the hsl() colour format) which makes the result clearer.

Obviously that demo is the most basic use of the library. I don't yet have an online demo available but if you can pretty easily copy-paste it into an HTML file and then open that file in your web browser to see it.
