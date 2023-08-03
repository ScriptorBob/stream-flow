# Changelog

1. New refresh mesh tool, doesn't export or import meshes, uses OpenMaya
2. Added new panel shortcut in the DISK: Attribute Spreadsheet
3. Settings:
    Displays all of the pie menus, and they can have the shortcut removed.
    Cosmetic changes, added the sections to dropdown menus.
4. New Tool: "Curve Tools"
5. Pie Menu Editor Finished
6. Commands executed are now global. For internal commands, must use "streamflow_fn_.module.", or "(streamflow)." prefix.

7. Created Selection Asset tool. Can mark items in outliner as assets, select them, and open a window with selection asset tree.
8. Reworked promptbox, now has buttons with icons, and optionboxes
9. New Tool: Scale Individually
10. New Tool: Move Selection to and from camera




# Issues

* Pie Menu: <br>
    * when "Shift modifier" is pressed, if the angle of the mouse doesn't directly match the button, it's extra_widget will not be focused
    * Pressing shift while distance is greater then inner shell changes the indicator radius to internal

* Duplicate Mesh:
    
    * Naming issue when duplicating group, possibly due to namespace.
    * Duplicating a mesh with "_01" at the end will not rename it to "_02", instead it will rename it to "_01_01"

* Quick Menu:
  
    * Quick Menu widgets can't be scrolled with mouse click, fix focus out event in parent QLabel

* Pie Menu Editor:
  
    * Fix absolute paths display and data storing. <br>
    * Fix default icon on newly created sibling button.

* Circular Shelf
  * Item 0 in the widget is not focused when the angle goes right below 0 

# Dev Notes

1. Fixed rare bug in `rectangulate UV` where the script won't recognize mesh islands properly.
2. Fixed bug in `Selection.get_component_type` where empty list made errors.
3. Fixed bug in `collapsible menu` where if you add text without remove button it moves the text in the center.
4. Added function: create switch node # WIP
5. Implemented new workflow for icons.
6. `AssignFirstShdToOBjects()#mel` - fixed selection invert.
7. Fixed bug in getViewPlane where objectName in some object is str for some reason.
8. Pie Menu:
   * Fixed bug where submenu items wouldn't have option_box or sibling.
   * Primary item in submenu now expanding to fit leftover space.
   * Placing extra_boxes with coordinates - now accepts "Top", "Bottom", "Left", "Right" as pre-build positions, as well as custom coordinates.


9. General tool window class created,tracks every window that is created, and shuts down on plugin reload.


10. Fixed bug in quick import and export : There was an unaccounted value in export parameters.
    


<br>
<br>



<a href="../v_01_01_00_README.md#changelog">
    <img src="../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>


