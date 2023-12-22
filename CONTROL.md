## Control System module

The Control System Module offers algorithms and applications designed to systematically analyze, design, and adjust linear control systems.

You have the flexibility to define your system using a transfer function or state-space model. Through various tools and functions, such as step response plots and Bode plots, you can examine and represent system dynamics across time and frequency domains.

Interactive tuning techniques, including Bode loop shaping and the root locus method, enable you to adjust compensator parameters.
This module seamlessly accommodates both Single Input Single Output (SISO) and Multiple Input Multiple Output (MIMO) compensators, automatically fine-tuning them as needed.

```matlab
H = tf([1 0.1 7.5],[1 0.12 9 0 0]);
bode(H,{1 10}, '-.')
```

![bode plot](https://github.com/nelson-lang/nelson-website/raw/master/images/bode.png "bode")

### [List of control system functions](https://nelson-lang.github.io/nelson-website/help/en_US/chapter_control_system.html)

[Previous page](FEATURES.md)
