# Resource pack creation

## Unity Installation

Install the Unity editor using [this guide](https://github.com/trbflxr/kino/blob/master/Help/UnityInstallation.md).

## Create a Unity project

First you need to create a new **HDRP** project. It can be done from the Unity Hub.

![unity_hub_create.png](../Images/guide/resources/unity_hub_create.png)

Then you need to select any **HDRP** template. It's preferable to select **Core (HDRP)** if available, otherwise you can select any default HDRP template for a Unity project.

> [!NOTE]  
> It is mandatory to specify the version of the Unity Editor `2020.3.25f1`, then you can create the project.

![unity_hub_create_hdrp.png](../Images/guide/resources/unity_hub_create_hdrp.png)

## Installing the tools for the resource pack creation

At the moment Kino supports loading of any asset bundles without any specific custom format.

You can create the asset bundles in any way you prefer. If you have any tools for working with the bundles that you're accustomed to - you are free to use them.

We recommend using [AssetBundles Browser](https://github.com/Unity-Technologies/AssetBundles-Browser#installation). This is the tool that will be used in all the examples for this guide.

### AssetBundles Browser installation

1. Open the Package Manager in the project

![unity_open_pm.png](../Images/guide/resources/unity_open_pm.png)

2. After that click on the **+** and select **_Add package from git URL_**

![unity_add_git_package.png](../Images/guide/resources/unity_add_git_package.png)

3. Copy this https://github.com/Unity-Technologies/AssetBundles-Browser.git and paste inside the field. Then press **Add**

![unity_add_bundle_browser.png](../Images/guide/resources/unity_add_bundle_browser.png)

4. Wait until the installation is complete

Documentation for the **AssetBundles Browser** is available [at this link](https://github.com/Unity-Technologies/AssetBundles-Browser/blob/master/Documentation/com.unity.assetbundlebrowser.md).

## [Optional] Preparation of a scene and a project in Unity

For a more convenient workflow we recommend creating an empty **HDRP** scene.

1. Press File -> New scene or `Ctrl + N`

![unity_new_scene.png](../Images/guide/resources/unity_new_scene.png)

2. Then select **Basic Outdoors (HDRP)** and press **Create**

![unity_create_new_scene.png](../Images/guide/resources/unity_create_new_scene.png)

3. Then save the scene to a suitable directory

### [Optional] Deleting unnecessary stuff from the project

In case the created project contains examples, you are free to delete them for the sake of speeding up the project.

In the example we created **3D Sample Scene (HDRP)** project, scene and the assets of which are of no use to us. The following folders can be deleted from your project.

![unity_delete_samples.png](../Images/guide/resources/unity_delete_samples.png)

## Exporting models from Blender

In the example we are exporting models from **Blender**, however you can use any 3D modelling software you're familiar with.

1. Press File -> Export -> FBX

![blender_export.png](../Images/guide/resources/blender_export.png)

2. In the **Path Mode** field press **Copy** and make sure that **Embeded textures** option is active
3. Then go to the **Transform** field and specify the correct values for **Forward** and **Up** as shown in the screenshot.

![blender_export_params.png](../Images/guide/resources/blender_export_params.png)

4. Specify the path and press **Export FBX**

## Preparation of the object

The objects can be created either from the models that you [exported](#exporting-models-from-blender) from Blender, or using any other models. You can also create simple models right in Unity.

The process of the creation might be a little different. A few variations are described bellow.

### Preparation of the exported model

1. After exporting the model place the **.fbx** file inside of the**Assets** folder of your Unity project
2. Then select the model in the asset list, then got to the **Materials** tab inside of the **inspector** and press **Extract textures**. Then select the folder where the textures will be exported.

![unity_extract_textures.png](../Images/guide/resources/unity_extract_textures.png)

3. At this stage the preparation process is complete and the model should appear in the preview with correct textures. Now you can get to [creating an object](#object-creation)

### Preparation of other models

In some cases you'll have to extract the materials and assign the textures and their properties manually. In order to do that select the model in the assets list and press **Extract materials** in the **inspector**. Then specify where you want to extract the materials.

After that adjust the material settings and assign the textures if needed. All of this can be done in the inspector of the selected material.

![unity_extract_materials.png](../Images/guide/resources/unity_extract_materials.png)

## Object creation

1. After the model has been [prepared](#preparation-of-the-object) load it into the scene by dragging it to the scene's hierarchy.
2. Here you can adjust the **Transform** parameters of the objects, its hierarchy and more

![unity_object_on_scene.png](../Images/guide/resources/unity_object_on_scene.png)

> [!NOTE]
> **[Optional]** In case you want to make the object paintable add ```car_paint_``` at the start of the paintable object's name

![unity_car_paint.png](../Images/guide/resources/unity_car_paint.png)

![carx_car_paint.png](../Images/guide/resources/carx_car_paint.png)

> [!NOTE]  
> **[Optional]** You can also create a custom **exhaust / wastegate**. To do that put empty objects in places where the backfire is supposed to be and add ```flames_root``` at the start of the object's name for every object that needs it.

![carx_car_paint.png](../Images/guide/resources/flames_root_model.png)

![carx_car_paint.png](../Images/guide/resources/flames_root_hierarchy.png)

> [!IMPORTANT]  
> Keep in mind that the direction of the flames depends on the rotation of the ```flames_root``` objects. Make sure to test it properly before publishing.

3. Then drag an object from the scene back to the **Assets** tab and select **Original Prefab** in the dialog box.

![unity_save_prefab.png](../Images/guide/resources/unity_save_prefab.png)

![unity_save_prefab_dialog.png](../Images/guide/resources/unity_save_prefab_dialog.png)

As you might have noticed the icon change to the icon of the prefab.

Object is created. Now you can [add it to the bundle](#adding-an-object-to-a-bundle).

## Creating a bundle (resource pack)

You already installed [AssetBundles Browser](#installing-the-tools-for-the-resource-pack-creation) earlier.

> [!NOTE]  
> You can create as many bundles or add as many objects to them as you wish. Bellow is an example of creating a new bundle.

1. Press Window -> AssetBundle Browser

![unity_open_bundle_browser.png](../Images/guide/resources/unity_open_bundle_browser.png)

2. Rick click on the appearing window and press **Add new bundle**

![unity_create_bundle.png](../Images/guide/resources/unity_create_bundle.png)

3. Then specify the name of the bundle

![unity_name_bundle.png](../Images/guide/resources/unity_name_bundle.png)

4. Bundle is created. Now you can [add](#adding-an-object-to-a-bundle) objects to it.

## Adding an object to a bundle

To add an object to a bundle you need to select the bundle which you want the object to be added to and then drag in the object from the **Project** tab.

![unity_bundle_add_asset.png](../Images/guide/resources/unity_bundle_add_asset.png)

> [!NOTE]  
> You can have as many objects added to a bundle (resourcepack) as you want. However it's not recommended to make the bundles too big in size as it would affect the loading times.

## Building the bundle (resourcepack)

To build the bundle go the **Build** tab and press **Build**.

![unity_bundle_build.png](../Images/guide/resources/unity_bundle_build.png)

After the build is complete you can [install the pack](#resourcepack-installation).

## Resourcepack installation

Copy the created bundle to the `KN_Base/resources` folder, after that the bundle is ready for use.

# Notes

This guide shows the process of creation of a simple object from a model. However this is by far not the only resourcepack capability.
You can create custom effects, animated objects or anything else that you might want using the Unity tools and then load it to CarX using Kino resourcepacks.
