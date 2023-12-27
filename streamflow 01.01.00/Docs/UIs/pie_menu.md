# Pie Menus
<br>
<img src="../../media/gif/PieNav Demo.gif" alt="drawing" align="center" width="800"/><br><br>


The Pie Menu is a inspired by Maya's marking menu and Blender's pie menu, although it differs from both of them.

Pie Menu buttons can have an extra widget to the right: sibling, an optionBox or a submenu that pops up when button is focused.

The buttons are automatically selected, so the cursor doesn't need to hover over them to execute their commands.

Pie Menus can be accessed by clicking in a parent button in the Control Panel or by using keyboard shortcuts.

If the key is released without moving the cursor, the menu will stay visible.

If the cursor is slightly moved away from the center to the edge of the circle, the menu will close without executing a command.

The menus can consist of two layers, an inner and outer shell where each button can have a submenu, and fixed boxes which can be placed to custom locations.

### <b>How buttons autofocus works:</b>

>There is an invisible circular boundary between the inner and the outer buttons in the menu. If no modifier key is pressed and the cursor crosses the boundary, the outer shell will become focused.<br>
>Alternatively, if the cursor is inside the boundary and the Alt modifier key is pressed, the outer shell will become focused.

>If the Shift modifier key is pressed, the menu will only focus on the button to the right of the primary one, whether it's a sibling or an optionBox.<br>
>The Shift modifier key takes into account whether the Alt modifier key is also pressed or if the shell boundary is crossed.

>Menus can contain empty spaces instead of buttons. When an empty space is encountered, the menu will automatically focus on the nearest button on the circle.

>The menu itself is an invisible window. When the cursor moves far away enough from the origin point, the menu will disengage its autofocus.<br>
>If the menu is activated with a mouse click and the click is not released after activation, it will continue to autofocus even after leaving the borders of the window.

## Usage

The pie menus you create will be displayed in the corresponding section of the plugin settings. There, you can assign a hotkey to a pie menu, enabling you to call it with a hotkey from the control panel.<br>
Alternatively, you can obtain the code that activates a specific menu, allowing you to call the menu using Maya's native hotkeys or even from the shelf.<br>
Here's an example of how to call a menu using Python:

    streamflow_fn_.module.RadialMenuWindow.call_pie_menu('Add_Objects_Pie_Menu')

To call a specific menu, `Add_Objects_Pie_Menu` in the code above should be replaced with the name of the new menu. All the names of the existing pie menus can be viewed in the plugin settings in the pie menu section.


<br>

--- 
## Notable pre-built Pie Menus:

### [Selection Tools Pie Menu](./built_in_pie_menus/selection_tools_piemenu.md)
### [Geometry Tools Pie Menu](./built_in_pie_menus/geometry_tools_piemenu.md)
### [Primitives At Selection Pie Menu](./built_in_pie_menus/primitives_at_selection_piemenu.md)
### [Adjust Pivot Pie Menu](./built_in_pie_menus/adjust_pivot_pie_menu.md)


<br>
<br>

<a href="../../v_01_01_00_README.md#pie-menus">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>