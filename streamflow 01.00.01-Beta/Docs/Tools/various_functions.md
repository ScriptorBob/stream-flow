
# Extras

### This project started as a series of short scripts for hotkeys. Some functions are still best used like that. Here is a list of most of them:<br><br>
```python
    streamflow_fn_.module.P_SlideEdge_Absolute() #Python  
    streamflow_fn_.module.P_SlideEdge_Relative() #Python
```
  > These two functions activate the Maya's slide edge tool, with relative or absolute mode enabled.
---
    wireFrameOnShaded()   #MEL

  > Toggles WireFrame on shaded 
---
    WireFrameGlobal_TGL()  #MEL

  > Toggle Wireframe on selected
---
    Detach_Cut_UV()  #MEL

  > Detaches Geometry by Edge in viewport, Detaches UV in uv editor
---
    custom_deleteHistory()  #MEL

  > Deletes history of selection, even if selected mesh is in component mode, or just hilighted.<br>
  >Works with multiple Objects selected.

---
    AddLatticeToObject()  #MEL

  >Adds a Lattice to the selection - Mesh or Components, and sets the context to Lattice Point edit.<br>
  >The Lattice is invisible in the Outliner, has 2x2x2 divisions.<br>
  >This is intended for a Mesh hot fix, where you need to do a tweak and delete the history.
---
    ConvertToObject()   #MEL
    ConvertToVertex()   #MEL
    ConvertToEdge()     #MEL
    ConvertToFaces()    #MEL
  >Converts selection to Object Mode or some component mode. Safe and free of misclicks.<br>
  >ConvertToVertex will go into "lattice point" or "curve point" mode
 if that's what is selected.
---
    RotateStuff("X")  #MEL
    RotateStuff("Y")  #MEL
    RotateStuff("Z")  #MEL

  >Rotates mesh by its pivot on a given axis.
  >Rotates component selection taking the manipulator position as the center.<br>
  >RotateStuff("X") and RotateStuff("Y") will rotate the UV clockwise or counterclockwise when in UV Edtitor.<br>
  >Rotate angle is 45 degrees.
---    
    flipMesh_or_UV("X")  #MEL
    flipMesh_or_UV("Y")  #MEL
    flipMesh_or_UV("Z")  #MEL

  >Same as RotateStuff() above, but flip the Mesh or UV for the given axis.<br>

---




---
    streamflow_fn_.module.CursorOrientation.Toggle()  #Python

  >Toggles The cursor orientation on Move, Rotate and Scale tools to: World, Object, Component modes.
---
    streamflow_fn_.module.Windows_MNGR.toggle_Editors()  #Python

  >Toggles AttributeEditor or ChannelBox.<br>
  >If those are detached, places each to the right in the viewport, and rescales the window's heigh to fit the Viewport.
---
    streamflow_fn_.module.Windows_MNGR.toggleOutliner()  #Python

  > Toggles the Outliner.<br>
    If the Outliner is detached, it places it to the left in the Viewport and rescales the window's heigh to fit the Viewport.<br>
  > This action is aware if PolyCount is turned on or off, and rescales the Outliner appropriately.
  
---
     streamflow_fn_.module.isolate_things()  #Python

  > Isolates Selection in Viewport or UV selection in the UV Editor,
    Makes selected node solo in Hypershade.
---
    streamflow_fn_.module.toggle_ortho()  #Python

  > Makes the current camera ortho and snapped to the nearest plane, or the opposite.<br>

---
    streamflow_fn_.module.Windows_MNGR.min_Maximize()  #Python

  > Minimizes or Maximizes any floating window of Maya.
  > If performed when mouse over the Viewport, toggles FullScreen mode.
---
    streamflow_fn_.module.toggle_Default_Mat()  #Python

  > Toggles the displaying of the  default material (lambert) on the active panel.
---
    TGL_Objects_Materials()  #MEL

  > Toggles the selection between objects, and their materials.
  
<br>
<br>

<a href="../../README.md#various-functions">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>