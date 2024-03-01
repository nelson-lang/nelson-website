## Build C/C++ code on the fly

Nelson provides a cross-platform command-line tool written in Nelson for compiling native addon modules for Nelson. It takes away the pain of dealing with the various differences in build platforms.

```matlab
if ispc() && ~havecompiler()
configuremsvc()
end
C_CONTENT = ["double";
"functionC(double x)";
"{";
"    return x + 8;";
"}"];
DEST_DIR = [tempdir(), 'example_C'];
mkdir(DEST_DIR);
C_DEST_FILE = [tempdir(), 'example_C/demo.c'];
filewrite(C_DEST_FILE, C_CONTENT)

dlgeneratemake(DEST_DIR, 'C_DEMO', {C_DEST_FILE}, {DEST_DIR})
[res, message] = dlmake(DEST_DIR)

lib = dlopen([DEST_DIR, '/C_DEMO', getdynlibext()])
c = dllibinfo(lib)

f = dlsym(lib, 'functionC', 'double', {'double'});
R = dlcall(f, 3) % 8 + 3
dlclose(lib)

```

![Nelson environment](https://github.com/nelson-lang/nelson-website/raw/master/images/build_c_cpp_on_fly.png "build on the fly")

[Previous page](FEATURES.md)
