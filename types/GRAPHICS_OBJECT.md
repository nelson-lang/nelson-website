- Graphics objects:

Graphics objects are the components used by Nelson to create visualizations of data.

Each graphics window and the drawing it contains are represented by hierarchical entities.
The hierarchy top level is the `Figure`. Each `Figure` defines at least one child of type `Axes`. 

```matlab
>> ax = gca()

ax =

  1×1 [graphics_object] 

  axes with properties:

  ALim: [0 0]
  ALimMode: 'auto'
  AmbientLightColor: [0 0 0]
  Box: 'off'
  CLim: [0 1]
  CLimMode: 'auto'
  CameraPosition: [0.500000 0.500000 2]
  CameraPositionMode: 'auto'
  CameraTarget: [0.500000 0.500000 0.500000]
  CameraTargetMode: 'auto'
  CameraUpVector: [0 1 0]
  CameraUpVectorMode: 'auto'
  CameraViewAngle: 0
  CameraViewAngleMode: 'auto'
  Children: [0x1 ]
  Clipping: 'on'
  Color: [1 1 1]
  ColorOrder: [0 0.447000 0.741000 0.850000 0.325000 0.098000 0.929000 0.694000 0.125000 0.494000 0.184000 0.556000 0.466000 0.674000 0.188000 0.301000 0.745000 0.933000 0.635000 0.078000 0.184000]
  DataAspectRatio: [1 1 1]
  DataAspectRatioMode: 'auto'
  DataLimits: [0.000000 0.000000 0.000000 0.000000 0.000000 0.000000]
  FontAngle: 'normal'
  FontName: 'helvetica'
  FontSize: 10
  FontUnits: 'points'
  FontWeight: 'normal'
  GridLineStyle: ':'
  HandleVisibility: 'on'
  HitTest: 'on'
  Interruptible: 'on'
  Layer: 'bottom'
  LineStyleOrder: <>
  LineWidth: 1
  MinorGridLineStyle: ':'
  NextPlot: 'replace'
  OuterPosition: [0.000000 0.000000 1.000000 1.000000]
  Parent: [1x1 figure]
  PlotBoxAspectRatio: [1 1 1]
  PlotBoxAspectRatioMode: 'auto'
  Position: [0.100000 0.100000 0.800000 0.800000]
  PositionMode: 'auto'
  Projection: 'orthographic'
  Selected: 'off'
  SelectionHighlight: 'on'
  Tag: ''
  TextHeight: 15
  TickDir: 'in'
  TickDirMode: 'auto'
  TickLength: [0.010000 0.025000]
  TightInset: [0.000000 0.000000 0.000000 0.000000]
  Title: [0x1 ]
  Type: 'axes'
  Units: 'normalized'
  UserData: [0×0]
  Visible: 'on'
  XAxisLocation: 'bottom'
  XColor: [0 0 0]
  XDir: 'normal'
  XGrid: 'off'
  XLabel: [0x1 ]
  XLim: [0 1]
  XLimMode: 'auto'
  XMinorGrid: 'off'
  XScale: 'linear'
  XTick: [0 0.100000 0.200000 0.300000 0.400000 0.500000 0.600000 0.700000 0.800000 0.900000 1.000000]
  XTickLabel: <>
  XTickLabelMode: 'auto'
  XTickMode: 'auto'
  YAxisLocation: 'left'
  YColor: [0 0 0]
  YDir: 'normal'
  YGrid: 'off'
  YLabel: [0x1 ]
  YLim: [0 1]
  YLimMode: 'auto'
  YMinorGrid: 'off'
  YScale: 'linear'
  YTick: [0 0.100000 0.200000 0.300000 0.400000 0.500000 0.600000 0.700000 0.800000 0.900000 1.000000]
  YTickLabel: <>
  YTickLabelMode: 'auto'
  YTickMode: 'auto'
  ZColor: [0 0 0]
  ZDir: 'normal'
  ZGrid: 'off'
  ZLabel: [0x1 ]
  ZLim: [0 1]
  ZLimMode: 'auto'
  ZMinorGrid: 'off'
  ZScale: 'linear'
  ZTick: [0 0.500000 1]
  ZTickLabel: <>
  ZTickLabelMode: 'auto'
  ZTickMode: 'auto'
```

[Previous page](../TYPES.md)
