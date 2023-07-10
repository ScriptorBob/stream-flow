# Pie Menus
<br>
<img src="../../media/gif/PieNav Demo.gif" alt="drawing" align="center" width="800"/><br><br>


The Pie Menu is a inspired by Maya's marking menu and Blender's pie menu, although it differs from both of them.

Pie Menu buttons can have a sibling right next to them, an optionBox, or a submenu that pops up when button is focused.

The buttons are autofocused, the cursor doesn't need to hover over them in order to execute its command.

The pie menu can be called with a mouse click in the Control Panel, or from keyboard.

If the key is released without moving the cursor, the menu will stay visible.

If the cursor is moved a little from the point of origin to the circle boundary, the menu will close without executing a command.

The menus can have two shells, inner and outer, button submenus, and an fixed boxes.


### <b>How buttons autofocus works:</b>

>There is an invisible circular boundary around the center of the menu. If no modifier is pressed, and the cursor has crossed the boundary, the outer shell will come into focus.
>Alternatively, if the cursor is inside the boundary, and Alt Modifier is pressed, the outer shell will come into focus.

>If Shift Modifier is being pressed, the menu will focus only on the button to the right of the primary one - a sibling or an optionBox.\
>Shift Modifier press takes into consideration if Alt Modifier is also pressed, or if the shell boundary is crossed.

>Menus can have empty spaces instead of buttons. If a space is encountered, the menu will autofocus on the nearest button on the virtual circle.

>The menu itself is an invisible window. When getting enough far away from the origin point, It will disengage its autofocus.\
>When activated with mouse click, and if the click is not released after activation, it will continue to autofocus even after leaving the window's borders.


## Usage
The created pie menus will be displayed in the appropriate section in the plugin settings. There you can bind a hotkey to a pie menu, which will allow you to call the pie menu with a hotkey from the control panel.<br>
Alternatively, you can obtain the code that would activate the particular menu which can allow you to call the menu with the Maya's native hotkeys or even from the shelf.<br>
This is how a menu call looks like in python: <br>

    streamflow_fn_.module.RadialMenuWindow.call_pie_menu('Add_Objects_Pie_Menu')

To call a specific menu, you need to replace the `Add_Objects_Pie_Menu` part with the name of the new menu, which can be viewed in the plugin settings.


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
