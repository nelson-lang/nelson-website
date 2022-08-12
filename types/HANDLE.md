## handle object

This feature is available with version 0.1.6 and more:

A handle is a reference to an internal object (equivalent to C++ pointer).
Nelson allows to manipulate a generic type: handle and support overloading on this type.

Currently, Nelson allows to use QML objects (GUI & graphics) as handles.
Other pointers can be added easily in the future (COM, java, ...)

Example:

In this example, we load a basic qml file and modify text of the button:

hello.qml:

```
import QtQuick 2.0
import QtQuick.Window 2.0
import QtQuick.Controls 1.4


Window {
    id: mainWindow
    visible: true
    width: 360
    height: 360
    title: "Qml Window"
    objectName: "Fenetre"
    Text {
        id: text
        text: "Hello world!"
        objectName: "text1"
    }


    Button {
        text: "Button"
        anchors.centerIn: parent
        onClicked: nelson.evaluate("A = 3")
        objectName: "myBut1"
    }
}
```

```
>> a = qml_loadfile('hello.qml')

a =

  1×1 handle [QObject]

	active: bool true
	activeFocusItem: QQuickItem* handle
	children: handle 1x3
	className: QQuickWindow
	color: QColor r:255 g:255 b:255 a:255
	contentItem: QQuickItem* handle
	contentOrientation: int 0
	data: QQmlListProperty<QObject> handle
	flags: int 1
	height: int 360
	maximumHeight: int 16777215
	maximumWidth: int 16777215
	minimumHeight: int 0
	minimumWidth: int 0
	modality: int 0
	objectName: QString basic_window
	opacity: double 1
	parent: handle
	title: QString Qml Window
	transientParent: QWindow* handle
	visibility: int 2
	visible: bool true
	width: int 360
	x: int 780
	y: int 335

```

![hello QML](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/hello_qml.png "hello")

With overloading, many basic functions come available for handles:

examples: disp, size, fieldnames, ...

```
>> disp(a)
  1×1 handle [QObject]

	active: bool false
	activeFocusItem: QQuickItem* handle
	children: handle 1x3
	className: QQuickWindow
	color: QColor r:255 g:255 b:255 a:255
	contentItem: QQuickItem* handle
	contentOrientation: int 0
	data: QQmlListProperty<QObject> handle
	flags: int 1
	height: int 360
	maximumHeight: int 16777215
	maximumWidth: int 16777215
	minimumHeight: int 0
	minimumWidth: int 0
	modality: int 0
	objectName: QString basic_window
	opacity: double 1
	parent: handle
	title: QString Qml Window
	transientParent: QWindow* handle
	visibility: int 2
	visible: bool true
	width: int 360
	x: int 780
	y: int 335
```

```
>> fieldnames(a)

ans =

  25×1 cell array

              {'active'}
     {'activeFocusItem'}
            {'children'}
           {'className'}
               {'color'}
         {'contentItem'}
    {'contentOrientat…'}
                {'data'}
               {'flags'}
              {'height'}
       {'maximumHeight'}
        {'maximumWidth'}
       {'minimumHeight'}
        {'minimumWidth'}
            {'modality'}
          {'objectName'}
             {'opacity'}
              {'parent'}
               {'title'}
     {'transientParent'}
          {'visibility'}
             {'visible'}
               {'width'}
                   {'x'}
                   {'y'}

```

Example how to modify title of the button "Button":

Get children of the figure created by 'hello.qml'

```
% or children = get(a, 'children')
>> children = a.children

children =

  1×3 handle

```

Two children, previously created:

one for text field with "hello world" content,

```
>> text_child = children(1)

text_child =

  1×1 handle [QObject]

	activeFocus: bool false
	activeFocusOnTab: bool false
	anchors: QQuickAnchors* handle
	antialiasing: bool false
	baselineOffset: double 0
	childrenRect: QRectF x:0 y:0 w:226 h:194
	className: QQuickRootItem
	clip: bool false
	containmentMask: QObject* handle
	data: QQmlListProperty<QObject> handle
	enabled: bool true
	focus: bool false
	height: double 360
	implicitHeight: double 0
	implicitWidth: double 0
	layer: QQuickItemLayer* handle
	objectName: QString
	opacity: double 1
	parent: handle
	rotation: double 0
	scale: double 1
	smooth: bool true
	state: QString
	transformOrigin: int 4
	transformOriginPoint: QRectF x:180 y:180
	visible: bool true
	visibleChildren: QQmlListProperty<QQuickItem> handle
	width: double 360
	x: double 0
	y: double 0
	z: double 0

```

one for the button with "Button" content:

```
>> button_child = children(2)

button_child =

  1×1 handle [QObject]

	activeFocus: bool false
	activeFocusOnTab: bool false
	advance: QSizeF handle
	anchors: QQuickAnchors* handle
	antialiasing: bool true
	baseUrl: QUrl file:///D:/Developpements/Github/nelson/modules/qml_engine/examples/basic_window/hello.qml
	baselineOffset: double 13
	bottomPadding: double 0
	childrenRect: QRectF x:0 y:0 w:0 h:0
	className: QQuickText
	clip: bool false
	color: QColor r:0 g:0 b:0 a:255
	containmentMask: QObject* handle
	contentHeight: double 16
	contentWidth: double 69
	effectiveHorizontalAlignment: int 1
	elide: int 3
	enabled: bool true
	focus: bool false
	font: QFont MS Shell Dlg 2,7.8,-1,5,50,0,0,0,0,0
	fontInfo: QJSValue handle
	fontSizeMode: int 0
	height: double 16
	horizontalAlignment: int 1
	hoveredLink: QString
	implicitHeight: double 16
	implicitWidth: double 69
	layer: QQuickItemLayer* handle
	leftPadding: double 0
	lineCount: int 1
	lineHeight: double 1
	lineHeightMode: int 0
	linkColor: QColor r:0 g:0 b:255 a:255
	maximumLineCount: int 2147483647
	minimumPixelSize: int 12
	minimumPointSize: int 12
	objectName: QString text1
	opacity: double 1
	padding: double 0
	paintedHeight: double 16
	paintedWidth: double 69
	parent: handle
	renderType: int 0
	rightPadding: double 0
	rotation: double 0
	scale: double 1
	smooth: bool true
	state: QString
	style: int 0
	styleColor: QColor r:0 g:0 b:0 a:255
	text: QString Hello world!
	textFormat: int 2
	topPadding: double 0
	transformOrigin: int 4
	transformOriginPoint: QRectF x:34.500000 y:8.000000
	truncated: bool false
	verticalAlignment: int 32
	visible: bool true
	width: double 69
	wrapMode: int 0
	x: double 0
	y: double 0
	z: double 0

```

To get the text of the button:

```matlab
% text_button = get(button_child, 'text')
>> text_button = button_child.text

text_button =

    'Hello world!'

```

To set the text of the button:

```matlab
% or set(button_child, 'text', 'new button text'); button_child
>> button_child.text = 'new button text'; button_child

button_child =

  1×1 handle [QObject]

	activeFocus: bool false
	activeFocusOnTab: bool false
	advance: QSizeF handle
	anchors: QQuickAnchors* handle
	antialiasing: bool true
	baseUrl: QUrl file:///D:/Developpements/Github/nelson/modules/qml_engine/examples/basic_window/hello.qml
	baselineOffset: double 13
	bottomPadding: double 0
	childrenRect: QRectF x:0 y:0 w:0 h:0
	className: QQuickText
	clip: bool false
	color: QColor r:0 g:0 b:0 a:255
	containmentMask: QObject* handle
	contentHeight: double 16
	contentWidth: double 89
	effectiveHorizontalAlignment: int 1
	elide: int 3
	enabled: bool true
	focus: bool false
	font: QFont MS Shell Dlg 2,7.8,-1,5,50,0,0,0,0,0
	fontInfo: QJSValue handle
	fontSizeMode: int 0
	height: double 16
	horizontalAlignment: int 1
	hoveredLink: QString
	implicitHeight: double 16
	implicitWidth: double 89
	layer: QQuickItemLayer* handle
	leftPadding: double 0
	lineCount: int 1
	lineHeight: double 1
	lineHeightMode: int 0
	linkColor: QColor r:0 g:0 b:255 a:255
	maximumLineCount: int 2147483647
	minimumPixelSize: int 12
	minimumPointSize: int 12
	objectName: QString text1
	opacity: double 1
	padding: double 0
	paintedHeight: double 16
	paintedWidth: double 89
	parent: handle
	renderType: int 0
	rightPadding: double 0
	rotation: double 0
	scale: double 1
	smooth: bool true
	state: QString
	style: int 0
	styleColor: QColor r:0 g:0 b:0 a:255
	text: QString new button text
	textFormat: int 2
	topPadding: double 0
	transformOrigin: int 4
	transformOriginPoint: QRectF x:44.500000 y:8.000000
	truncated: bool false
	verticalAlignment: int 32
	visible: bool true
	width: double 89
	wrapMode: int 0
	x: double 0
	y: double 0
	z: double 0
```

The result:

![hello QML modified](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/hello_qml_modified.png "hello modified")

Others examples about QML capabilities:

Advanced example with QML:
![Advanced example with QML](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/qml-nelson-handle-properties.png "Advanced example with QML")

Nelson interaction with QML and D3.js:
![Nelson interaction with QML and D3.js](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/qml-nelson-d3.png "Nelson interaction with QML and D3.js")

Nelson interaction with QML and QCharts.js:
![Nelson interaction with QML and QCharts.js](https://github.com/Nelson-numerical-software/nelson-website/raw/master/images/qml-nelson-QCharts.png "Nelson interaction with QML and QCharts.js")

[Previous page](../TYPES.md)
