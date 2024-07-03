# Creating Resource Packs

## Unity and Content SDK Installation

Install the Unity editor using [this guide](../UnityInstallation/UnityInstallation_EN.md).

Next, install and configure the [Content SDK](../ContentSDK/ContentSDKInstallation_EN.md).

> [!NOTE]
> In the `Assets/Content/CustomObjects/Example` folder, you'll find an example resource pack that you can explore.

## Project structure preparation

Assume that all resource packs should be located in the `Assets/Content/CustomObjects` folder.

Each resource pack should have its **own** folder. This approach enhances convenience and speeds up creation.

Example structure:

```
📂 Assets
 └ 📁 Content
    └ 📁 CustomObjects
       └ 📁 Example
       └ 📁 MyPack1
       └ 📁 MyPack2
```

> [!IMPORTANT]
> Create a new folder within `CustomObjects` for each new resource pack.

## Creating resource pack metadata

> [!IMPORTANT]
> In this example, we'll use the pack name `Example`. Feel free to name your resource packs as you like.

For each new pack, you need to create a **metadata file**. To do this, create and navigate to the folder of your new resource pack. Then, create the metadata file using the **context menu**.

![meta_create.png](../Images/ResourcePacks/meta_create.png)

The structure should look as follows:

```
📂 CustomObjects
 └ 📁 Example
    └ 📄 __objects_meta
```

## Filling out metadata for the resource pack

Fill out the metadata for the pack. This needs to be done **once** for **each** resource pack.

![pack_meta_setup.png](../Images/ResourcePacks/pack_meta_setup.png)

The most important field is **Name**, which is the name of the resource pack and must be unique.

The other fields are **optional**, you may leave them as is.

## Creating and configuring objects in Blender

This example discusses working with **Blender**, but you can use any **other software**.

You can add the following options for objects:
* [CarPaint](#carpaint) - allows painting the object in the game
* [CarLights](#carlights) - light sources
* [Exhaust](#exhaust) - exhaust particle source

### CarPaint
Mark objects with CarPaint for which painting capability is intended.

![car_paint_blender.png](../Images/ResourcePacks/car_paint_blender.png)

> [!IMPORTANT]
> In the example, you can see that to add CarPaint, you need to either name the object `car_paint` or prefix its name with `car_paint_`.

### CarLights

For additional headlights and taillights for the car, create the necessary objects as shown in the example below.

These can be either empty objects with light sources, which can be configured directly in **Blender**, or models. There are no restrictions.

The visibility of `head_lights` and `running_lights` will be toggled in Kino with the headlight binds. Additionally, pressing the brake will turn on the `tail_lights` objects.

![car_lights_naming.png](../Images/ResourcePacks/car_lights_naming.png)

> [!IMPORTANT]  
> To add CarLights, you need to either name the object `head_lights, running_lights, tail_lights`, or prefix their names with these.

### Exhaust

The Exhaust option specifies where the exhaust particles will emit from.

To add an exhaust source, create an empty object and set its desired position and rotation.

![flames_root_blender.png](../Images/ResourcePacks/flames_root_blender.png)

Note that particles will emit along the `Z` axis. Rotate the object in the correct direction.

![flames_root_direction.png](../Images/ResourcePacks/flames_root_direction.png)

![flames_root_name.png](../Images/ResourcePacks/flames_root_name.png)

> [!IMPORTANT]  
> Name the object `flames_root` or prefix its name with `flames_root_` to mark it as an exhaust source.

## Creating and configuring objects in other software

You can also configure objects in any other software, including **Unity** itself.

The setup process will be similar to [the setup in Blender](#creating-and-configuring-objects-in-blender).

## Setting Up Blender Integration

> [!WARNING]  
> If you are not using Blender or want to use `.fbx` models, you can skip this step.
> Find information on importing models from your chosen software online.
> The process of importing models is [described below](#importing-blend--fbx-files-into-unity).

Instructions for setting up **Blender** integration are described in [this guide](../Blender/BlenderIntegration_EN.md).

## Importing .blend / .fbx Files into Unity

> [!WARNING]  
> If you want to add models as `.fbx` files, make sure the export settings are configured as highlighted in the screenshot.
> The `Path Mode` field should be set to **Copy**, and the `Forward` and `Up` settings in the `Transform` section should be set as shown in the example.

> [!IMPORTANT]  
> Export the model to the folder of the resource pack you are working on, next to the `__objects_meta` metadata file. This way, Unity will see the textures and the model without any additional actions.


```
📂 Assets
 └ 📁 Content
    └ 📁 CustomObjects
       └ 📁 Example
          └ 📁 your_model_name.fbm   <- this folder will be created by Blender, and it contains the textures for the model
          └ 📄 __objects_meta
          └ 📄 your_model_name.fbx   <- right here
```

![blender_export_fbx.png](../Images/Blender/blender_export_fbx.png)

> The process of importing `.blend` and `.fbx` files is similar.

If the file contains one model or multiple models but is intended to be one object, select the metadata file (in this example `__object_meta`) and click **Refresh assets** in the inspector. Then you can proceed to [building the resource pack](#building-the-resource-pack).

![meta_refresh_assets.png](../Images/ResourcePacks/meta_refresh_assets.png)

If your project/file contains more than one model or you want to fine-tune its components, you will need to perform the following steps.

1. Drag the newly saved file to the scene (the **Hierarchy** tab), as shown in the example below.  
   ![blend_drag_on_scene.png](../Images/ResourcePacks/blend_drag_on_scene.png)

2. Unpack the prefab  
   ![prefab_unpack.png](../Images/ResourcePacks/prefab_unpack.png)

3. Select the required object or objects and drag them to the `Project` window, as shown in the example  
   ![prefab_save_part.png](../Images/ResourcePacks/prefab_save_part.png)

4. Double-click the newly saved prefab to enter edit mode.

5. Then select the metadata file and click `Refresh assets` to add the prefab to the resource pack.  
   ![meta_refresh_assets.png](../Images/ResourcePacks/meta_refresh_assets.png)

6. You can now proceed to [building the resource pack](#building-the-resource-pack).

> [!WARNING]  
> Note that changes made to `.blend` or `.fbx` files **will NOT** automatically apply to the unpacked prefabs.
> You will need to delete the prefab(s) and go through the unpacking process again.

## Building the Resource Pack

If the build tool is not open, you can open it through the menu `Kino -> Custom Objects tool`.

![tool_open.png](../Images/ResourcePacks/tool_open.png)

You can drag the **Build tool** to any area for convenience.

![tool_drag.png](../Images/ResourcePacks/tool_drag.png)

If you see a message like this, click the button to create metadata.

![tool_meta_create.png](../Images/ResourcePacks/tool_meta_create.png)

In the **Build Folder** field, you can specify any convenient folder. I specified the path to `KN_Base\resources` so that the finished resource packs are immediately installed in the game.
![tool_build_meta_setup.png](../Images/ResourcePacks/tool_build_meta_setup.png)

In the build tool window, select the resource packs you want to build using the `Selected to build` field. Then click the `Build for ...` button.

You can also configure author information, build folder, and open settings for each resource pack from this tool.
![tool_main.png](../Images/ResourcePacks/tool_main.png)

After the build is complete, the finished resource pack will be placed in the folder you specified.

# Note

This guide shows the process of creating a simple object from a model. However, this is far from the only possibility of resource packs.
You can create custom effects, animated objects, and much more using Unity tools and upload it to CarX using Kino resource packs.