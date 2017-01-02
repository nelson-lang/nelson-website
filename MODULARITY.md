## Modularity

Each "module" (toolboxe) can be disabled or replaced by another:

```
¦   loader.nls
¦
+---etc
¦       finish.nls
¦       startup.nls
¦
+---functions
¦       *.nlf
¦
+---help
¦   +---en_US
¦           org.nelson.modules.*.help.qch
¦
+---tests
        *.nls
```

```
--> [name,path]=getmodules
name =

  <cell> - size: 36x1

Columns 1 to 1
 'dynamic_link'
 'modules_manager'
 'engine'
 'functions_manager'
 'core'
 'localization'
 'i18n'
 'string'
 'error_manager'
 'function_handle'
 'constructors_functions'
 'types'
 'single'
 'double'
 'data_structures'
 'integer'
 'elementary_functions'
 'trigonometric_functions'
 'sparse'
 'logical'
 'files_folders_functions'
 'os_functions'
 'memory_manager'
 'console'
 'stream_manager'
 'interpreter'
 'time'
 'random'
 'history_manager'
 'help_tools'
 'gui'
 'help_browser'
 'assert_functions'
 'tests_manager'
 'cacsd'
 'module_skeleton'
path =

  <cell> - size: 36x1

Columns 1 to 1
 'D:/Developpements/GitHub/nelson/modules/dynamic_link'
 'D:/Developpements/GitHub/nelson/modules/modules_manager'
 'D:/Developpements/GitHub/nelson/modules/engine'
 'D:/Developpements/GitHub/nelson/modules/functions_manager'
 'D:/Developpements/GitHub/nelson/modules/core'
 'D:/Developpements/GitHub/nelson/modules/localization'
 'D:/Developpements/GitHub/nelson/modules/i18n'
 'D:/Developpements/GitHub/nelson/modules/string'
 'D:/Developpements/GitHub/nelson/modules/error_manager'
 'D:/Developpements/GitHub/nelson/modules/function_handle'
 'D:/Developpements/GitHub/nelson/modules/constructors_functions'
 'D:/Developpements/GitHub/nelson/modules/types'
 'D:/Developpements/GitHub/nelson/modules/single'
 'D:/Developpements/GitHub/nelson/modules/double'
 'D:/Developpements/GitHub/nelson/modules/data_structures'
 'D:/Developpements/GitHub/nelson/modules/integer'
 'D:/Developpements/GitHub/nelson/modules/elementary_functions'
 'D:/Developpements/GitHub/nelson/modules/trigonometric_functions'
 'D:/Developpements/GitHub/nelson/modules/sparse'
 'D:/Developpements/GitHub/nelson/modules/logical'
 'D:/Developpements/GitHub/nelson/modules/files_folders_functions'
 'D:/Developpements/GitHub/nelson/modules/os_functions'
 'D:/Developpements/GitHub/nelson/modules/memory_manager'
 'D:/Developpements/GitHub/nelson/modules/console'
 'D:/Developpements/GitHub/nelson/modules/stream_manager'
 'D:/Developpements/GitHub/nelson/modules/interpreter'
 'D:/Developpements/GitHub/nelson/modules/time'
 'D:/Developpements/GitHub/nelson/modules/random'
 'D:/Developpements/GitHub/nelson/modules/history_manager'
 'D:/Developpements/GitHub/nelson/modules/help_tools'
 'D:/Developpements/GitHub/nelson/modules/gui'
 'D:/Developpements/GitHub/nelson/modules/help_browser'
 'D:/Developpements/GitHub/nelson/modules/assert_functions'
 'D:/Developpements/GitHub/nelson/modules/tests_manager'
 'D:/Developpements/GitHub/nelson/modules/cacsd'
 'D:/developpements/github/nelson/module_skeleton'
```

[Previous page](FEATURES.md)
