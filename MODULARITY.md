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

```matlab
>> [name, path] = getmodules()

name =

  64×1 cell array

    {'functions_manager'}      
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
    {'constructors_functions'} 
    {'logical'}                
    {'types'}                  
    {'single'}                 
    {'double'}                 
    {'data_structures'}        
    {'integer'}                
    {'operators'}              
    {'elementary_functions'}   
    {'data_analysis'}          
    {'special_functions'}      
    {'trigonometric_functions'}
    {'sparse'}                 
    {'files_folders_functions'}
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
    {'assert_functions'}       
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
    {'characters_encoding'}    
    {'webtools'}               
    {'graphics'}               
    {'mex'}                    
    {'ipc'}                    
    {'statistics'}             
    {'validators'}             
    {'polynomial_functions'}   
    {'slicot'}                 
    {'fftw'}                   


path =

  64×1 cell array

    {'D:/Developpements/Github/nelson/modules/functions_manager'}      
    {'D:/Developpements/Github/nelson/modules/modules_manager'}        
    {'D:/Developpements/Github/nelson/modules/engine'}                 
    {'D:/Developpements/Github/nelson/modules/core'}                   
    {'D:/Developpements/Github/nelson/modules/localization'}           
    {'D:/Developpements/Github/nelson/modules/i18n'}                   
    {'D:/Developpements/Github/nelson/modules/string'}                 
    {'D:/Developpements/Github/nelson/modules/debugger'}               
    {'D:/Developpements/Github/nelson/modules/error_manager'}          
    {'D:/Developpements/Github/nelson/modules/overload'}               
    {'D:/Developpements/Github/nelson/modules/function_handle'}        
    {'D:/Developpements/Github/nelson/modules/constructors_functions'} 
    {'D:/Developpements/Github/nelson/modules/logical'}                
    {'D:/Developpements/Github/nelson/modules/types'}                  
    {'D:/Developpements/Github/nelson/modules/single'}                 
    {'D:/Developpements/Github/nelson/modules/double'}                 
    {'D:/Developpements/Github/nelson/modules/data_structures'}        
    {'D:/Developpements/Github/nelson/modules/integer'}                
    {'D:/Developpements/Github/nelson/modules/operators'}              
    {'D:/Developpements/Github/nelson/modules/elementary_functions'}   
    {'D:/Developpements/Github/nelson/modules/data_analysis'}          
    {'D:/Developpements/Github/nelson/modules/special_functions'}      
    {'D:/Developpements/Github/nelson/modules/trigonometric_functions'}
    {'D:/Developpements/Github/nelson/modules/sparse'}                 
    {'D:/Developpements/Github/nelson/modules/files_folders_functions'}
    {'D:/Developpements/Github/nelson/modules/os_functions'}           
    {'D:/Developpements/Github/nelson/modules/json'}                   
    {'D:/Developpements/Github/nelson/modules/stream_manager'}         
    {'D:/Developpements/Github/nelson/modules/display_format'}         
    {'D:/Developpements/Github/nelson/modules/file_archiver'}          
    {'D:/Developpements/Github/nelson/modules/dynamic_link'}           
    {'D:/Developpements/Github/nelson/modules/memory_manager'}         
    {'D:/Developpements/Github/nelson/modules/console'}                
    {'D:/Developpements/Github/nelson/modules/interpreter'}            
    {'D:/Developpements/Github/nelson/modules/time'}                   
    {'D:/Developpements/Github/nelson/modules/random'}                 
    {'D:/Developpements/Github/nelson/modules/history_manager'}        
    {'D:/Developpements/Github/nelson/modules/help_tools'}             
    {'D:/Developpements/Github/nelson/modules/gui'}                    
    {'D:/Developpements/Github/nelson/modules/help_browser'}           
    {'D:/Developpements/Github/nelson/modules/assert_functions'}       
    {'D:/Developpements/Github/nelson/modules/tests_manager'}          
    {'D:/Developpements/Github/nelson/modules/linear_algebra'}         
    {'D:/Developpements/Github/nelson/modules/handle'}                 
    {'D:/Developpements/Github/nelson/modules/qml_engine'}             
    {'D:/Developpements/Github/nelson/modules/com_engine'}             
    {'D:/Developpements/Github/nelson/modules/f2c'}                    
    {'D:/Developpements/Github/nelson/modules/nig'}                    
    {'D:/Developpements/Github/nelson/modules/text_editor'}            
    {'D:/Developpements/Github/nelson/modules/mpi'}                    
    {'D:/Developpements/Github/nelson/modules/audio'}                  
    {'D:/Developpements/Github/nelson/modules/hdf5'}                   
    {'D:/Developpements/Github/nelson/modules/matio'}                  
    {'D:/Developpements/Github/nelson/modules/profiler'}               
    {'D:/Developpements/Github/nelson/modules/characters_encoding'}    
    {'D:/Developpements/Github/nelson/modules/webtools'}               
    {'D:/Developpements/Github/nelson/modules/graphics'}               
    {'D:/Developpements/Github/nelson/modules/mex'}                    
    {'D:/Developpements/Github/nelson/modules/ipc'}                    
    {'D:/Developpements/Github/nelson/modules/statistics'}             
    {'D:/Developpements/Github/nelson/modules/validators'}             
    {'D:/Developpements/Github/nelson/modules/polynomial_functions'}   
    {'D:/Developpements/Github/nelson/modules/slicot'}                 
    {'D:/Developpements/Github/nelson/modules/fftw'}                   

```

[Previous page](FEATURES.md)
