## data structures

### [cell](https://nelson-lang.github.io/nelson-website/help/en_US/cell.html)

```matlab
>> ce = {85, 50, 68; 'Pierre', 'Anna', 'Roberto'}

ce =

  2×3 cell array

    {[85]}        {[50]}      {[68]}
    {'Pierre'}    {'Anna'}    {'Roberto'}

```

### [struct](https://nelson-lang.github.io/nelson-website/help/en_US/struct.html)

```matlab
>> names = {'Pierre', 'Anna', 'Roberto'}
values =  {45, 42, 13}
st = struct ('name', names, 'age', values)

names =

  1×3 cell array

    {'Pierre'}    {'Anna'}    {'Roberto'}


values =

  1×3 cell array

    {[45]}    {[42]}    {[13]}


st =

  1×3 struct array with fields:

    name
    age

```

### [dictionary](https://nelson-lang.github.io/nelson-website/help/en_US/dictionary.html)

```matlab
>> names = {'Pierre', 'Anna', 'Roberto'};
values =  [45, 42, 13];
d = dictionary(values, names)

d =

  dictionary (double ⟼ cell) with 3 entries:

  45 ⟼ {'Pierre'}
  42 ⟼ {'Anna'}
  13 ⟼ {'Roberto'}

>> d(42)

ans =

  1×1 cell array

    {'Anna'}
```

[Previous page](../TYPES.md)
