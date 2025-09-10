# Mod doesn't work?  
If the mod doesn't work there could be multiple reasons as to why that could be happening.
> **Note:** Win 7 and cracked version of the game are unsupported.

Let's take a look at possible solutions:

### **|** Installation  
If this is your first time installing the mod and it doesn't appear in the game, then the most common case is wrong installation. It could be either the improper installation of the [KSL](https://github.com/trbflxr/ksl/blob/master/doc/guide/install_win.md) mod loader or the mod itself. Either way, if you're installing Kino for the first time, and it doesn't appear in the game, please refer to the [installation](../../INSTALL.md) and make sure you did everything right.

### **|** Use the correct branch. 
Make sure you're on the moddable version of the game.  
Go to Steam and right click on **CarX Drift Racing Online**. Go to **`Properties...`**, then click on **`BETAS`** and select a version of the game that has **[moddable]** next to the version name.

### **|** Update to the latest version
A lot of fixes are posted as patches instead of releases, so you won't find them on the list of releases. Make sure you have the latest version. Reinstall the latest release manually if needed.

### **|** Verify game files
This is one of the obvious solutions a lot of people seem to look over. If none of the mods work, then this just might be the case. To do that, click on the game in your steam library, click on the `Properties..`, go to `Local files` and click on the `Verify integrity of game files...`

### **|** .NET Framework
The mod uses the .NET Framework 4.7.2. Usually this is something you should already have installed. However, it won't hurt to try. Download it from the [Microsoft website](https://dotnet.microsoft.com/download/dotnet-framework/net472). You will need the [.NET Framework 4.7.2 Runtime](https://dotnet.microsoft.com/download/dotnet-framework/thank-you/net472-web-installer)

### **Get the log**

1. Start the game

2. If you have an issue with a specific feature make sure to reproduce it

3. Close the game normally

4. The file will appear inside the following folder:

```
CarX Drift Racing Online/kino/output.log
```

The loader will generate the file automatically, so you don't have to change any values.

# The Mod displays incorrectly and/or not all features are available

If after updating the mod the UI displays incorrectly and/or you lose access to swaps, sticker packs, or tuning features, use [this guide](ResourcesUpdate.md) to resolve the issue.
