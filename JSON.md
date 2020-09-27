## JavaScript Object Notation


Functions to transmit data objects consisting of attribute–value pairs and array data types (or any other serializable value). 

Example:

```
field1 = 'f1';  value1 = zeros(1,10);
field2 = 'f2';  value2 = {'a', 'b'};
field3 = 'f3';  value3 = {pi, pi*pi};
field4 = 'f4';  value4 = {'fourth'};
s = struct(field1,value1,field2,value2,field3,value3,field4,value4)
r = jsonencode(s)
r = jsonprettyprint(r)
r2 = jsondecode(r)
```


[Previous page](FEATURES.md)
