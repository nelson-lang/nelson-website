---
title: "Integer types"
description: "Signed and unsigned 8, 16, 32, and 64-bit integer types in Nelson, with saturating arithmetic."
---

# Integer types

Integers come in 8, 16, 32, and 64-bit signed and unsigned forms. Scalars, vectors, 2-D matrices, and N-dimensional arrays are supported.

```matlab
>> intmax('int8')

ans =

  int8

   127

>> intmax('int16')

ans =

  int16

   32767

>> intmax('int32')

ans =

  int32

   2147483647

>> intmax('int64')

ans =

  int64

   9223372036854775807

```

Integer supports saturation:

```matlab
>>  int8(200) + int8(60)

ans =

  int8

   127
```

[Back to data types](../types.md)
