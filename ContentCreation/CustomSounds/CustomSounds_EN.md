# Creating Sound Packs

## Installing Unity and the Content SDK

If you still don’t have Unity installed, install it using [this guide](../Tools/UnityInstallation_EN.md).

If you don’t have the **Content SDK** installed yet, [install and configure it](../Tools/SDKInstall_EN.md).  
Or [update](../Tools/SDKUpdate_EN.md) the **Content SDK** if you already have it installed.

## Sound Banks (.bank)

Sound banks are where all sounds and their parameters are stored.

If you want to port sounds from other games or you already have a compiled sound bank, jump straight to [creating a pack](#creating-a-pack).

If you want to create your own sounds from scratch, follow the guide on [creating sound banks](CustomSoundsFmod_EN.md).

## Creating a Pack

All part sound packs are expected to live in the `Assets/Content/Sounds` folder.

Each pack must be placed in **its own** folder. This makes things cleaner and speeds up the workflow.

Example structure:

```
📂 Assets
 └ 📁 Content
    └ 📁 Sounds
       └ 📁 Examples
       └ 📁 My2JZ_Sound
       └ 📁 SR20_Sound
```

### Finding Target Cars and Swaps

Some sounds are tied to specific cars or Kino swaps.  
To enable Kino swap IDs in the menu `Kino -> Sounds -> FMOD Tools`, enable **Show Engine IDs**.

After that, you’ll see IDs displayed next to engine names in the Kino swap list.  
Car IDs can be viewed in the `Sounds` or `Tools` menus.

### Creating Pack Metadata

Every new pack requires a **metadata file**.  
Go into the folder of your new pack and create the metadata file using the **context menu**.

![sounds_meta_create.png](../Images/Sounds/sounds_meta_create.png)

At this stage, the structure should look something like this:

```
📂 Sounds
 └ 📁 Example
    └ 📄 __meta
```

### Filling in Pack Metadata

Fill in the pack metadata. This only needs to be done **once** per pack.

![sounds_pack_meta.png](../Images/Sounds/sounds_pack_meta.png)

In the `Name` field, enter the pack name. It must be unique and must not contain spaces or special characters.

In the `Bank Type` field, select the type of sound bank you’re using.

> [!IMPORTANT]
> If you don’t hear any sounds from the pack, chances are you selected the wrong `Bank Type`.

In the `Sound Bank` field, assign the **.bank** file.

In the `Guids` field, assign the **GUIDs.txt** file from your sound bank.

Set the pack version in the `Version` field and add a description in `Description`.

### Adding Sounds

To add sounds, click the `+` icon in the bottom-right corner and choose the desired type.

![sounds_meta_add_event.png](../Images/Sounds/sounds_meta_add_event.png)

All sounds follow the same general logic.  
Each one has a `Key` field that defines the sound’s key/name, as well as its components (events).

The example below uses an engine sound.

![sounds_meta_event.png](../Images/Sounds/sounds_meta_event.png)

In the `Key` field, enter an ID that describes the sound — for example `engine` for an engine sound.

This is the name users will see when browsing available sounds.

An engine sound has **two** events: `Rpm` and `Limiter`.  
Just like other events, they share the same structure.

Each event consists of the following fields:
* `ExtEvent` — the event ID that will be heard from **external cameras**, meaning any camera except the cockpit.
* `ExtBaseVolume` — base volume for the external sound. This value is used during sound synchronization.
* `IntEvent` — the event ID that will be heard **only** inside the cockpit.
* `IntBaseVolume` — base volume for the cockpit sound, also used during synchronization.

In the `ExtEvent` and `IntEvent` fields, you must enter the GUID of the corresponding event from **GUIDs.txt**.

If you created the sound bank yourself, you already know which events to use.  
If you’re porting sounds from another game, pay attention to event names in **GUIDs.txt** — usually it’s obvious which GUID goes where.

It’s also worth noting that the `Int*` fields are optional.  
You don’t have to fill them in — the important part is setting the `Ext*` fields.

> [!IMPORTANT]
> Before releasing your packs, you **MUST** tune `ExtBaseVolume` and `IntBaseVolume` for every sound so their loudness roughly matches the game’s default sounds.
>
> This is extremely important and has a big impact on how other players experience your sounds.

If a sound has a `Targets` field, specify the **car IDs** or **Kino swap IDs** it is intended for.

How to obtain target IDs was explained earlier in  
[finding target cars and swaps](#finding-target-cars-and-swaps).

You can specify as many targets as you want.  
For example, all cars using a **2JZ** engine, plus a Kino swap for a custom 2JZ sound.

This field is **required**.

## Building Packs

Once you’ve finished creating the pack and filling in its metadata, you can move on to building it.

If the build tool isn’t open, you can access it via  
`Kino -> Car Sounds Build Tool`.

![sounds_tool_open.png](../Images/Sounds/sounds_tool_open.png)

If you see this message, click the button to create the metadata.

![sounds_tool_meta_create.png](../Images/Sounds/sounds_tool_meta_create.png)

In the **Build Folder** field, you can choose any folder you like.  
In this example, the path points to `KN_Base\sounds` so finished packs are installed immediately.

![sounds_tool_meta_folder.png](../Images/Sounds/sounds_tool_meta_folder.png)

In the build tool window, select the packs you want to build using the `Selected to build` field, then click `Build for ...`.

From this tool, you can also configure author information, the build folder, and open settings for individual part packs.

![sounds_build_tool.png](../Images/Sounds/sounds_build_tool.png)

Once the build process is complete, the finished packs will be placed in the folder you specified.