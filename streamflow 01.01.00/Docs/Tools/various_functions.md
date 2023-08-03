
# Extras

### This project started as a series of short scripts for hotkeys. Some functions are still best used like that. Here is a list of most of them:<br><br>



```python
streamflow_fn_.module.GeneralWindowManager.toggle_editors()  #python
```

This function toggles the Attribute Editor and the Channel Box in a particular fashion:
First the Attribute Editor will be shown, then the Channel Box will be shown while the Attribute Editor is hidden, and then it will hide the Channel Box.
If the editors are detached as a separate windows, it will automatically rescale them to fit the viewport, and place them to the right of the viewport.

This feature was created in order to address the slow toggling of the editors when they are attached to the viewport, because the viewport is constantly being resized. This function allows for them to behave as if they are attached to the right part of the viewport, but the toggling can be done fast, and it doesn't affect the scaling of the viewport.

```python
streamflow_fn_.module.GeneralWindowManager.toggle_outliner()  #python
```
This function toggles the Outliner, and if it is detached, it will place it to the left of the viewport. It will automatically rescale the Outliner window if poly count info is turned on.

<br><br>

---


```python
streamflow_fn_.module.GeneralUtilities.poly_slide_edge_absolute() #python
streamflow_fn_.module.GeneralUtilities.poly_slide_edge_relative() #python
```

These two functions activate the Maya's slide edge tool, with relative or absolute mode enabled.

<br><br>

---


```python
streamflow_fn_.module.Transform.move_sel_to_from_camera(1)    #Python
```

This function moves the selection closer of further to the camera depending on the value you provide in it.<br>
When in object mode, all of the transforms of the parent need to be frozen in order for the tool to work properly.<br>
It works correctly in component mode regardless of the state of the parent transforms.


<br><br>

---

```python
streamflow_fn_.module.GeomActions.do_duplicate() #python
```

Duplicates the selection, renames the pieces, and places them just under the original ones.

<br><br>

---

```MEL
wireFrameOnShaded //MEL
```
Toggles WireFrame on shaded.

<br><br>

---

```python
streamflow_fn_.module.GeneralUtilities.toggle_global_wireframe() #python
```

Toggle global wireframe overlay.

<br><br>

---

```python
streamflow_fn_.module.SfCamera.toggle_camera_lock()
```

Locls/Unlocks the currently active camera 

<br> <br>

---


```MEL
Detach_Cut_UV()  //MEL
```
Detaches Geometry by Edge in viewport, Detaches UV in uv editor

<br><br>

---

```MEL
custom_deleteHistory()  //MEL
```

Deletes history of selection, even if selected mesh is in component mode, or just highlighted.<br>
Works with multiple Objects selected.

<br><br>

---

```MEL
AddLatticeToObject()  //MEL
```
Adds a Lattice to the selection - Mesh or Components, and sets the context to Lattice Point edit.<br>
The Lattice is invisible in the Outliner, has 2x2x2 divisions.<br>
This is intended for a Mesh hot fix, where you need to do a tweak and delete the history.


<br><br>

---

```MEL
ConvertToObject()   //MEL
ConvertToEdge()     //MEL
ConvertToFaces()    //MEL
```
```python
streamflow_fn_.module.Selection.convert_sel_vertex_mode() #python
```

These functions are already mapped in the selection pie menu, but it's worth noticing them here too.
They allow for safe and misclicks free selection conversion .<br>
ConvertToVertex will go into "lattice point" or "curve point" mode if lattice or curve is selected.

<br><br>

---

```MEL
RotateStuff("X")  //MEL
RotateStuff("Y")  //MEL
RotateStuff("Z")  //MEL
```

Rotates mesh by its pivot on a given axis.
Rotates component selection taking the manipulator position as the center.<br>
RotateStuff("X") and RotateStuff("Y") will rotate the UV clockwise or counterclockwise when in UV Edtitor.<br>
Rotate angle is 45 degrees.

<br><br>

---

```MEL
flipMesh_or_UV("X")  //MEL
flipMesh_or_UV("Y")  //MEL
flipMesh_or_UV("Z")  //MEL
```

Same as RotateStuff() above, but flip the Mesh or UV for the given axis.<br>

<br><br>

---

```python
streamflow_fn_.module.CursorOrientation.toggle_context()  #Python
```

Toggles The cursor orientation on Move, Rotate and Scale tools to: World, Object, Component modes.

<br><br>

---

```python
streamflow_fn_.module.GeneralUtilities.isolate_things()  #Python
```

Isolates Selection in Viewport or UV selection in the UV Editor,
Makes selected node solo in Hypershade. The Hypershade part can be buggy, but will not break anything.

<br> <br>

---

```python
streamflow_fn_.module.tool_vault.SfCamera.toggle_ortho()  #Python
```
Makes the current camera ortho and snapped to the nearest plane, or restores the perspective.<br>

<br><br>

---

```python
streamflow_fn_.module.GeneralWindowManager.min_maximize_window_under_pointer()  #Python
```
Minimizes or Maximizes any floating window of Maya.<br>
If activated when mouse is over the Viewport, toggles FullScreen mode.

<br><br>

---
```python
streamflow_fn_.module.GeneralUtilities.toggle_default_material()    #Python
```
Toggles the displaying of the  default material (lambert) on the active panel.

<br><br>

---
```MEL
TGL_Objects_Materials()  //MEL
```

Toggles the selection between objects and their materials.
  
<br>
<br>





---


<a href="../../v_01_01_00_README.md#various-functions">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>