# StreamFlow - Plugin for Autodesk Maya


## This repo contains only the description and manual! <br>
## Download [Here](https://3dbob.gumroad.com/l/spxrq). <br>

## The forementioned link is the only place where the plug-in is published. Downloading the files from another place might expose you to malicious and harmful code.

<br>
<br>

<div style="display: flex; flex-direction: row;">
<img src="./media/img/Main_UI.png" alt="drawing" width="600"/>
<img src="./media/img/Pie_Menu_Example_02.png" alt="drawing" width="600"/>
</div>


# Table of contents:
* [Description](#about)
* [Features](#features)
* [Tools](#tools)
* [Installation Guide](#installation-guide)
* [Reporting bugs and asking questions](#reporting-bugs-and-asking-questions)
* [Terms and Conditions](#terms-and-conditions)

<br>

# About
The plugin's purpose is to increase the workflow efficiency in Autodesk Maya, enriching the software with numerous features - user friendly UI widgets, tools, and scripts that create new, or extend existing tools.\

Of all the features it offers, most are oriented towards modeling and scene assembly, which is the author's expertise.
However, the UI widgets it brings to Maya can improve the workflow of any type of artist that works with the software.
Much focus has been set of cross-version compatibility, which sadly is not straightforward with many tools, scripts, and plugins.
StreamFlow supports at least 6 versions of Maya, across two major versions of python and PySide2. One of it's design goals is to serve as a hub for other scripts users may have, by providing many ways to save and call functions, and be able to transfer them easily to the next version of Maya.


Tested Maya versions:


| Maya version   |      UI      |  All functionalities |
|----------|:-------------:|------:|
| 2017    |   working     |   not fully tested |
| 2018    |   working     |   Yes |
| 2019    |   working     |   Yes |
| 2020    |   working     |   mostly tested |
| 2022    |   working     |    not fully tested  |
| 2023    |   unknown     |    unknown |


Supported Operating Systems:
  * Windows



<br/>

## Roadmap:
  1. Add cross-platform support
   
  2. Add Customizable pie menus option
   
  4. Create new tools, improve existing ones

  3. Create detailed roadmap.

<br>

# Features:
### [Control Panel](./Docs/UIs/control_panel.md)
### [Pie Menus](./Docs/UIs/pie_menu.md)
### [Extra Popups](./Docs/UIs/extra_popups.md)
### [Circular Shelf](./Docs/UIs/circular_shelf.md)
### [Hotkeys](./Docs/Tools/hotkeys.md)
### [Settings](./Docs/UIs/settings.md)
<br>


# Tools:
### [Snap Camera](./Docs/Tools/snap_camera.md#snap-camera)
### [Reload Mesh](./Docs/Tools/reload_mesh.md#reload-mesh)
### [Various Functions](./Docs/Tools/various_functions.md)
<br>


# Installation Guide
## Windows 
  * <b>Automatic</b>
      1. Extract Contents from the zip folder at some location
   
      2. In the extracted folder,there is a subfolder `INSTALLER_PLAIN`. Run the `installer_plain.exe` from there. It will open a python shell asking for a version you would like the install the plugin to.
  
  * <b>Manual</b>
    1. Extract Contents from the zip folder at some location.
    2. Copy  and edit a file:
       1. From the extracted files, grab `MMGA.py` and place it in the folder:   `\Users\<USER>\Documents\maya\<MayaVersion>\prefs\scripts`
       2. Open "MMGA.py" with a text editor and find the text `def streamflow_fn_(toolPath='Z:/Projects/Maya_Dev/MMGA'):` - should be at line 46
       3. Replace `Z:/Projects/Maya_Dev/MMGA` with the directory path of the extracted content's folder.
<br><br>
   
    1. Edit "userSetup.py"
       1. From the extracted files, open the file "Starter.txt" and copy the text.
       2. Open the file `userSetup.py` from: `\Users\<USER>\Documents\maya\<MayaVersion>\prefs\scripts` 
       3. Paste the content at the end the existing text inside the `userSetup.py`, if there is existing text. If not, just paste.



    * <span style="color: yellow;">Notes :</span>

        `<MayaVersion>` is the version you want to install the plugin to. Can be 2017, 2018, 2019, 2020, 2022. <br>
        `userSetup.py` might not be present inside this folder. If so, create a nex txt folder, and rename it to `userSetup`, and change the extension `.txt` with `.py`

<span style="color: red;">Important: </span>When installed, Maya will continue to use the files directly from where they were extracted. Extract to a meaningful location and do not delete afterwards.
<br><br>


## Reload Guide
### Windows
  
   To reload the whole plugin in session, the following python command needs to be executed:<br>
```python
streamflow_fn_()
```
  To hard reload, one or two files should be deleted from the prefs:

  Even when reinstalled, the plugin will not create default settings if they are already present in the appropriate folder.<br>

  When initiated, the plugin copies its default setting into this folder: `\Users\<USER>\Documents\maya\<MayaVersion>\prefs\MMGA`.

  The files are called `HotkeysData.json` and `SK_Wnd_GeneralSettings.json`. The first one holds only the custom hotkey data. <br>

  When either of these files are deleted, the plugin will create new defaults on startup or on reload.

---
## Uninstallation Guide

#### Windows
  1. Open the file `userSetup.py` from:  `\Users\<USER>\Documents\maya\<MayaVersion>\prefs\scripts`
  2. From this file, Remove the following lines:

          """MMGA IMPORT"""
          import os
          import maya
          import MMGA

          with open(os.path.splitext(MMGA.__file__)[0] + ".py") as fh:
              exec (fh.read())

          maya.cmds.evalDeferred("streamflow_fn_()",lp=1)
          """MMGA IMPORT"""
      Or if no foreign scripts are loaded through this file, delete it completely.<br>
      This will stop the plugin from being loaded on startup.

      Additional Files and folders to delete:
      1. `MMGA.py `from:  `\Users\<USER>\Documents\maya\<MayaVersion>\prefs\scripts\`
      2. `MMGA` folder, from: `\Users\<USER>\Documents\maya\<MayaVersion>\prefs\`
<br><br>

## Installation-tips
### General
* This plug-in gets initiated before maya is fully started, and the errors it might encounter get outputted to the console window, called "Output Window" in Maya. Any error encountered will be printed there.

### Maya 2022+:
* In these versions, Maya is sometimes shipped without pymel, which is a library this plug-in uses and is required in order for it to work.<br>
  [Here](https://knowledge.autodesk.com/support/maya/learn-explore/caas/CloudHelp/cloudhelp/2023/ENU/Maya-Scripting/files/GUID-2AA5EFCE-53B1-46A0-8E43-4CD0B2C72FB4-htm.html) is a guide on how to install it on WindowsOS.

<br><br>



# Reporting bugs and asking questions

## Bugs and questions are handled in [Issues](https://github.com/ScriptorBob/stream-flow/issues). 

### Q: How can I report a bug?

1. Go through the [reported bugs](https://github.com/ScriptorBob/stream-flow/labels/bug) and make sure this bug hasn't already been reported.
2. If you are unable to find the specific bug there, then [report](https://github.com/ScriptorBob/stream-flow/issues/new?labels=bug&template=bug) a new one.
3. If you are new to GitHub issues, make sure you go through [issues quickstart](https://docs.github.com/en/issues/tracking-your-work-with-issues/quickstart) first before opening a new issue.   
4. Add the steps to reproduce the problem and provide as much details as possible.

### Q: How can I ask a question?

1. Go through the [existing questions](https://github.com/ScriptorBob/stream-flow/labels/question) and make sure this question hasn't already been asked.
2. If you are unable to find the specific question there, then [ask](https://github.com/ScriptorBob/stream-flow/issues/new?labels=question&template=question) a new one.  
3. If you are new to GitHub issues, make sure you go through [issues quickstart](https://docs.github.com/en/issues/tracking-your-work-with-issues/quickstart) first before opening a new issue.
4. Provide as much details as possible.
 
<br>

<br>

# Terms and Conditions

By using this software you agree to the following [Terms and Conditions](
https://htmlpreview.github.io/?https://github.com/ScriptorBob/stream-flow/blob/main/TOS.html)
