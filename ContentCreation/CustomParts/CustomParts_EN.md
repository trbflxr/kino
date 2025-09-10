# Creating Custom Parts Packs

## Installing Unity and the Content SDK

If you still don’t have Unity installed, install it using [this guide](../Tools/UnityInstallation_EN.md).

If you haven’t installed the **Content SDK**, then [install and set it up](../Tools/SDKInstall_EN.md). Or [update](../Tools/SDKUpdate_EN.md) the **Content SDK** if you already have it installed.

> [!NOTE]  
> There are example custom parts packs in the `Assets/Content/CarParts/Examples` folder that you can refer to.

## Creating Parts Pack

All parts packs should be located in the `Assets/Content/CarParts` folder.

Each pack should be in its **own** folder. This will increase convenience and speed up creation.

Example structure:

```
📂 Assets
 └ 📁 Content
    └ 📁 CarParts
       └ 📁 Examples
       └ 📁 MyWheelPack1
       └ 📁 MyExteriorPack1
       └ 📁 MyInteriorPack1
```

> [!IMPORTANT]  
> Create a new folder in `CarParts` for each new parts pack.

### Creating Pack Metadata

> [!IMPORTANT]  
> In this example, the pack name `Example` will be used. You can name your packs as you wish.

For each new pack, a **metadata file** must be created. To do this, create and navigate to the new pack's folder. Then create the metadata file using the **context menu**.

![parts_meta_create.png](../Images/CarParts/parts_meta_create.png)

The structure should look as follows:

```
📂 CarParts
 └ 📁 Example
    └ 📄 __meta
```

### Filling in the Pack Metadata

Fill in the metadata for the pack. This needs to be done **once** for **each** pack.

![parts_meta_setup.png](../Images/CarParts/parts_meta_setup.png)

In the **Type** field, specify the pack type.

In the **Name** field, specify a name. It must be unique and should not contain spaces.

Specify the category name in the **CategoryName** field. This name will be displayed in the game interface on the pack card.

Add a description of the pack in the **Description** field.

In the **PackIcon** field, specify the icon for the pack. This icon will be displayed on the pack card in the game interface.

The **Version** field is for the pack version. Leave it as it is for now, with the value `100`.

> [!IMPORTANT]
> To create a pack for body kit parts, select the type `Car Parts`. **Be sure** to specify the car ID for which this pack is intended in the `Target car ID` field.
>
> You can find the ID of the current car in the Kino menu: `Tools -> Developer tools`.

## Creating Content

You can now start creating custom parts.

> [Wheels](CustomPartsWheels_EN.md)

> [Body parts and lights](CustomPartsExterior_EN.md)

> [Brakes](CustomPartsBrakes_EN.md)

> [Tires](CustomPartsTires_EN.md)

> [Interior](CustomPartsInterior_EN.md)

> [Universal interior parts](CustomPartsUniversalInterior_EN.md)

## Building Packs

Once you have finished creating the pack and filling out its metadata, you can proceed with building it.

If the build tool is not open, you can access it via the menu `Kino -> Car Parts build tool`.

![parts_tool_open.png](../Images/CarParts/parts_tool_open.png)

You can drag the **Build tool** to any zone for ease of use.

![parts_tool_drag.png](../Images/CarParts/parts_tool_drag.png)

If you see a message like this, click the button to create the metadata.

![parts_tool_meta_create.png](../Images/CarParts/parts_tool_meta_create.png)

In the **Build Folder** field, you can specify any convenient folder. I have set the path to `KN_Base\car_parts` so that the finished packs are immediately installed in the game.
![parts_tool_meta_setup.png](../Images/CarParts/parts_tool_meta_setup.png)

In the build tool window, select the resource packs you want to build using the `Selected to build` field. Then click the `Build for ...` button.

From this tool, you can also set author information, the build folder, and open settings for each parts pack.
![parts_tool_main.png](../Images/CarParts/parts_tool_main.png)

After the build is complete, the finished packs will be placed in the folder you specified.
