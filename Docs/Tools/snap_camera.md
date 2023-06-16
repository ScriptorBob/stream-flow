
# Snap Camera
<br>
<img src="../../media/gif/Camera Snap Demo.gif" alt="drawing" align="center" width="1200"/><br><br>


Snap Camera is available as a python command, and on mouse wheel stroke on the widget in the center of the Control Panel.
When activating it from The Disc, it will perform the toggle, and spawn a duplicate of the button from The Disk right under the mouse.<br>
When making a camera ortho, it will maintain its position and have the same view as before, not obscured by any object behind its back.<br>

This button will self-hide when the cursor leaves its area, and has slightly different commands:
  * It takes two wheel strokes to get to do the toggle.
  * The intermittent stroke snaps the camera to the nearest View Plane, but does not make it orthographic. This is useful when the active camera needs to be cleared of rotation transforms.
<br>
<br>

The python commands for this are:

```python
streamflow_fn_.module.tool_vault.SfCamera.toggle_ortho(0) # to toggle between current position and snapped ortho
streamflow_fn_.module.tool_vault.SfCamera.cycle_restore_snap_ortho(1) # if camera not ortho, nor snapped to a view, snap, if snapped, make ortho
streamflow_fn_.module.tool_vault.SfCamera.cycle_restore_snap_ortho(0) # of ortho, restore to snapped, if snapped, restore to original position
```
<br>
<br>



<a href="../../README.md#snap-camera">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>