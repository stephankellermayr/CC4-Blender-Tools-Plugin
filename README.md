# CC4 Blender Pipeline Tool (Installed in CC4)

**This plugin is for Character Creator 4, for Character Creator 3 [look here](https://github.com/soupday/CC3-Blender-Tools-Plugin)**

This is a python plugin for Character Creator 4 to re-import a character from Blender generated using the **CC4 Blender Pipeline Tool** auto-setup add-on: https://github.com/soupday/cc_blender_tools.

This plugin will re-import the selected character and reconstruct the materials exactly as specified in the character Json data, which is exported with all FbxKey exports to Blender.

The character export from Blender must be generated with the **CC/iC Blender Tools** add-on as the Fbx export must be carefully altered to be compliant with CC4 and having exactly matching Object and Material names with the FbxKey, and also must have all relevent texture paths updated and changes to the material parameters written back to the exported Json data.

It is possible to include additional objects with the character exports from Blender by selecting them along with the character, but they must be parented to the character armature and have an armature modifier with valid vertex weights, otherwise CC4 will ignore them.

Installation
============

### Installer
- Download and run the installer ([Install-CC4BlenderToolsPlugin](https://github.com/soupday/CC4-Blender-Tools-Plugin/releases/download/1_0_6/Install-CC4BlenderToolsPlugin-1.0.6.exe)) from the [release page](https://github.com/soupday/CC4-Blender-Tools-Plugin/releases)

### Manual Installation
- Download the Zip file (__CC4-Blender-Tools-Plugin-main.zip__) from the **Code** button.
- Unzip the zip file. There should be a folder: **CC4-Blender-Tools-Plugin-main**
- Create the folder **OpenPlugin** in the <Character Creator 4 install directory>**\Bin64\OpenPlugin**
    - e.g: **C:\Program Files\Reallusion\Character Creator 4\Bin64\OpenPlugin**
- Copy or move the folder CC4-Blender-Tools-Plugin-main into the **OpenPlugin** folder.
    - e.g: **C:\Program Files\Reallusion\Character Creator 4\Bin64\OpenPlugin\CC4-Blender-Tools-Plugin-main**
- Load the script into the project from the **Plugins > Blender Auto-setup > Import From Blender** menu.

Alternatively the main.py script can run as a standalone script from the **Script > Load Python** menu.

Troubleshooting
===============

If after installing this plugin the plugin menu does not appear in Character Creator:

- Make sure you are using the correct version of the plugin for your version of Character Creator:
    - Character Creator 3: [CC3 Blender Tools Plugin](https://github.com/soupday/CC3-Blender-Tools-Plugin)
    - Character Creator 4: [CC4 Blender Tools Plugin](https://github.com/soupday/CC4-Blender-Tools-Plugin)
- Make sure your version of Character Creator is up to date (at the time of writing):
    - Character Creator 3: Version **3.44.4709.1**
    - Charatcer Creator 4: Version **4.12.1125.1**
- If the plugin still does not appear it may be that the Python API did not installed correctly and you may need to re-install Character Creator from the Reallusion Hub.

Links
=====

[CC/iC Blender Tools](https://github.com/soupday/cc_blender_tools)

[Baking Add-on](https://github.com/soupday/CC3_blender_bake)

## Demo Videos

1st Demo Video: https://youtu.be/gRhbcTSt118
(Mesh editing and material parameters)

2nd Demo Video: https://youtu.be/T4ZU1EmJya0
(Using material nodes to modify textures during export)

3rd Demo Video: https://youtu.be/sr5dWQE6nQ0
(Object Management and Item creation Demo)

Known Issues
============

- By default the FBX export settings have embed textures switched on, but this makes the export incompatible with re-importing the character back into CC4 as the textures are hidden in the original fbx and are not accessible to the file system.
**Always turn off embed textures.**

- Hidden faces information for clothing and accessories is lost upon re-importing into CC4.

Changelog
=========

### 1.1.2
- Export toggle buttons and info labels.

### 1.1.1
- Characterization import for non-standard humanoid characters now working.
- Accessory physics export / import fixed.

### 1.1.0
- Added HIK profile export/import for Humanoid Characters.
- Added Facial profile export/import for Standard and humanoid Characters.
- Added Facial expression Blend shape import for Standard and humanoid Characters.

### 1.0.10
- Fixed long path names causing textures to fail to load.

### 1.0.9
- Physics data reconstruction now includes hair meshes.
- Added export menu option to export with current pose. (For replace mesh and/or accessory editing)

### 1.0.8
- Support for importing props.
- Fix for empty texture paths.

### 1.0.7
- Unlocked import for non-standard characters (Humanoid, Creature, Prop), no longer requires an FBX key.
    - But do still require JSON data from the CC/iC Blender Tools add-on export.
- Fixed Diffuse maps with Alpha channels not applying Opacity channel on import.

### 1.0.6
- SSS and Tessellation data restoration added.
- Physics data restoration added.
- Added Export To Blender menu function.
- Some support for Humanoid imports.
    - Recommended that you Save the HIK profile in the **Modify** > **Characterization** panel first, then reload the profile and activate the Human-IK on re-importing.

### 1.0.5
- Ported to CC4

### 1.0.4
- Fixed AO Maps causing Bump maps to import with zero strength.
- Added Fbx Key check and warning message box.
- Added JSON data check and warning message box.

### 1.0.3
- Fixed error with absolute texture paths on different drives from the FBX file.

### 1.0.2
- First attempt to add automatic export button to CC4. (Didn't work, CC4 API needs updating, disabled for now.)

### 1.0.1
- Progress bars added.
- Fixed Duplicate materials causing Pbr import errors.

### 1.0.0
- First Release.


