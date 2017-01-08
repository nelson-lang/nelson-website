  - Integers: 8, 16, 32, 64 signed and unsigned: scalar, vector, matrix 2D, N dimensions array supported.

```
--> intmax('int8')

ans =

  <int8>  - size: 1x1
  127  

--> intmax('int16')

ans =

  <int16>  - size: 1x1
  32767  

--> intmax('int32')

ans =

  <int32>  - size: 1x1
    2147483647  

--> intmax('int64')

ans =

  <int64>  - size: 1x1
 9223372036854775807  
```

Integer supports saturation:

```
--> int8(200) + int8(60)

ans =

  <int8>  - size: 1x1
  127  
```

[Previous page](../TYPES.md)