# Creating Custom Wheels

## Preparing and Creating a Pack

If you have already created a pack and want to add new wheels to it, you can skip this step.

There's no need to create a separate pack for each wheel; group them by type, manufacturer, etc.

To create a pack, use [this guide](CustomParts_EN.md).

## Creating the Wheel Model

> [!NOTE]
> If you have experience creating wheels for the workshop, you can skip this step and proceed to [importing into Unity](#importing-models-into-unity).

The guide will show an example for `Blender`. If you use other modeling software, the steps will be similar.

After creating the wheel model, it needs to be prepared for export.

> [!IMPORTANT]
> The wheel should be oriented with its front side facing the `X` axis.

> [!IMPORTANT]
> The wheel should consist of at least two parts: `rim` and `spokes`, with these exact names. These parts should not have textures.

However, the wheel can have more than two components, and they can be named as desired. These components can also be textured.

In the example below, the wheel has a `wheel_nuts` component.

> [!IMPORTANT]
> Note the offset of the wheel relative to the zero coordinates. The wheel will be mounted on the hub by the central point of the `spokes` part. Keep this in mind and adjust the wheel as needed along the `X` axis.

![parts_wheel_blender_info](../Images/CarParts/parts_wheel_blender_info.png)

Now the wheel needs to be adjusted to the game's dimensions. To do this, import the fitment model from the `kino_content_sdk/FitmentModels` folder and adjust the size of your wheel to match the fitment model.

![parts_wheel_blender_fit](../Images/CarParts/parts_wheel_blender_fit.png)

Afterward, you can export the wheel. Ensure the `Transform` section parameters match those in the image.

Additionally, if there are other objects in the scene that you don't want included in the model, you can select one of the `Limit to` options. However, any unnecessary components can also be removed in Unity after creating the prefab.

![parts_blender_export](../Images/CarParts/parts_blender_export.png)

Upon completing the export, you can proceed to import the model into Unity.

## Importing Models into Unity

To import models into Unity, you can drag the necessary files into the `Project` window or manually place them there via the file explorer.

After importing, select the desired model and in the `Inspector` window, go to the `Materials` tab.

If the `Extract Textures` and `Extract Materials` buttons are greyed out and unclickable, there's nothing more to do.

If they are active, extract the textures first, followed by the materials.

![parts_unity_import_model](../Images/CarParts/parts_unity_import_model.png)

## Adding Wheels to the Pack

> [!WARNING]
> If you haven't created metadata for the pack yet, please do so using the [instructions above](#preparing-and-creating-a-pack).

To make the wheels available in the game, you need to add them to the pack. This is very simple.

1. In the `Project` window, select the previously created `__meta` file.  
   ![parts_select_pack_meta](../Images/CarParts/parts_select_pack_meta.png)

2. Then, add a slot for the wheel to the list by clicking `+`.
3. Fill in the fields as shown in the example below.

![parts_fill_part_meta](../Images/CarParts/parts_fill_part_meta.gif)

> [!NOTE]
> Note that in the `Replacement Id` field, I specified the value `111` because this wheel **from the standard set** in the game is the closest match to the one I added.

![parts_similar_part_id](../Images/CarParts/parts_similar_part_id.png)

### Replacement Id

This field is optional but highly recommended. It ensures that if someone doesn't have **Kino** or **this pack**, the car will still have a similar standard part installed.

## Building the Pack

The final step is to build the pack.

The process of building is described for all types of packs [here](CustomParts_EN.md#building-packs).

---

## Display Issues in the Game

If the wheels are not visible or are incorrectly oriented in the game, this can be easily fixed.

First, create a prefab for the wheel. Right-click on the wheel model in the **Project** window, then select `Create -> Prefab Variant`.

![parts_create_prefab](../Images/CarParts/parts_create_prefab.png)

Then, in the metadata file, replace the wheel prefab with the one just created.

![parts_meta_replace_prefab](../Images/CarParts/parts_meta_replace_prefab.png)

Go into edit mode by double-clicking on the new prefab in the `Project` window.

![parts_wheels_edit_prefab](../Images/CarParts/parts_wheels_edit_prefab.png)

### Scale Issues (Wheel Not Visible)

Ensure that the root object's (in this case `crooked_ssr`) `Transform` component has `Scale` fields set to **1**.

Then, select all objects inside the root and check the `Scale` parameter in the `Transform` component.

![parts_wheel_select_childs](../Images/CarParts/parts_wheel_select_childs.png)

If you followed the guide, the `Scale` field should have a value greater than or equal to one (1). However, if you see values below one, set the `Scale` fields to **1**, save the prefab, rebuild the pack, and check it in the game.

This way, you can adjust the scale correctly.

### Incorrect Wheel Orientation

Go into the prefab edit mode and check the wheel's orientation. The correct wheel orientation should look like this. The wheel should face the opposite direction along the `X` axis, as shown below.

![parts_wheel_correct_rotation](../Images/CarParts/parts_wheel_correct_rotation.png)

If the wheel is oriented differently, select all objects inside the root and rotate them correctly.

![parts_wheel_select_childs](../Images/CarParts/parts_wheel_select_childs.png)

In this case, setting `-90` on the `Y` axis fixed the issue.

![parts_wheel_correct_wheel_rotation_transform](../Images/CarParts/parts_wheel_correct_wheel_rotation_transform.png)

### Wheel Offset Issues

If the wheel's offset is incorrect or it is shifted along any axis in the game, this can be easily fixed.

![parts_wheel_bad_offset](../Images/CarParts/parts_wheel_bad_offset.png)

Select the desired prefab and double-click to enter edit mode. Then, select all objects inside the root and check the `Position` parameter in the `Transform` component.

![parts_wheel_offset_info](../Images/CarParts/parts_wheel_offset_info.png)

The game will attach the wheel to the hub at the point set in the `spokes` object. The image above shows how this point is offset, causing incorrect wheel placement in the game.

Move all objects inside the root to compensate for the offset as needed.

![parts_wheel_offset_fix](../Images/CarParts/parts_wheel_offset_fix.png)

In this case, setting `0.071` on the `X` axis fixed the issue.

Save the prefab and rebuild the pack.

### Wheel Still Offset or Stuck in Brakes

If the wheel is still offset after setting offsets for its parts, you need to fix its model in Blender.

The images show that the origin of the `spokes` component is at the center of the object. This point is where the wheel will attach to the hub.

![parts_wheel_spokes_bad_offset](../Images/CarParts/parts_wheel_spokes_bad_offset.png)

![parts_wheel_spokes_bad_offset_unity](../Images/CarParts/parts_wheel_spokes_bad_offset_unity.png)

To fix this, follow these steps:

1. Open the model in Blender.
2. Switch to `Object mode`.
3. Set the 3D cursor to the point where the origin should be.
4. Click `Object -> Set Origin -> Origin to 3D Cursor`.
5. Export the model and [import](#importing-models-into-unity) it into Unity.

![parts_wheel_spokes_offset_fix](../Images/CarParts/parts_wheel_spokes_offset_fix.png)

### Incorrect Shading or Black Wheel

This issue is related to incorrect UV mapping of the wheel and can be easily fixed.

The solution is provided by @Jeefrect (Discord: @jeefrect).

The UV map of the wheel should strictly follow the example. The front side of the spokes and rim must be in the **right half** of the UV map.

![parts_wheel_uv_fix](../Images/CarParts/parts_wheel_uv_fix.gif)

* In the **blue zone** (for spokes), place the UV map of the wheel spokes.
* In the **yellow zone** (for rims), place the UV map of the wheel rim.
* [Optional] In the **red zone** (for backface), place the UV map of the back sides of the wheel if you have them. These areas will be shaded in the game.

![parts_wheel_uv_back](../Images/CarParts/parts_wheel_uv_back.png)

* **Green zone** (for backface spoke), place the UV map of the back side of the spokes.
* **Blue zone** (for backface spoke), place the UV map of the back side of the wheel rim.

> [!NOTE]
> To quickly unwrap the UV map of a selected object in Blender, press `U -> Unwrap`.

![parts_wheel_uv_unwrap](../Images/CarParts/parts_wheel_uv_unwrap.png)

The correct UV map should look like this:

![parts_wheel_uv_both_sides](../Images/CarParts/parts_wheel_uv_both_sides.png)

Or like this if you only did it for the **front part** of the wheel:

![parts_wheel_uv_front](../Images/CarParts/parts_wheel_uv_front.png)