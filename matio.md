---
title: "MAT-Files functions I/O"
description: "Files with the .mat extension use a widely adopted binary data-container format for array data, so Nelson can exchange variables with other."
---

# MAT-Files functions I/O

Files with the `.mat` extension use a widely adopted binary data-container format for array data, so Nelson can exchange variables with other array-computing tools.

.mat files are categorized as data files that include variables, functions, arrays and other information.

```matlab
A = {"Nelson", "saves"; "cell", "array"};
matfilename = [tempdir(), '/doc_mat.mat'];
save(matfilename, 'A')
clear A
st = load(matfilename)
load(matfilename)
A
```

[Back to features](features.md)
