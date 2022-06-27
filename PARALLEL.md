## [Parallel Computing Module](PARALLEL.md)

Parallel Computing Module allows to solve computationally and data-intensive problems using multicore processors.

Example:

```matlab
% sequential
tic()
R1 = magic(5000);
R2 = magic(5000);
toc()
size(R1)
```

```matlab
% parallel
b = backgroundPool()
tic()
fptr = str2func('magic');
f1 = parfeval(b, fptr, 1, 5000);
f2 = parfeval(b, fptr, 1, 5000);
b
r1 = fetchOutputs(f1);
r2 = fetchOutputs(f2);
toc()
size(r1)
f1
f2
```

[Previous page](FEATURES.md)
