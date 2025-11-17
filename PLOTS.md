## [2D and 3D plotting with high-level plot commands](PLOTS.md)

Nelson provides graphics functions to visualize and export data:

You will find all graphical functions documentation: [HERE](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/index.html?open=./graphics/index.html)

Find more plots in [Plot Gallery](PLOT_GALLERY.md)

### 2D Plots

#### Draw Circle and Lissajous curve

```matlab
f = figure();
t = linspace(0, 2 * pi,63);
hold on
plot(cos(t), sin(t), '^r')
plot(cos(t), sin(2 * t), '-g', MarkerSize=2);
axis equal
legend(_('Circle'), _('Lissajous curve'))
```

<img src="https://github.com/nelson-lang/nelson-website/raw/master/images/plot-2D-1.svg">

#### Subplot

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

<img src="https://github.com/nelson-lang/nelson-website/raw/master/images/plot-2D-2.svg">

#### Animate a plot

```matlab
f = figure();
theta = 0:pi/20:2*pi;
x = cos(theta);
y = sin(theta);
h = plot(x,y);
axis([-1,7,-4,4]);
for i = 1:100
    x = x + 0.05;
    set(h,'xdata',x);
    pause(0.1);
end
```

### 3D Plots

#### meshgrid and surf

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

<img src="https://github.com/nelson-lang/nelson-website/raw/master/images/plot-3D-1.svg">

[Previous page](FEATURES.md)
