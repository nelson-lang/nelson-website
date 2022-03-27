## Foreign Function Interface:

"A foreign function interface (FFI) is a mechanism by which a program written in one programming language can call routines or make use of services written in another."
[see Wikipedia for more information](https://en.wikipedia.org/wiki/Foreign_function_interface)

Example: Call DASUM blas function from Nelson

```matlab
if ispc()
  blas_library_name = ['libnlsblaslapack', getdynlibext()];
else
  blas_library_name = ['libblas', getdynlibext()];
end
lib = dlopen(blas_library_name)
V = [ -2, 1, 3, -5, 4, 0, -1, -3]
N = length(V)
% load DASUM blas symbol (L1 Norm)
f = dlsym(lib, 'DASUM','double',{'int32Ptr','doublePtr','int32Ptr'})
% call DASUM blas symbol with arguments
r = dlcall(f, int32(N), V, int32(1))
assert(r == 19)
% release handles
delete(f);
delete(lib);
% clear variables
clear f
clear lib
```

Example: Call C getpid function from Nelson

```matlab
getpid_symbol = 'getpid';
if ispc()
  lib_c_name = ['msvcrt', getdynlibext()];
else
  lib_c_name = ['libc', getdynlibext()];
end
libc = dlopen(lib_c_name)
% getpid C function from standard libc library
f = dlsym(libc, getpid_symbol, 'int32', {})
% call getpid
pid = dlcall(f)
% release handles
delete(f);
delete(libc);
% clear variables
clear f
clear libc
```

[Previous page](FEATURES.md)
