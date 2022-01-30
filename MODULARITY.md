## Modularity

Each "module" (toolboxe) can be disabled or replaced by another:

```
¦   loader.m
¦
+---etc
¦       finish.m
¦       startup.m
¦
+---functions
¦       *.m
¦
+---help
¦   +---en_US
¦           org.nelson.modules.*.help.qch
¦
+---tests
        test_*.m
        bug_*.m
        bench_*.m
```

```
>> [name, path] = getmodules()

name =

  64×1 cell array

    {'functions_manag…'}
     {'modules_manager'}
              {'engine'}
                {'core'}
        {'localization'}
                {'i18n'}
              {'string'}
            {'debugger'}
       {'error_manager'}
            {'overload'}
     {'function_handle'}
    {'constructors_fu…'}
             {'logical'}
               {'types'}
              {'single'}
              {'double'}
     {'data_structures'}
             {'integer'}
           {'operators'}
    {'elementary_func…'}
       {'data_analysis'}
    {'special_functio…'}
    {'trigonometric_f…'}
              {'sparse'}
    {'files_folders_f…'}
        {'os_functions'}
                {'json'}
      {'stream_manager'}
      {'display_format'}
       {'file_archiver'}
        {'dynamic_link'}
      {'memory_manager'}
             {'console'}
         {'interpreter'}
                {'time'}
              {'random'}
     {'history_manager'}
          {'help_tools'}
                 {'gui'}
        {'help_browser'}
    {'assert_function…'}
       {'tests_manager'}
      {'linear_algebra'}
              {'handle'}
          {'qml_engine'}
          {'com_engine'}
                 {'f2c'}
                 {'nig'}
         {'text_editor'}
                 {'mpi'}
               {'audio'}
                {'hdf5'}
               {'matio'}
            {'profiler'}
    {'characters_enco…'}
            {'webtools'}
            {'graphics'}
                 {'mex'}
                 {'ipc'}
          {'statistics'}
          {'validators'}
    {'polynomial_func…'}
              {'slicot'}
                {'fftw'}


path =

  64×1 cell array

    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
    {'D:/Developpemen…'}
```

[Previous page](FEATURES.md)
