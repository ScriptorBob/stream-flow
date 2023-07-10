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


<br>

--- 
## Peculiar Pie Menus:

###  <b>1. Pie Menu -Central Menu Right Click</b>
  
  >This Menu is accessible through the Control Panel, with Right Click on the red button at the center. Since version `01.01`, it can set to be called through hotkeys.<br>

  >Most of the tools within work with multi mesh selection.<br>
  
  > <span style="color: yellow;">Note : </span><br>
  > * All of the tools created in Python or Mel, and are performing slower then the built in Maya tools.<br>
  >  For Meshes with high polyCount, it will perform noticeably slower - for example, extract selection will take 7-8 seconds for a mesh of 160 000 polygons, vs 1-1.5 seconds for a regular Extract.<br>
  > Merge Objects will not be so highly affected. <br>
  
  These are some of the tools that need introduction:

  * Tools Duplicate, Merge, Extract:<br><br>
  <img src="../../media/gif/Tool-Duplicate_Merge_Extract.gif" alt="drawing" align="center" width="1200"/><br><br>

    ><b>Duplicate:</b> Creates a Duplicate of Meshes, or selected components. Note: components must not be faces.

    ><b>Chip Off:</b> Duplicates selected Meshes, or components, but keeps them inside the mesh.

    ><b>Merge: </b> Combines Multiple Meshes and parents them to the transform of the last selected Mesh. This transform remains intact, and any connections it may have are preserved.

    ><b>Extract Selection - Split Mesh: </b> This is a context button.<br>
    >  * In <b>Object Mode: </b>Performs  a regular split mesh.
    >  * In <b>Component Mode: </b>it will split the selection into a new Mesh. add a tail "_Pt_01" to its name, and place it below the original mesh.<br>

    <br>

    ><span style="color: yellow;">Note : </span> <br>
    > * <b>Merge</b> function sometimes locks the Mesh normals. Perform Unlock Normals in Mesh Display menu to fix this.
                
<br>

  * Tool-Smart Connect: <br>
    Smart Connect is context sensitive. It does different things for Face, Edge, and Vertex selection:
    * Connect Faces: <br><br>
      <img src="../../media/gif/Tool-Smart Connect - Faces.gif" alt="drawing" align="center" width="800"/><br><br>
        In Face Mode, SmartConnect performs connect components, and selects one random half of the original faces.

        <br>
      <hr>
      
    * Connect Edges: <br><br>
      <img src="../../media/gif/Tool-Smart Connect - Edges.gif" alt="drawing" align="center" width="800"/><br><br>
      In Edge Mode, SmartConnect does different things, in different circumstances:
       * If one Edge is selected, it bridges the two neighboring Edges that lie on the Mesh Border, and selects the newly created one
       * If two neighboring Edges are selected, It performs polyAppend on the two Edges.
       * If two edges are selected, and they are not neighbors, it performs a simple bridge.
       * If more then two are selected, performs bridge on all of them.
  <br><br>
      <hr>
    * Connect Vertex: <br><br>
    <img src="../../media/gif/Tool-Smart Connect - Vertex.gif" alt="drawing" align="center" width="800"/><br><br>
    Same as with Edge Mode, does different things depending on the selection:
      > If one Vertex is selected, and no other is Highlighted, it will perform PolyCloseBorder if that Vertex is on the Border
      
      > If two Vertex are selected, or one Vertex and another is Highlighted:

      > If Vertex are neighbors: polyConnectComponents.

      > If they are not neighbors: MultiCut.

      > If both Vertex are on Border: Fill hole, then polyConnectComponents, or MultiCut.

      > If more then two Vertex are selected:
        > * If the Verts are on the same face, it will connect every Vertex with the last one.
        > * If they are not neighbors, it will connect every Vertex with the Next one in Selection.<br>

      <br>

      ><span style="color: yellow;">Notes :</span>
      > * When connecting two Vertex, and they both lay on a Border and are not neighbors, the tool will always perform PolyCloseBorder before connecting. You may not want that.
      > * When connecting Vertex that are not neighbors, the tool performs MultiCut between them:
      >    * It is not accurate, as that is the intrinsic property of the MultiCut Tool.<br>
      >    * When using the Tool in this fashion, make sure that you are close enough in the viewport and all of the Vertex are visible on the screen. Use it like you would use the MultiCut Tool.<br> 
      >
      >
      >     * Currently, this part of the Tool works only on Windows OS.


        <br>
  
    ---
  * Tools-InsertEdgeLoop++ and Add Divisions++: <br><br>
    <img src="../../media/gif/Tool-Insert_Edge_Loop__Add_Divisions.gif" alt="drawing" align="center" width="800"/><br><br>
    Both of these buttons work in similar fashion. Wheel Up or Down will change the number of subdivisions. Click applies the set divisions.<br>
    Add Divisions Button is context sensitive:
    * In Edge Mode, it will add subdivisions to the selected Edges.
    * In all other modes, it will perform polySubdivideFacet according to the multiplier displayed on the button.

    <br>

    ---
* Tool-Edit multiple Edge Loops: <br><br>
    <img src="../../media/gif/Tool-Edit Edge Flow.gif" alt="drawing" align="center" width="800"/><br><br>
    This tool edits multiple edge loops, without jumbling the topology.
    Can be performed with button click, but also with Wheel Up. Wheel down just performs undo on the action, stopping when undo queue reaches some other command.

    <span style="color: yellow;">Note :</span> Wheel down,  the undo, can sometimes misbehave and not perform the action. Most likely to happen when in Isolate Selection mode.

    <br>

    ---
* Tool-Equalize edge loops: <br><br>
    <img src="../../media/gif/Tool-Equalize edge lenght.gif" alt="drawing" align="center" width="800"/><br><br>

    <br>

    ---
* Tools-Straighten Edge Loops, straighten Vertex: <br><br>
    <img src="../../media/gif/Tool-Straighten edge,vert.gif" alt="drawing" align="center" width="800"/><br><br>
This button straightens selected Edge loops, by finding the end points for each edge and scaling down from there. <br>
The button to the right straightens vertices. It will straighten everything according to the first and the last vertex. <br>
<span style="color: yellow;">Note :</span> Works with transform constrains enabled - Edge and Surface Constraints.
    <br>

    ---
###  <b>2. Pie Menu - Create Primitives At Selection</b>
<br>
  <img src="../../media/gif/New Object Demo.gif" alt="drawing" align="center" width="800"/>
<br>
<br>


<br>
<br>

<a href="../../README.md#pie-menus">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>
