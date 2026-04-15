# Carnation-pencil
Many times you must sacrifice in order to move forward

![buh](https://github.com/nicolasbaez/Carnation-pencil/blob/main/xp066.gif)
```javascript
setup = (_) => createCanvas((w = 500), w);
k = 0;
draw = (_) => {
  h = 255;
  d = 0.01;
  background(0);
  for (i = 0; i < w; i += 20)
    for (j = 0; j < w; j += 20) {
      strokeWeight(4);
      stroke(h, 0, 0, noise(i * d, j * d, k) * h);
      point(i, j);
      stroke(0, h, 0, noise(k, i * d, j * d) * h);
      point(i + 4, j);
      stroke(0, 0, h, noise(j * d, k, i * d) * h);
      point(i + 8, j);
    }
  if (k == 0) saveGif("xp066.gif", 2000, { delay: 0, units: "frames" });
  k += d;
};
