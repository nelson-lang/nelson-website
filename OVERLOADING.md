## [Overloading](OVERLOADING.md)

Nelson allows to overload all operators available in the interpreter.

An example is better than a long text.

In this example, we want to create an 'complexObj' i.e an special complex number object

We create an function:
```
function r = complexObj(a, b)
 s.r = a;
 s.i = b;
 r = class(s, 'complexObj');
endfunction
```
This function creates in fact a struct typed 'complexObj', you can consider it as an constructor.

```
o = complexObj(5, 4);
```

If you forget the ';' at the end. You have:
```
--> o = complexObj(5, 4)
o =

function complexObj_disp undefined.
called from:
EvaluateString
```
It is normal because when you create an overloaded object, you need to also create dedicated display.
```
function complexObj_disp(obj)
  disp('complexObj_disp:')
  disp('real part');
  disp(obj.r);
  disp('imag part');
  disp(obj.i);
endfunction
```

and extraction function
```
function r = complexObj_extraction(varargin)
  obj = varargin{1};
  if varargin{2} == 1
   r = obj.r;
  else
   r = obj.i;
  end
endfunction
```

Result:
```
--> o = complexObj(5, 4)
o =

complexObj_disp:
real part
     5.0000
imag part
     4.0000
```

And if you want to add to 'complexObj', you need also to define: 'complexObj_plus_complexObj'
```
--> complexObj_plus_complexObj
Undefined variable or function: complexObj_plus_complexObj
```

```
function r = complexObj_plus_complexObj(a, b)
  // stupid addition algo.
  R1 = a.r + b.r;
  R2 = a.i + b.i;
  r = complexObj(R1, R2);
endfunction
```

```
--> o + o

ans =

complexObj_disp:
real part
    10.0000
imag part
     8.0000
```


[Previous page](FEATURES.md)
