## [Nelson Engine API for C (compatible with MEX Engine)](MEX_ENGINE.md)

Creates easily Engine applications (standalone programs) that allow you to call Nelson from your own C/C++ programs.

Example:

Save nex content in a file named `mex_engine_demo_1.c`

```C
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include "engine.h"

int main(int argc, char *argv[])
{
	Engine *ep = NULL;
    mxArray *v = NULL;
    mxArray *result = NULL;
	double v_values[10] = { 9.0, 8.0, 7.0, 6.0, 5.0, 4.0, 3.0, 2.0, 1.0, 0.0 };

	if (!(ep = engOpen(""))) {
		fprintf(stderr, "\nCan't start NELSON engine.\n");
		return EXIT_FAILURE;
	}
	v = mxCreateDoubleMatrix(1, 10, mxREAL);
	memcpy((void *)mxGetPr(v), (void *)v_values, sizeof(v_values));
	if (engPutVariable(ep, "v", v) != 0){
		fprintf(stderr, "\nCan't not put variable into NELSON engine.\n");
		return EXIT_FAILURE;
	}
	if (engEvalString(ep, "v2 = v * 2;") != 0){
		fprintf(stderr, "\nCan't not evaluate string into NELSON engine.\n");
		return EXIT_FAILURE;
	}
    if ((result = engGetVariable(ep, "v2")) == NULL) {
        printf("v2 variable does not exist.\n");
    } else {
        printf("v2 type is %s\t\n", mxGetClassName(result));
    }
	mxDestroyArray(result);
	engClose(ep);
	return EXIT_SUCCESS;
}
```

From Nelson:

It will generate an executable file calling nelson's computation engine.

```matlab
mex('-client', 'engine', 'mex_engine_demo_1.c');
```

Libraries path need to contain nelson path to find Nelson's libraries at runtime.

Set the value to the path returned by the following Nelson command:

`res = modulepath(nelsonroot(),'core','bin')`

(replaces `res` by returned value in next command.)

- on linux:

`export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:res`

`export PATH=$PATH:res`

- on macos:
  `export DYLIB_LIBRARY_PATH=$DYLIB_LIBRARY_PATH:res`

`export PATH=$PATH:res`

- on windows:

`set PATH=%PATH%;res`

[Previous page](FEATURES.md)

MATLAB is a registered trademark of The MathWorks, Inc.
