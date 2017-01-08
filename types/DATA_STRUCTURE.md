## data structures

### [cell](https://nelson-numerical-software.github.io/nelson-website/help/en_US/cell.html)

```

--> ce = {85, 50, 68; 'Pierre', 'Anna', 'Roberto'}
ce =

  <cell> - size: 2x3

Columns 1 to 3
 [85.000000][50.000000][68.000000]
```

### [struct](https://nelson-numerical-software.github.io/nelson-website/help/en_US/struct.html)

```
--> names = {'Pierre', 'Anna', 'Roberto'}
values =  {45, 42, 13}
st = struct ('name', names, 'age', values)
names =

  <cell> - size: 1x3

Columns 1 to 3
 'Pierre''Anna''Roberto'
values =

  <cell> - size: 1x3

Columns 1 to 3
 [45.000000][42.000000][13.000000]
st =

  <struct> - size: 1x3
  Fields
    name
    age
```


[Previous page](../TYPES.md)
