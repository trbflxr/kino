# Setting Up Blender Integration

> [!WARNING]  
> This guide is based on the example of CustomObjects (resource packs). However, if you are creating **maps** or **car parts**, the only difference will be the folder where you save the `.blend` file.

Importing `.blend` files is the fastest and simplest way to add models to the editor.

Save your Blender project in the folder with your **resource pack** / **map** / **car parts**, next to the **metadata** file (for example, `__objects_meta`).

```
📂 Assets
 └ 📁 Content
    └ 📁 CustomObjects
       └ 📁 Example
          └ 📁 Textures                <- possible textures location
          └ 📄 __objects_meta
          └ 📄 your_model_name.blend   <- right here
 └ 📁 SharedTextures                   <- possible textures location
```

> [!WARNING]  
> Please keep in mind that textures used in Blender must be located in the `Assets` folder of your project for Unity to **detect** them.

If you see an error similar to the one below in the **Unity** console after saving the `.blend` file:

![blender_not_found_error.png](../Images/Blender/blender_not_found_error.png)

Fixing this is very simple. Open the folder with the `.blend` file, then go to its properties: `Right-click -> Properties`

![blend_file_properties.png](../Images/Blender/blend_file_properties.png)

In the `Open with` field, click `Change`, then specify the path to `blender-launcher.exe`, located in the **root directory** of Blender. Click **Apply** in the file properties window.

Next, open Unity, select the `.blend` file in the list, click `...` in the Inspector, and select `Reset`.
![blend_reset_unity.png](../Images/Blender/blend_reset_unity.png)
