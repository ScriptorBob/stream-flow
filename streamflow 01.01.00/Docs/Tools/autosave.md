# AutoSave
 
StreamFlow Autosave is created to addresses some of the issues the default autosave one has.<br>
It will not clog up disk space so quickly, nor will it spawn  application blocking popup to ask for permission to save.<br>

It has a dedicated pie menu, which is called when clicking on the button in the Autosave section in the control panel.<br>
This pie menu holds functions that allows you to start and stop the countdown, to forcefully perform the autosave, to reset the timer, and to open the autosave folder with the file explorer .


Features:
  * When performing autosave, it will deactivate itself if Maya application is not active. It will automatically activate when Maya application is activated.
  * If Maya application is active, but idle, or no change is made to the scene, it will skip autosave.
  * It will try to save the scene as Maya Ascii. If unable to do so, it will save as Maya Binary.
  * Prompts a non-interrupt popup to the central part of the viewport, notifying that Autosave action is imminent, with the option to cancel it.
  * It will reset the countdown when New Scene is created, or old one Saved.
  
  <br>

  <b>Unexpected Feature:</b>
  * If Maya is stuck in a deep calculation, but not crash frozen, AutoSave is sometimes still able to save the scene.
        <br><br>

  > <span style="color: yellow;">Note : </span>
  > AutoSave has a dedicated section in Settings. There its interval, path, and status can be set. Turning it off will result with the removal of the Autosave UI from the Control Panel.<br><br>
  
<br>
<br>

  <a href="../../v_01_01_00_README.md#custom-autosave">
    <img src="../../media/icons/Arrow_v2_LEFT.png" alt="BackArrow" height="60">
</a>
