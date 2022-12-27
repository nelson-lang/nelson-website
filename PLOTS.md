## [2D and 3D plotting with high-level plot commands](PLOTS.md)

Nelson provides graphics functions to visualize and export data:

You will find all graphical functions documentation: [HERE](https://nelson-numerical-software.github.io/nelson-website/help/en_US/chapter_graphics.html)

### 2D Plots

Examples:

```matlab
f = figure();
t = linspace(0, 2 * pi,63);
hold on
plot(cos(t), sin(t), '^r')
plot(cos(t), sin(2 * t), '-g', 'MarkerSize', 2);
axis equal
legend(_('Circle'), _('Lissajous curve'))
```
<img src="https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/plot-2D-1.svg">

subplot:
```matlab
f = figure();
t = linspace(0, 2 * pi, 128);
subplot(3, 3, 1);
plot(cos(t), sin(t));
subplot(3, 3, [2 3]);
plot(t, cos(t));
subplot(3, 3, [4 7]);
plot(sin(t), t);
subplot(3, 3, [5 9]);
t = linspace(0, 2 * pi,64);
plot(t, sin(t));
hold on
plot(t, cos(t));
hold off
```
<img src="https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/plot-2D-2.svg">

Demo:

<img src="https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/butterfly.png">

### 3D Plots


Example:

```matlab
f = figure();
[u, v] = meshgrid(linspace(0, pi, 50), linspace(pi / 4, pi,25));
x=sin(v) .* cos(u);
y=sin(v) .* sin(u);
z=cos(v);
surf(x,y,z,x);
hold on
surf(x, -y, z, rand(size(z)));
hold off
axis equal;
colormap(autumn)
```
<img src="https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/plot-3D-1.svg">

3D Animation

[![3D Animation](https://i.ytimg.com/an_webp/ziM-DlD3LOg/mqdefault_6s.webp?du=3000&sqp=CKDorJ0G&rs=AOn4CLD1sr1RTfwb1JN5_t4tQYXXRV5X3A)](https://www.youtube.com/watch?v=ziM-DlD3LOg)


Your imagination is the only limit ;)

[Previous page](FEATURES.md)
