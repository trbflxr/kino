# Setting Up Blender Integration

> [!WARNING]  
> This guide uses CustomObjects (resource packs) as an example. However, the process is the same for other types of content.

Importing `.blend` files is the fastest and easiest way to add models into the editor.

Save the Blender project into the desired folder. The folder must be located inside `Assets` in the `Content SDK` project.

```
📂 Assets
 └ 📁 Content
    └ 📁 CustomObjects
       └ 📁 Example
          └ 📁 Textures
          └ 📄 __objects_meta
          └ 📄 your_model_name.blend   <- for example, here
 └ 📁 SharedTextures
```

> [!WARNING]  
> Note that the textures you use in `Blender` must be located inside the project’s `Assets` folder, otherwise Unity **will not detect** them.

If after saving the `.blend` file you see this or a similar error in the **Unity** console:

![blender_not_found_error.png](../Images/Blender/blender_not_found_error.png)

Fixing this is very simple. Open the folder with the `.blend` file, then go to its properties: `RMB -> Properties`.

![blend_file_properties.png](../Images/Blender/blend_file_properties.png)

In the `Open with` field, click `Change`, then specify the path to `blender-launcher.exe`, which is located in the **root directory** of Blender. Then click **Apply** in the file properties window.

Next, open Unity, select the `.blend` file in the list, click `...` in the inspector, and choose `Reset`.  
![blend_reset_unity.png](../Images/Blender/blend_reset_unity.png)