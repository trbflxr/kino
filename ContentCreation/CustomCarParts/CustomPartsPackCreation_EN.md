## Preparing the Project Structure

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

## Creating Pack Metadata

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

## Filling in the Pack Metadata

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
