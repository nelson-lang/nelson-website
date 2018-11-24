## QML engine:

The QML engine enables nelson programs to display and manipulate graphical content using Qt's QML framework.
```
  qml_demos // for demonstrations
```
![qml_demos screenshot](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/qml_demos.png "qml_demos")


![checkboxes screenshot](https://github.com/Nelson-numerical-software/nelson-website/blob/master/images/demo_checkboxes.png "checkboxes demo")

### Interacting with Nelson

Interaction with Nelson happens through the following mechanisms:
* Call Nelson functions from QML,

```
    Button {
        text: "Button"
        anchors.centerIn: parent 
        onClicked: nelson.disp('button pressed.')
        objectName: "myButton"
    }
```

* Read and set context properties from Nelson and QML.

```

--> h1 = errordlg()
h1 =

[QObject] - size: 1x1

	__maximumDimension: int 927
	className: QQuickAbstractMessageDialog
	clickedButton: int 0
	detailedText: QString 
	height: int 0
	icon: int 3
	informativeText: QString 
	isWindow: bool true
	modality: int 0
	objectName: QString errordlg
	parent: handle
	standardButtons: int 1024
	standardIconSource: QUrl images/critical.png
	text: QString This is the default error string.
	title: QString Error Dialog
	visible: bool true
	width: int 0
	x: int 0
	y: int 0

```


[Previous page](FEATURES.md)