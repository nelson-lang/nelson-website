## [C MEX API support](MEX.md)

Nelson includes an interface to allow legacy mex-files to be compiled and linked with Nelson.

A mex file is a type of computer file that provides an interface between Octave or the reference commercial software and functions written in C, C++.

Nelson have also his own C++ API to manage more easily internal nelson's objects.

```
mex('mexPrintf.c');
```

```
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

[Previous page](FEATURES.md)

MATLAB is a registered trademark of The MathWorks, Inc.
