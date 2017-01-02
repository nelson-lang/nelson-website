## Internal data types:
  - double:

Scalar:

```
--> pi

ans =

     3.1416
```

Vector:

```
--> [0.2:0.2:1]

ans =

     0.2000     0.4000     0.6000     0.8000     1.0000  
```

Complex:

```
--> 3*i

ans =

     0.0000 +   3.0000i
```

```
--> class(pi)

ans =

double
```

2D matrix:

```
--> rand(3, 3)

ans =

     0.5488     0.8443     0.5449  
     0.5928     0.6028     0.8473  
     0.7152     0.8579     0.4237 
```

N Dimensions matrix:

```
--> rand(2,2,2)

ans =

  <double>  - size: 2x2x2
(:,:,1) =


Columns 1 to 2
    0.836078768828884         0.337396161630750      
    0.0710360587108880        0.0871292969677597     
(:,:,2) =


Columns 1 to 2
    0.648171876557171         0.368241537362337      
    0.0202183991204947        0.832619842840359    
```

Sparse:

```
--> sparse(eye(3, 3))

ans =

  (1,1)     1.0000
  (2,2)     1.0000
  (3,3)     1.0000
```

  - Single:

Scalar, vector, matrix 2D, N dimensions array, sparse matrix supported.

```
--> single(rand(2,2))

ans =

  <single>  - size: 2x2

Columns 1 to 2
    0.54881352         0.71518934      
    0.59284461         0.84426576      
```

  - Logical:
  
Scalar, vector, matrix 2D, N dimensions array, sparse matrix supported.

```
--> logical(sparse(eye(3,2)))

ans =

  (1,1) true
  (2,2) true
```

  - String (Unicode):

```
--> disp('Hello: 你好')
Hello: 你好
```

```
--> int32('你好')

ans =

  <int32>  - size: 1x2

Columns 1 to 2
         20320          22909  
```

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

[Previous page](FEATURES.md)
