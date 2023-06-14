# Reload Mesh
<br>
<img src="../../media/img/reloadMesh.png" alt="image" align="center" width="1200"/><br><br>

When modeling a mesh for a longer time, Maya tends to accumulate unnecessary data along the way.<br>
This 'history' will not get deleted with the deleteHistory command, and neither mesh cleanup can fix it.<br>
This extra data gets saved when the scene is saved, so it is not removed even then.<br>
Some of the things using this kind of mesh can have these consequences:
* The time rendering such object can be even x4 times slower then if a clean mesh was used.<br>
* Can lead to frequent scene crashes at render time.<br>
* Can slow down the responsiveness of a rigged mesh, so that the animation process is slow and difficult.<br>
* Maya can falsely detect non-manifold uv or geometry where there is none.<br>
* Various Maya Tools can become unresponsive to the mesh, such as the multicut tool.<br>

One solution for this problem is to export the mesh as obj, and reimport it back into the scene.<br>
Another is to rebuild the mesh with raw data using OpenMaya.<br>
Both of these solutions are implemented in version `01.01` and above, and each has it's advantages and drawbacks.

When a whole scene is cleaned in this manner, the resulting scene file size can sometimes get reduced by one third(150MB to  100MB). This is the amount of unneeded and sometimes obtrusive data Maya keeps.

## .Obj way:
---
This function exports, re-imports, and replaces the old mesh with the new one, preserving it's name and position in Outliner.<br>

* It uses the Maya's native .obj exporter, and which streamlines the data to the disk, and can clean even monstrously big meshes.<br>

* It is not Undoable, because importing in Maya is also not Undoable.

* It reads and writes to the disk, for every mesh selected, one by one. Writing data to the SSD is damaging in the long run, if done in large numbers (modern SSDs have 3,000 to 100, 000 write cycles per memory block).<br>
That is the reason why it has customizable import-export link, found in the Settings, named "Mesh Reloader".
* It is more tested. This function has been in use for more than five years without issues.

## OpenMaya way:
---
This function reads the data from the mesh, creates a new one using the Maya Api, and replaces the old one with it.

* About x40 times faster then the `.obj` way, which itself is relatively fast.
* Semi-Undoable. Undoing this action will not result in an error like with the previous function, but the newly created meshes will not be registered in the Undo stack. It will undo the old objects deletion, which will result with duplicate overlapping meshes.
* It reads all of the data and holds them into the memory in order to recreate the new object. This means that it needs more memory to operate, which can be a problem if the polyCount is in the millions. However, it is not damaging to the SSD.

---



<span style="color: yellow;">Notes :</span><br>

* Since version `01.01`, there is a checkmark in the plugin settings that signifies wether to use  the old or the new importer (old is the `.obj`).
* Doing this to a mesh will set its normals to soft, will not preserve color sets, extra uv sets, keyframes, or other connections. Only the basic geometry will be preserved, with the UVs from the object's current uv set, and it's material.
  
* Both methods Will now work if the material has no surface shader, and if the surface shader is unknown node.

<br>
<br>
The python commands for this are:

```python
streamflow_fn_.module.tool_vault.GeomActions.reload_selection() #This will calls one of the functions below based on the state of the checkmark in settings.
streamflow_fn_.module.tool_vault.GeomActions._reload_meshes_obj() # Reload using .obj export and import
streamflow_fn_.module.tool_vault.GeomActions._reload_meshes_internal() # reload using Maya Api
```
<br>
<br>



<a href="../../README.md#snap-camera">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>