# Godot

## Shortcuts

### General
 - `Ctrl + F1/F2/F3` - Switch to 2D/3D/Script view, respectively.
 - `Ctrl + Tab` - Switch tab forwards.
 - `Ctrl + Shift + Tab` - Switch tab backwards.
 - `Ctrl + Shift + Q` - Quit to project list
 - `F` - Center viewport onto the selected node?
 - `W` - Move Mode
 - `Q` - Select Mode
 - `E` - Rotate Mode
 - `S` - Scale Mode
 - `R` - Ruler Mode
 - `Shift + S` - Smart snap
 - `Shift + G` - Grid snap
 - `Ctrl + '` - Show grid
 - `Y` - Show guides
 - `Alt + Drag` - Move nodes
 - `Alt + Shift + Drag` - Move node on axis.
 - `Ctrl + Drag` - Rotate node.
 - `Ctrl + Alt + Drag` - Scale node.
 - `Ctrl + Alt + Shift + Drag` - Scale uniform node.
 - `Alt + 1` - <CUSTOM> Switch to 2D editor.
 - `Alt + 2` - <CUSTOM> Switch to script editor.
 - `F8` - Stops running project
 - `F5` - Run project
 - `F6` - Run scene
 - `F7` - Pause running project
 - `Shift + F12` - Expand bottom (debug) panel

### Scene Tree
 - `Ctrl + A` - Add new node.
 - `Ctrl + Shift + A` - Add new child node.
 - `Ctrl + N` - Create new scene.
 - `Ctrl + D` - Duplicate node.
 - `Ctrl + Up/Down` - Move node up/down tree, respectively.

### Script Editor
 - `Ctrl + Shift + F` - Search through all scripts.
 - `Ctrl + \` - Toggle script panel visibility.
 - `Ctrl + Shift + F11 - Focus mode.
 - `Ctrl + R` - Replace modal.
 - `Ctrl + Shift + ,/.` - Go to next/previous script file, respectively.
 - `Ctrl + Alt + O` - Quick open script
 - `Ctrl + Shift + O` - Quick open scene

## Debugging
`F5` - Runs project
`F10` - Steps over
`F11` - Steps into


## Tips
 - Collion layers define which layer the object is in, while mark defines which layers it can interact with.
 - Use print_debug() to show where it is being printed from.
 - To click on a specific node that is stacked on others, use `Select Mode` and alt right-click to select.

## Conventions
### Naming Conventions
Type		Convention	Info
File names	snake_case	yaml_parsed.gd
class_name	PascalCase	YAMLParser
Node names	PascalCase	
Functions	snake_case	
Variables	snake_case	
Signals		snake_case	always in past tense "door_opened"
Constants	CONSTANT_CASE	
enum names	PascalCase	
enum members	CONSTANT_CASE	


### Code order
01. tool 
02. class_name 
03. extends 
04. # docstring
05. signals
06. enums
07. constants
08. exported variables
09. public variables
10. private variables
11. onready variables
12. optional built-in virtual _init method
13. built-in virtual _ready method
14. remaining built-in virtual methods
15. public methods
16. private methods 
