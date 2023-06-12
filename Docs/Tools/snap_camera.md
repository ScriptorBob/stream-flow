
# Snap Camera
<br>
<img src="../../media/gif/Camera Snap Demo.gif" alt="drawing" align="center" width="1200"/><br><br>


Snap Camera is available in [Shortcuts](), and on The Disk.
When activating it from The Disc, it will perform the toggle, and spawn a duplicate of the button from The Disk right under the mouse.<br>
When making a camera ortho, it will maintain its position and have the same view as before, not obscured by any object behind its back.<br>

This button will self-hide when the cursor leaves its area, and has slightly different commands:
  * It takes two wheel strokes to get to do the toggle.
  * The intermittent stroke snaps the camera to the nearest View Plane, but does not make it orthographic. This is useful when the active camera needs to be cleared of rotation transforms.
<br>
<br>

the python commands for this are:

```python
streamflow_fn_.module.toggle_ortho() # to toggle between current position and snapped ortho
streamflow_fn_.module.camera_snap_to_orto_restore_tgl(1) # if camera not ortho, nor snapped to a view, snap, if snapped, make ortho
streamflow_fn_.module.camera_snap_to_orto_restore_tgl(0) # of ortho, restore to snapped, if snapped, restore to original position
```
<br>
<br>



<a href="[../../README.md#snap-camera](https://github.com/ScriptorBob/stream-flow#snap-camera)">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="30">
</a>  <a href="https://github.com/ScriptorBob/stream-flow#snap-camera"> Back </a> 