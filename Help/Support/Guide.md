# Mod Usage Manual

## This manual is guide you through the main mod's features and provide a short guide on how to use them.

![main window](../../Images/main.png)
## List of mod tabs:

> [Lights](#lights)  

> [Hazards](#hazards)

> [Neon](#neon)

> [License plates](#license-plates)

> [Weather](#weather)

> [Players](#players)

> [Collision manager](#collision-manager)

> [Swaps](#swaps)

> [Tune](#tune)

> [Maps](#maps)

> [Waypoints](#waypoints)

> [Change car](#change-car)

> [Cinematic](#cinematic)

> [Custom HUD](#custom-hud)

> [Visuals](#visuals)

> [Air](#air-suspension)

> [Extras](#extras)

> [Noclip](#noclip-settings)

> [Settings](#settings)

> [Keybinds](#keybinds)

> [Resource manger](#resource-manager)
#
## Extras
![extras](../../Images/icons/extras.png)  
Extras is the module given to kino supporters.  
In the extras tab you can enable your custom nametag as well as select whether it will show in the front or after you nickname. Your tag can be set in the `tag.txt` file located at:  
`../Carx Drift Racing Online/BepInEx/plugins/KN_Base/tag.txt`  
![extras_tut](../../Images/extras.png)  
Here's an example of how the file should look:  
![tag](../../Images/custom_tag.png)

Aside from the nametag Extras include [engine swaps](#swaps).  
And ability to manage player's [collisions](#players).
#
## Lights
![lights](../../Images/icons/headlights.png)  
In this tab you can adjust settings of your headlights such as horizontal angle (affects vertical as well), brightness and the colors of the beam.
![lights_tut](../../Images/lights_settings.png)
#
## Hazards
![Hazards](../../Images/icons/hazards.png)  
Here you can set up your hazard lights. Settings allow you to change their blinking interval and adjust positions to fit your bodykit.
![hazards_tut](../../Images/hazards.png)
#
## Neon
![neon](../../Images/icons/neons.png)  
Color settings, brightness and lighting mode for your underglow.
![neon_tut](../../Images/neon.png)
#
## License plates
![plates](../../Images/icons/license_plates.png)  
In license plates settings you can add plates for front and rear of the car, adjust their positions, change the format and put your own text on it.
![plates_tut](../../Images/license_plates.png)
#
## Weather
![weather](../../Images/icons/weather.png)  
In the weather tab you can adjust in-game lighting, enable the fog and use custom skyboxes.
![weather_tut](../../Images/weather_settings.png)
#
## Players
![player](../../Images/icons/players.png)  
In the **players** tab you can teleport to a selected player by clicking on their name in the list.  
`S` button next to a players name allows you to check the selected players specs.  

**Extras only**  
`H` button allows you to hide players.  
`C` button disables selected player's collision.
![players_tut](../../Images/players.png)
#
## Collision manager
![collisions](../../Images/icons/collisions.png)  
In the collision manager you can disable collisions for console players or hide them completely. Per player collisions can be manged from the [players](#players) tab.
![collisions_tut](../../Images/collision_manager.png)
#
## Swaps
![swaps](../../Images/icons/engine_swap.png)  
**AS OF NOW ENGINE SWAPS ARE ONLY AVAILABLE TO KINO SUPPORTERS**  
In this tab you can swap the engine of the car and adjust the engine settings on the track.
![swaps_tut](../../Images/swaps.png)
#
## Tune
![tunes](../../Images/icons/tuning.png)  
From here you can save and load your tunes, as well as enable suspension monitor to see live values for your camber and enable custom backfire.  

The saved tunes can be found inside the **tunes** folder.
It can be found at: 
```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\visuals
```
To use a downloaded tune put it in this folder as well.
![tunes_tut](../../Images/tuning.png)
#
## Maps
![maps_icon](../../Images/icons/maps.png)  
Kino features a custom maploader that allows you to load the maps in the .obj format.  
![maps](../../Images/maps.png)
Downloaded maps should be installed into:
```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\maps
```
To instal the map you need to put the folder containing the .obj file in the aformentioned folder. No .zip or .rar files.  
If you wish to create your own maps, refer to the [this guide](Map%20Conversion.md).
#
## Waypoints
![waypoints_icon](../../Images/icons/waypoints.png)  
This feature allows you to save multiple points on the map that you can quickly teleport to. Every native map already has some preset waypoints.  
![waypoints](../../Images/waypoints.png)
#
## Change car
![change car](../../Images/icons/car_swap.png)  
Change car feature allows you to switch your car on the track (works only in multiplayer). You can bind a shortcut button for it in the [keybinds](#keybinds) tab of the mod.
#
## Cinematic
![cinematic](../../Images/icons/cinematic.png)  
Select players you want to record from the list and click on the record button to record a replay. Click on the stop button to save your replay once you're done.
![cinematic_tut](../../Images/cinematic_1.png)  
From the playback tab you can load your replays and focus on cars from the replay by choosing a ghost from the list and pressing F3.  

You replays are saved to:
```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\replays
```
![cinematic_tut](../../Images/cinematic_2.png)  
On the timeline you can set the starting and ending point of your replay by dragging arrows at the start and the end of the timeline. You can also adjust the playback speed and loop your replay.
![timeline](../../Images/timeline.png)
#
## Custom HUD
![custom hud](../../Images/icons/custom_hud.png)  
Currently only allows you to enable simplified tachometer that only works with in-game UI hidden (F11 by default.)
![hud_tut](../../Images/custom_hud.png)
#
## Visuals
![visuals](../../Images/icons/visuals.png)  
In the visuals tab you can load and save your liveries. Additionally you have some additional features to help you with livery creation such as camera zoom and offset along with the ability to enable and disable symmetry for all the layers at once as well as change their material.

The saved liveries can be found inside the **visuals** folder.  
It can be found at: 
```
...\CarX Drift Racing Online\BepInEx\plugins\KN_Base\visuals
```
To use a downloaded livery put it in this folder as well.
![visuals_tut](../../Images/visuals.png)
#
## Air suspension
![air_icon](../../Images/icons/air.png)  
A module rewarded as a part of Discord exclusive rewards for 2nd tier Patreon supporters.  

It allows you to control the suspension height, switch between air and hydraulics modes, save up to 3 presets for the air suspension and set up [keybinds](#keybinds) for a more convenient use.

The first time you open the module you will be greeted with a tutorial containing some information on how to use the features. 
![air](../../Images/air.png)
#
## Noclip settings
![noclip](../../Images/icons/noclip.png)  
In the noclip settings you can change the speed and the speed multiplier.  
Default keybinds:  
`F1` to activate noclip.  
`Left Shift` to speed up (uses speed multiplier setting).  
`Home` to freeze your car in place.  
`End` to unfreeze the car.
![noclip_tut](../../Images/noclip.png)
**Noclip only works in singleplayer and modded lobbies (with *CORRUPTED* tag).**
#
## Settings
![settings](../../Images/icons/settings.png)  
In the gui settings you can change the mod language, color theme, enable window dragging or change the scale of the mod's window.
![settings_gui](../../Images/settings_gui.png)  
From the modules tab you can enable and disable some of the mod's features.
![settings_modules](../../Images/settings_modules.png)  
In the game settings you have some *quality of life* features as well as toggles for synchronization of different mod features between kino users (on by defaul).
![settings_game](../../Images/settings_game.png)
#
## Keybinds
![keybinds](../../Images/icons/keybind.png)  
Here you can bind shortcuts for some of the mod's features. Controller is supported, however some buttons can not be binded due to certain limitations.
![keybinds_tut](../../Images/keybinds.png)
#
## Resource manager
![resource manager](../../Images/icons/resource_manager.png)  
For some of the mod's features you might have to download an asset bundle containing resouces needed for the feartures to function. In this tab you can download and update the bundle.
![resouce manger_tut](../../Images/resource_manager.png)