## Component Object Model interface:

Component Object Model (COM) is a binary-interface standard for software components introduced by Microsoft (see [Wikipedia](https://en.wikipedia.org/wiki/Component_Object_Model))

- Component Object Model (COM) client interface: binary-interface standard for software components on Windows.

  - actxcontrollist : get list all available control services installed on current Windows.
  - actxserverlist : get list all available active X services installed on current Windows.
  - actxGetRunningServer : get COM handle of an existing COM server.
  - actxserver : creates a COM server.
    ![actxserver example](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/actxserver.jpg "actxserver")

  - COM_used : get list of COM handle currently used in current Nelson's session.
  - iscom : determines if it is a COM handle.
  - overload on : class, delete, disp, fieldnames, get, set, invoke, ismethod, isprop, isvalid, methods.
  - add COM handle.
  - see examples in [modulepath('com_engine'), '/examples/'] directory.
    ![COM_excel example](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/COM_excel.jpg "COM example with Excel")

- On Windows, Nelson can read/write all excel 97-2016 file formats (Excel required) based on COM:
  - COM_xlsread : read a xls/xlsx file.
    ![COM_xlsread example](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/COM_xlsread.jpg "COM_xlsread")
  - COM_xlswrite : write a xls/xlsx file.
  - COM_xlsfinfo : get information about xls/xlsx file.

[Previous page](FEATURES.md)
