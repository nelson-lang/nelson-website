---
title: "Overloading"
description: "Nelson supports object-oriented programming with classdef. By defining methods on a class, you decide how your own types respond to operators such as +."
---

# Overloading

Nelson supports object-oriented programming with `classdef`. By defining methods on a class, you decide how your own types respond to operators such as `+` and `*`, and to functions such as `disp` or `norm`. The name of the method selects what it overloads: a method called `plus` is invoked for `+`, a method called `norm` is invoked by `norm(obj)`, and so on.

An example is clearer than a long description.

### A value class with overloaded operators

The `Vector3` class holds a three-component vector. It overloads addition, scalar multiplication, `dot`, `norm`, and the way an instance is shown at the prompt. Save it as `Vector3.m` in a folder on the Nelson path.

```matlab
classdef Vector3
  % Vector3  A small 3-D vector value class with overloaded operators.
  properties
    x = 0
    y = 0
    z = 0
  end
  methods
    function obj = Vector3(x, y, z)
      if nargin > 0
        obj.x = x;
        obj.y = y;
        obj.z = z;
      end
    end

    function r = plus(a, b)
      % Overloads the + operator.
      r = Vector3(a.x + b.x, a.y + b.y, a.z + b.z);
    end

    function r = mtimes(a, b)
      % Overloads the * operator for scalar * vector and vector * scalar.
      if isa(a, 'Vector3')
        v = a; s = b;
      else
        v = b; s = a;
      end
      r = Vector3(v.x * s, v.y * s, v.z * s);
    end

    function d = dot(a, b)
      % Overloads dot() for two Vector3 objects.
      d = a.x * b.x + a.y * b.y + a.z * b.z;
    end

    function n = norm(obj)
      % Overloads norm() for a Vector3 object.
      n = sqrt(obj.x^2 + obj.y^2 + obj.z^2);
    end

    function disp(obj)
      % Overloads disp(obj) and the prompt display (see display below).
      fprintf('Vector3(%g, %g, %g)\n', obj.x, obj.y, obj.z);
    end

    function display(obj, varargin)
      % Overloads the prompt display (a statement with no semicolon).
      disp(obj);
    end
  end
end
```

### Using the class

```matlab
u = Vector3(1, 2, 3)
v = Vector3(4, 5, 6)
w = u + v
s = 2 * u
d = dot(u, v)
n = norm(v)
class(w)
```

The session prints:

```text
Vector3(1, 2, 3)
Vector3(4, 5, 6)
Vector3(5, 7, 9)
Vector3(2, 4, 6)

d =

    32

n =

    8.7750

ans =

    'Vector3'
```

Each result comes from a method:

- `u + v` calls `plus` and returns `Vector3(5, 7, 9)`.
- `2 * u` calls `mtimes`, which accepts the scalar on either side.
- `dot(u, v)` and `norm(v)` call the methods of the same name, so ordinary function syntax works on the object.
- The `Vector3(...)` lines are produced by `disp`. The `display` method routes the no-semicolon prompt output through it.

The same pattern extends to the other operators and functions: define `minus` for `-`, `eq` for `==`, `mtimes` or `times` for `*` and `.*`, `subsref` for indexing, and so on.

### Calling the original function

A method shadows a built-in only for its own class, so the global function keeps its behaviour for every other type. To reach the original built-in from inside a method, use `builtin`:

```matlab
r = builtin('norm', [3 4])
```

```text
r =

     5
```

### The classic folder-based style

Before `classdef`, overloads were written as separate function files inside an `@ClassName` folder, for example `@Vector3/plus.m`, with the object built from a `struct` by `class`. That style still works and remains handy for adding a single method to an existing type, but `classdef` keeps the whole definition in one file and is the recommended approach for new code.

For the full list of class features, method and property attributes, and inheritance, see the [`classdef` documentation](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/interpreter/classdef.html).

[Back to features](features.md)
