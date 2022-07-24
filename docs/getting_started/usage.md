# Usage

This manual is going to guide you through the main mod's features and provide a short guide on how to use them.

If you try to find quick links to all settings on the right sidebar.

![main window](../img/main.png)

---

## Basic Controls

|         Keyboard | Action                                                        |
| ---------------: | ------------------------------------------------------------- |
|    <kbd>F4</kbd> | bring up the KiNO menu                                        |
|    <kbd>F3</kbd> | toggle cinematic camera                                       |
| <kbd>PG UP</kbd> | toggle hazard lights                                          |
| <kbd>PG DN</kbd> | toggle headlights                                             |
|    <kbd>F1</kbd> | toggle noclip/flymod (only works in modded/corrupted lobbies) |

???+ info "Noclip/Flymod Controls"
    Controlls are <kbd>W</kbd> <kbd>A</kbd> <kbd>S</kbd> <kbd>D</kbd> / <kbd>Q</kbd> <kbd>E</kbd> keys.

    Speed can be adjusted in [settings](getting_started/usage.md#keybinds)

---

## Supporter **only** features

We have some features reserved for our supporters as an appreciation for their support to make this mod possible.

### <img src="../img/icons/extras.png" style="height: 1.4rem" alt="Events Icon"/> Extras

In this module you can create a custom **name tag** that can be shown before or after your nickname.

You can also set up the colors for your tag, as well as your Steam nickname using a solid color, gradient or by coloring each letter separately.

You are also able to save up to 3 presets for your name.

![extras_tut](../img/extras.png)

### <img src="../img/icons/engine_swap.png" style="height: 1.4rem" alt="Swaps Icon" /> Swaps

In this tab you can swap the engine of the car and adjust the engine settings on the track.

![swaps_tut](../img/swaps.png)

### <img src="../img/icons/air.png" style="height: 1.4rem" alt="Air Icon" /> Air suspension

This feature is limited to our ==2nd Tier supporters== ^^only^^!

It allows you to control the suspension height, switch between air and hydraulics modes, save up to 3 presets for the air suspension and set up [keybinds](#keybinds) for a more convenient use.

The first time you open the module you will be greeted with a tutorial containing some information on how to use the features.

![air](../img/air.png)

### Extra player options

As a supporter, you also get additional options in the [players menu](#players).

<kbd>C</kbd> button disables selected player's collision.  
<kbd>H</kbd> button allows you to hide players.

See the [player menu section](#players) for more details.

---

## Normal Features

### <img src="../img/icons/headlights.png" style="height: 1.4rem" alt="Lights Icon" /> Lights

!!! info inline end "Pop-up headlights don't work on AE86 due to the model having issues."

In this tab you can adjust settings of your headlights such as horizontal angle (affects vertical as well), brightness and the colors of the beam.

Also you have an option for daylight running lights which hide the beams and toggle pop-ups in **fully open** and **sleepy** modes.

![lights_tut](../img/lights_settings.png)

### <img src="../img/icons/hazards.png" style="height: 1.4rem" alt="Hazards Icon" /> Hazards

Here you can set up your hazard lights. Settings allow you to change their blinking interval and adjust positions to fit your bodykit.
![hazards_tut](../img/hazards.png)

### <img src="../img/icons/neons.png" style="height: 1.4rem" alt="Neon Icon" /> Neon

Color settings, brightness and lighting mode for your underglow.
![neon_tut](../img/neon.png)

### <img src="../img/icons/license_plates.png" style="height: 1.4rem" alt="Plates Icon" /> License plates

In license plates settings you can add plates for front and rear of the car, adjust their positions, change the format and put your own text on it.
![plates_tut](../img/license_plates.png)

### <img src="../img/icons/weather.png" style="height: 1.4rem" alt="Graphics Icon" /> Graphics

In the graphics tab you can adjust in-game lighting, enable the fog and use custom skyboxes.

General settings enable you to toggle `HD shadows` and `Realtime reflections`.  
Realtime reflections have 2 quality options: **Low** only relfects skybox and the map while **Medium** reflects cars and shadows as well.

![graphics_general](../img/graphics_general.png)

![graphics_sun](../img/graphics_sun.png)

![graphics_sky](../img/graphics_sky.png)

To load your own skyboxes you need to have them in the following formats:

![skybox_tut](../img/tut_skyboxes.png)

![graphics_fog](../img/graphics_fog.png)

!!! example "For cubemaps"
nx = +x  
 ny = -y  
 nz = -z  
 px = +x  
 py = +y  
 pz = +z

`.png` and `.jpg` ^^only^^

All the face images should be inside a folder.

!!! example "For panoramas:"
Panoramas can be used in `.png` and `.jpg` formats. You can convert HDR and EXR skyboxes to .png or .jpg to use them with the mod.

Skyboxes are installed into the following folder:

```
CarX Drift Racing Online\BepInEx\plugins\KN_Base\sky
```

### <img src="../img/icons/players.png" style="height: 1.4rem" alt="Player Icon" /> Players

In the **players** tab you can teleport to a selected player by clicking on their name in the list.  
<kbd>S</kbd> button next to a players name allows you to check the selected players specs.

!!! info "Supporter only"
<kbd>C</kbd> button disables selected player's collision.  
 <kbd>H</kbd> button allows you to hide players.

    These two buttons, as mentioned in [Supporter only features](#extra-player-options), are only available for supporters!

![players_tut](../img/players.png)

### <img src="../img/icons/collisions.png" style="height: 1.4rem" alt="Collisions Icon" /> Collision manager

In the collision manager you can disable collisions for console players or hide them completely.
Per player collisions can be manged from the [players](#players) tab <small>(if you are a supporter)</small>.

![collisions_tut](../img/collision_manager.png)

### <img src="../img/icons/tuning.png" style="height: 1.4rem" alt="Tunes Icon" /> Tune

From here you can save and load your tunes, as well as enable suspension monitor to see live values for your camber and enable custom backfire.

The saved tunes can be found inside the **tunes** folder.
It can be found at:

```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\visuals
```

To use a downloaded tune put it in this folder as well.
![tunes_tut](../img/tuning.png)

### <img src="../img/icons/maps.png" style="height: 1.4rem" alt="Maps Icon" /> Maps

KiNO features a custom maploader that allows you to load the maps in the .obj format.  
![maps](../img/maps.png)
Downloaded maps should be installed into:

```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\maps
```

To instal the map you need to put the folder containing the .obj file in the aformentioned folder. No .zip or .rar files.  
If you wish to create your own maps, refer to the [this guide](Map%20Conversion.md).

### <img src="../img/icons/waypoints.png" style="height: 1.4rem" alt="Waypoints Icon" /> Waypoints

This feature allows you to save multiple points on the map that you can quickly teleport to. Every native map already has some preset waypoints.  
![waypoints](../img/waypoints.png)

### <img src="../img/icons/car_swap.png" style="height: 1.4rem" alt="Change Car Icon" /> Change car

Change car feature allows you to switch your car on the track (works only in multiplayer). You can bind a shortcut button for it in the [keybinds](#keybinds) tab of the mod.

### <img src="../img/icons/cinematic.png" style="height: 1.4rem" alt="Cinematic Icon" /> Cinematic

Select players you want to record from the list and click on the record button to record a replay. Click on the stop button to save your replay once you're done.
![cinematic_tut](../img/cinematic_1.png)  
From the playback tab you can load your replays and focus on cars from the replay by choosing a ghost from the list and pressing F3.

You replays are saved to:

```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\replays
```

![cinematic_tut](../img/cinematic_2.png)  
On the timeline you can set the starting and ending point of your replay by dragging arrows at the start and the end of the timeline. You can also adjust the playback speed and loop your replay.
![timeline](../img/timeline.png)

### <img src="../img/icons/custom_camera.png" style="height: 1.4rem" alt="Custom Camera Icon" /> Custom Camera

The feature allows to adjust different camera parameters for the 3rd person cameras. The mod automatically forces dynamic camera setting for the better look. You can save and load custom camera presets from the file.

```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\cameras
```

Or save up to 3 presets inside the menu for quick application.

![custom_camera](../img/custom_camera.png)

Camera shake can also be turned on and off and adjusted to your taste.
![custom_camera_shake](../img/custom_camera_shake.png)

### <img src="../img/icons/custom_hud.png" style="height: 1.4rem" alt="Custom HUD Icon" /> Custom HUD

Currently only allows you to enable simplified tachometer that only works with in-game UI hidden (F11 by default.)
![hud_tut](../img/custom_hud.png)

### <img src="../img/icons/visuals.png" style="height: 1.4rem" alt="Visuals Icon" /> Visuals

In the visuals tab you can load and save your liveries. Additionally you have some additional features to help you with livery creation such as camera zoom and offset along with the ability to enable and disable symmetry for all the layers at once as well as change their material.

The saved liveries can be found inside the **visuals** folder.  
It can be found at:

```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\visuals
```

To use a downloaded livery put it in this folder as well.
![visuals_tut](../img/visuals.png)

### <img src="../img/icons/noclip.png" style="height: 1.4rem" alt="Noclip Icon" /> Noclip settings

In the noclip settings you can change the speed and the speed multiplier.  
Default keybinds:  
`F1` to activate noclip.  
`Left Shift` to speed up (uses speed multiplier setting).  
`Home` to freeze your car in place.  
`End` to unfreeze the car.
![noclip_tut](../img/noclip.png)
**Noclip only works in singleplayer and modded lobbies (with _CORRUPTED_ tag).**

### <img src="../img/icons/settings.png" style="height: 1.4rem" alt="Settings Icon" /> Settings

In the gui settings you can change the mod language, color theme, enable window dragging or change the scale of the mod's window.
![settings_gui](../img/settings_gui.png)  
From the modules tab you can enable and disable some of the mod's features.
![settings_modules](../img/settings_modules.png)  
In the game settings you have some _quality of life_ features as well as toggles for synchronization of different mod features between KiNO users (on by defaul).
![settings_game](../img/settings_game.png)

### <img src="../img/icons/keybind.png" style="height: 1.4rem" alt="Keybinds Icon" /> Keybinds

Here you can bind shortcuts for some of the mod's features. Controller is supported, however some buttons can not be binded due to certain limitations.
![keybinds_tut](../img/keybinds.png)

### <img src="../img/icons/resource_manager.png" style="height: 1.4rem" alt="Resource Manager Icon" /> Resource manager

For some of the mod's features you might have to download an asset bundle containing resouces needed for the feartures to function. In this tab you can download and update the bundle.
![resouce manger_tut](../img/resource_manager.png)
