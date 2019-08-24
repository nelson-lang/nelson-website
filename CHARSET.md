## UNICODE and charset support


Nelson supports more 30 charset encoding including UNICODE

Examples:

```
R = unicode2native('片仮名', 'SHIFT_JIS')
native2unicode(R, 'SHIFT_JIS')
```

```
str = 'живете зело, земля, и иже и како люди';
filewrite([tempdir(), 'example_fileread.txt'], str, 'native', 'windows-1251')
T1 = fileread([tempdir(), 'example_fileread.txt'], 'char', 'native', 'windows-1251')
T2 = fileread([tempdir(), 'example_fileread.txt'], 'string', 'native', 'auto')
```


[Previous page](FEATURES.md)
