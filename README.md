# Pager auto back-and-forth

A version of the Plasma applet Pager implementing a feature of i3wm: [Automatic back-and-forth when switching to the current workspace](https://i3wm.org/docs/userguide.html#workspace_auto_back_and_forth).

## Installation

Run

```
cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
cmake --install build
```

## Activation

### Adding the pager to your panel
1. Right click on your panel.
2. Choose 'Add or Manage Widgets'
3. Click on the new entry named 'Pager (auto back-and-forth)'.

### Enabling auto back-and-forth
1. Right click on the pager.
2. Choose 'Configure Pager (auto back-and-forth)...'.
3. Change the setting 'Selecting current virtual desktop' to 'Switches to the previous desktop'.

## Usage

Click on a different virtual desktop, and click it again to switch to the previously used virtual desktop.
