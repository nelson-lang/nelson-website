## [Overloading](OVERLOADING.md)

Nelson allows to overload all functions and all operators available in the interpreter.

Some examples are better than a long text.

### functions

In this example, we want to change behavior of `gamma` function for `double` type.

Creates a function file '@double/gamma.m'

```matlab
function r = gamma(A)
 disp('gamma function overload called.')
 r = builtin('gamma', A + 100 )
end
```

add parent directory of '@double' directory and try to call `gamma` with a `double` or `single` type.

If you want to continue to call standard function, see `builtin` function.

### operators

In this example, we want to create an 'complexObj' i.e an special complex number object.

We create an function:

```matlab
function r = complexObj(a, b)
 s.r = a;
 s.i = b;
 r = class(s, 'complexObj');
end
```

This function creates in fact a struct typed 'complexObj', you can consider it as an constructor.

```matlab
o = complexObj(5, 4);
```

You can check the new 'user-defined' type:

```matlab
>> class(o)

ans =

complexObj
```

If you forget the ";" at the end. You have:

```matlab
>> o = complexObj(5, 4)

Error:
Check for incorrect argument data type or missing argument in call to function 'cos'.
```

It is normal because when you create an overloaded object, you need to also create dedicated display (@complexObj/display.m).

```matlab
function display(obj)
  disp('complexObj display:')
  disp('real part');
  disp(obj.r);
  disp('imag part');
  disp(obj.i);
end
```

and extraction function:

```matlab
function r = subsref(varargin)
  obj = varargin{1};
  if varargin{2} == 1
   r = obj.r;
  else
   r = obj.i;
  end
end
```

Result:

```matlab
>> o = complexObj(5, 4)
o =

complexObj_disp:
real part
     5.0000
imag part
     4.0000
```

And if you want to add to 'complexObj', you need also to define: '@complexObj/plus.m'

```matlab
function r = plus(a, b)
  % stupid addition algo.
  R1 = a.r + b.r;
  R2 = a.i + b.i;
  r = complexObj(R1, R2);
end
```

Result of o + o:

```matlab
>> o + o

ans =

complexObj_disp:
real part
    10.0000
imag part
     8.0000
```

This example is available [here](https://github.com/nelson-lang/nelson/tree/master/modules/overload/examples/complex)

This syntax

[Previous page](FEATURES.md)
