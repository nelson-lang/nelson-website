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
--> a = qml_loadfile('hello.qml')
a =

[QML] - size: 1x1

	parent: handle  []
	children: handle 1x2
	active: bool true
	activeFocusItem: QQuickItem* handle
	color: QColor #ffffff
	contentItem: QQuickItem* handle
	contentOrientation: int 0
	flags: int 134279169
	height: int 360
	maximumHeight: int 16777215
	maximumWidth: int 16777215
	minimumHeight: int 0
	minimumWidth: int 0
	modality: int 0
	objectName: QString Fenetre
	opacity: double 1
	title: QString Qml Window
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
--> disp(a)
[QML] - size: 1x1

	parent: handle  []
	children: handle 1x2
	active: bool false
	color: QColor #ffffff
	contentItem: QQuickItem* handle
	contentOrientation: int 0
	flags: int 134279169
	height: int 360
	maximumHeight: int 16777215
	maximumWidth: int 16777215
	minimumHeight: int 0
	minimumWidth: int 0
	modality: int 0
	objectName: QString Fenetre
	opacity: double 1
	title: QString Qml Window
	visibility: int 2
	visible: bool true
	width: int 360
	x: int 780
	y: int 335
```

```
--> fieldnames(a)

ans =

  <cell> - size: 19x1

Columns 1 to 1
 'active'
 'color'
 'contentItem'
 'contentOrientation'
 'flags'
 'height'
 'maximumHeight'
 'maximumWidth'
 'minimumHeight'
 'minimumWidth'
 'modality'
 'objectName'
 'opacity'
 'title'
 'visibility'
 'visible'
 'width'
 'x'
 'y'
```

Example how to modify title of the button "Button":

Get children of the figure created by 'hello.qml'

```
% or children = get(a, 'children')
--> children = a.children
children =

[QML] - size: 1x2
```

Two children, previously created:

one for text field with "hello world" content,

```
--> text_child = children(1)
text_child =

[QML] - size: 1x1

	parent: handle
	children: handle []
	activeFocus: bool false
	activeFocusOnTab: bool false
	anchors: QQuickAnchors* handle
	antialiasing: bool true
	baseUrl: QUrl file:///D:/Developpements/GitHub/nelson-qml//hello.qml
	baselineOffset: double 13
	bottomPadding: double 0
	bottomPadding: double 0
	childrenRect: QRectF x:0 y:0 w:0 h:0
	clip: bool false
	color: QColor #000000
	contentHeight: double 16
	contentWidth: double 69
	effectiveHorizontalAlignment: int 1
	elide: int 3
	enabled: bool true
	focus: bool false
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
	linkColor: QColor #0000ff
	maximumLineCount: int 2147483647
	minimumPixelSize: int 12
	minimumPointSize: int 12
	objectName: QString text1
	opacity: double 1
	padding: double 0
	paintedHeight: double 16
	paintedWidth: double 69
	paintedWidth: double 69
	renderType: int 0
	rightPadding: double 0
	rotation: double 0
	scale: double 1
	smooth: bool true
	state: QString
	style: int 0
	styleColor: QColor #000000
	text: QString Hello world!
	textFormat: int 2
	topPadding: double 0
	transformOrigin: int 4
	transformOriginPoint: QPointF x:34.500000 y:8.000000
	truncated: bool false
	verticalAlignment: int 32
	visible: bool true
	width: double 69
	wrapMode: int 0
	x: double 0
	y: double 0
	z: double 0
```

one for the button with "Button" content:

```
--> button_child = children(2)
button_child =

[QML] - size: 1x1

	parent: handle
	children: handle 1x12
	__action: QQuickAction1* handle
	__behavior: QObject* handle
	__effectivePressed: bool false
	__iconAction: QQuickAction1* handle
	__iconOverriden: bool false
	__panel: QQuickItem* handle
	__position: QString only
	__style: QObject* handle
	activeFocus: bool false
	activeFocusOnPress: bool false
	activeFocusOnTab: bool true
	anchors: QQuickAnchors* handle
	antialiasing: bool false
	baselineOffset: double 19
	checkable: bool false
	checked: bool false
	checked: bool false
	childrenRect: QRectF x:0 y:0 w:93 h:28
	clip: bool false
	enabled: bool true
	focus: bool false
	height: double 28
	hovered: bool false
	iconName: QString
	iconSource: QUrl
	implicitHeight: double 28
	implicitWidth: double 93
	isDefault: bool false
	layer: QQuickItemLayer* handle
	objectName: QString myBut1
	opacity: double 1
	opacity: double 1
	pressed: bool false
	rotation: double 0
	scale: double 1
	smooth: bool true
	state: QString
	style: QQmlComponent* handle
	text: QString Button
	tooltip: QString
	transformOrigin: int 4
	transformOriginPoint: QPointF x:46.500000 y:14.000000
	visible: bool true
	width: double 93
	x: double 133
	y: double 166
	z: double 0
```

To get the text of the button:

```
% text_button = get(button_child, 'text')
--> text_button = button_child.text
text_button =

Button
```

To set the text of the button:

```
% or set(button_child, 'text', 'new button text'); button_child
--> button_child.text = 'new button text'; button_child

[QML] - size: 1x1

	parent: handle
	children: handle 1x12
	__action: QQuickAction1* handle
	__behavior: QObject* handle
	__effectivePressed: bool false
	__iconAction: QQuickAction1* handle
	__iconOverriden: bool false
	__panel: QQuickItem* handle
	__position: QString only
	__style: QObject* handle
	activeFocus: bool false
	activeFocusOnPress: bool false
	activeFocusOnTab: bool true
	anchors: QQuickAnchors* handle
	antialiasing: bool false
	baselineOffset: double 19
	checkable: bool false
	checked: bool false
	checked: bool false
	childrenRect: QRectF x:0 y:0 w:98 h:28
	clip: bool false
	enabled: bool true
	focus: bool false
	height: double 28
	hovered: bool false
	iconName: QString
	iconSource: QUrl
	implicitHeight: double 28
	implicitWidth: double 98
	isDefault: bool false
	layer: QQuickItemLayer* handle
	objectName: QString myBut1
	opacity: double 1
	opacity: double 1
	pressed: bool false
	rotation: double 0
	scale: double 1
	smooth: bool true
	state: QString
	style: QQmlComponent* handle
	text: QString new button text
	tooltip: QString
	transformOrigin: int 4
	transformOriginPoint: QPointF x:49 y:14
	visible: bool true
	width: double 98
	x: double 131
	y: double 166
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
