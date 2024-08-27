## [Create User Interface Control](UICONTROL.md)

Nelson provides graphics functions to visualize and export data:

You will find uicontrol documentation: [HERE](https://nelson-lang.github.io/nelson-website/help/en_US/uicontrol.html)

### Example

#### Plot interactive with uicontrol

<img src="https://github.com/nelson-lang/nelson-website/raw/master/images/uicontrol-1.svg" alt="uicontrol-1" width="600" height="400">

Main .m file: (uicontrol_demo.m)

```matlab
% Create a new figure window with specific properties
fig = figure('Name', 'UIControl Demo', 'NumberTitle', 'off', 'Position', [300, 300, 600, 400]);

% Create an axes object within the figure for plotting
ax = axes('Parent', fig, 'Position', [0.2, 0.4, 0.7, 0.5]);

% Set the limits for the Y-axis of the plot
ylim(ax, [-10, 10]);

% Label the X-axis
xlabel('X-Axis');

% Label the Y-axis
ylabel('Y-Axis');

% Enable grid lines on the plot
grid on;

% Set the initial value for the slider control
initialValue = 5;

% Create a push button UI control with a callback function to reset the plot
btn = uicontrol('Style', 'pushbutton', 'String', 'Reset Plot',  'Position', [50, 50, 100, 30], 'Callback', @resetPlot);

% Create a slider UI control with a callback function to update the plot
sld = uicontrol('Style', 'slider', 'Min', 1, 'Max', 10, 'Value', initialValue, 'Position', [200, 50, 300, 30], 'Callback', @updatePlot);

% Generate X data for the plot, ranging from 0 to 2*pi with 100 points
x = linspace(0, 2*pi, 100);

% Compute the sine of the X data to generate Y data
y = sin(x);

% Plot the X and Y data on the axes
p = plot(ax, x, y);

% Store the plot object in the slider's UserData for later use in the callback function
sld.UserData = p;

% Store the plot object, slider, and initial value in the button's UserData for use in the reset callback
btn.UserData = {p, sld, initialValue};
```

Callback function for slider: (updatePlot.m)

```matlab
function updatePlot(h, event)
  % Callback function to update the plot based on the slider value

  % Get the current value of the slider, which determines the amplitude
  scale = h.Value;

  % Retrieve the plot object from the slider's UserData
  p = h.UserData;

  % Access the existing X data of the plot
  x = p.XData;

  % Compute the new Y data by scaling the sine wave based on the slider value
  y = sin(x) * scale;

  % Update the plot with the new X and Y data
  p.XData = x;
  p.YData = y;

  % Update the plot's title to reflect the current amplitude
  title(['Sine Wave with Amplitude = ', num2str(scale)]);

  % Ensure the grid remains on after updating the plot
  grid on;
end
```

Callback function for button: (resetPlot.m)

```matlab
function resetPlot(h, event)
  % Callback function to reset the plot to its original state

  % Reset the labels of the X and Y axes
  xlabel('X-Axis');
  ylabel('Y-Axis');

  % Retrieve the plot object from the button's UserData
  p = h.UserData{1};

  % Generate the original X data for the plot
  x = linspace(0, 2*pi, 100);

  % Generate the original Y data as a sine wave
  y = sin(x);

  % Update the plot with the original X and Y data
  p.XData = x;
  p.YData = y;

  % Ensure the grid is on after resetting the plot
  grid on;

  % Retrieve the slider control from the button's UserData
  sld = h.UserData{2};

  % Reset the slider's value to the initial value stored in UserData
  sld.Value = h.UserData{3};

  % Update the plot's title to reflect the reset amplitude value
  title(['Sine Wave with Amplitude = ', num2str(sld.Value)]);
end
```

Or you can use the following command to run the example:

```matlab
addpath([modulepath('graphics','root'), '/examples/uicontrol'])
edit uicontrol_demo
uicontrol_demo
```

[Previous page](FEATURES.md)
