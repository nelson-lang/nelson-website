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


[Previous page](FEATURES.md)