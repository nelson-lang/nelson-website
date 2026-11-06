---
title: "C MEX API support"
description: "Nelson includes an interface to allow legacy mex-files to be compiled and linked with Nelson."
---

# C MEX API support

Nelson includes an interface to allow legacy mex-files to be compiled and linked with Nelson.

A MEX file provides an interface between the interpreter and functions written in C or C++,
following the widely used MEX convention so that legacy MEX sources can be reused.

Nelson also has its own C++ API to manage its internal objects more easily.

```matlab
mex('mexPrintf.c');
```

```C
#include <mex.h>

void
mexFunction (int nlhs, mxArray *plhs[], int nrhs, const mxArray *prhs[])
{
    size_t i = 0;
    for (i = 0; i < 2; ++i){
        mexPrintf ("Result %d\n", i);
    }
}
```

[Back to features](features.md)
