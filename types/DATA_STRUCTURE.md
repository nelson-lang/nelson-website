## data structures

### [cell]https://nelson-lang.github.io/nelson-website/latest/latest/en_US/index.html?open=./data_structures/cell.html)

```matlab
>> ce = {85, 50, 68; 'Pierre', 'Anna', 'Roberto'}

ce =

  2×3 cell array

    {[85]}        {[50]}      {[68]}
    {'Pierre'}    {'Anna'}    {'Roberto'}

```

### [struct](https://nelson-lang.github.io/nelson-website/latest/latest/en_US/index.html?open=./data_structures/struct.html)

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

### [dictionary](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/index.html?open=./dictionary/dictionary.html)

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

### [table](https://nelson-lang.github.io/nelson-gitbook/releases/en_US/latest/index.html?open=./table/table.html)

```matlab
T = table([1; 2], {'A'; 'B'}, 'VariableNames', {'ID', 'Label'})
% Insert a new column 'Score'
T.Score = [10; 20]
% Update the value in row 1, column 'Score'
T{1, 'Score'} = 15
% Extract the 'ID' column from the table
ID_column = T.ID

T =

  2×2 table

    ID    Label
    __    _____

    1     {'A'}
    2     {'B'}


T =

  2×3 table

    ID    Label    Score
    __    _____    _____

    1     {'A'}    10
    2     {'B'}    20


T =

  2×3 table

    ID    Label    Score
    __    _____    _____

    1     {'A'}    15
    2     {'B'}    20


ID_column =

     1
     2

```

[Previous page](../TYPES.md)
