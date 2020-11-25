## [HDF5 High Level functions I/O](HDF5.md)

[HDF5](https://en.wikipedia.org/wiki/Hierarchical_Data_Format) is a file format for storing very large datasets.

High-level functions make it easy to read a data set from an HDF5 file or write a variable from Nelson into an HDF5 file.

Example:

```
h5filename = [tempdir(), '/doc_h5write.h5'];
h5write(h5filename,'/rand', rand(3, 4));
h5write(h5filename,'/str', 'Hello');
h5dump(h5filename)
h5read(h5filename,'/rand')
h5read(h5filename,'/str')
```

Files with the .nh5 extension are files that are in the binary data container format that Nelson uses.

.nh5 files are categorized as data files that include variables, functions, arrays and other information.

```
A = ["Nelson", "saves"; "string", "array"];
nh5filename = [tempdir(), '/doc_nh5.nh5'];
save(nh5filename, 'A')
clear A
st = load(nh5filename)
load(nh5filename)
A
```

[Previous page](FEATURES.md)
