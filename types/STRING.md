- String Array (Unicode):

```
>> A = ["Nelson" "manages"; "string" "array"]

A =

  2×2 string array

    "Nelson"    "manages"
    "string"      "array"

>> class(A)

ans =

    'string'

>> strlength(A)

ans =

     6     7
     6     5

>> B = {'Nelson' 'is' 'open' 'source'}

B =

  1×4 cell array

    {'Nelson'}    {'is'}    {'open'}    {'source'}

>> B = string(B)

B =

  1×4 string array

    "Nelson"    "is"    "open"    "source"

>> C = string('Hello: 你好')

C =

    "Hello: 你好"

>> C(3) = string('World')

C =

  1×3 string array

    "Hello: 你好"    <missing>    "World"

```

[Previous page](../TYPES.md)
