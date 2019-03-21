## [MAT-Files functions I/O](MATIO.md)


Files with the .mat extension are files that are in the binary data container format that MATLAB® uses.

.mat files are categorized as data files that include variables, functions, arrays and other information.

```
A = {"Nelson", "saves"; "cell", "array"};
matfilename = [tempdir(), '/doc_mat.mat'];
save(matfilename, 'A')
clear A
st = load(matfilename)
load(matfilename)
A
```

[Previous page](FEATURES.md)


MATLAB is a registered trademark of The MathWorks, Inc.