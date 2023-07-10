# Circular Shelf
<br>
<img src="../../media/gif/Circular Shelf demo.gif" alt="drawing" align="center" width="800"/><br><br>


This Window holds copies of all of the buttons present in the Maya Shelves. It can be enabled in [Settings](./settings.md#).<br>
The first time the plugin is called with the Circular Shelf enabled, it will get the state of the shelf buttons and write it to disk. Every next time it will read from the disk.<br>
The shelves have click and double click. Double click is replaced by right click.<br>
In the middle of the window there is a red button that pops up a Pie Menu with which you can navigate between the radial shelves.<br>
The shelves can also be navigated through by the default hotkeys "A" and "D" - the same that controls The Disc in the primary Window.<br>
It is show to the screen by demand, and contains all of the buttons the original Maya Shelf has. The Maya Shelf can be turned off to conserve screen space.<br>
It is easily navigable, once used to it.<br>
The shelfButtons don't update automatically with changes in the shelves. To update changes, click the `Save Current Shelf Buttons as Default` button in `Settings`. It will save the shelfButtons as default buttons for future use.<br>


Known issues and workaround: 
  *  Takes some time to load, adds 2-3 seconds of load and reload time to the plugin.
  *  Can cause an error at Maya startup if it is trying to read all of the shelf data before they are created. This will result in the plugin not loading, and can be resolved by calling the `reload command`.<br>
    It is disabled by default because of this circumstance. <br>
    Solution : If you enable the shelf in `settings`, and `reload` the plugin afterwards, It will write the shelf data to a file, and this will no longer be an issue.

<br>
<br>



<a href="../../README.md#circular-shelf">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>