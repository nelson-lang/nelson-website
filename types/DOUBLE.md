- double:

Scalar:

```matlab
>>  pi

ans =

    3.1416

```

Vector:

```matlab
>> [0.2:0.2:1]

ans =

    0.2000    0.4000    0.6000    0.8000    1.0000

```

Complex:

```matlab
>>  3*i

ans =

   0.0000 + 3.0000i

```

```matlab
>> class(pi)

ans =

    'double'

```

2D matrix:

```matlab
>>  rand(3, 3)

ans =

    0.9575    0.9706    0.8003
    0.9649    0.9572    0.1419
    0.1576    0.4854    0.4218

```

N Dimensions matrix:

```matlab
>> rand(2,2,2)

ans(:,:,1) =

    0.8147    0.1270
    0.9058    0.9134


ans(:,:,2) =

    0.6324    0.2785
    0.0975    0.5469

```

Sparse:

```matlab
>> sparse(eye(3, 3))

ans =

   (1,1)        1
   (2,2)        1
   (3,3)        1

```

[Previous page](../TYPES.md)
