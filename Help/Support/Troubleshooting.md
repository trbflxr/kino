# Mod doesn't work?  
If the mod doesn't work there could be multiple reasons as to why that could be happening.
> **Note:** Win 7 and cracked version of the game are unsupported.

Let's take a look at possible solutions:

### **|** Installation  
If this is your first time installing the mod and it doesn't appear in the game, then the most common case is wrong installation. It could be either the improper installation of the BepInEx mod loader or the mod itself. Either way, if you're installing KiNO for the first time and it doesn't appear in the game, please refer to the [installation](../../INSTALL.md) and make sure you did everything right.

### **|** Use the correct branch. 
Make sure you're on the moddable version of the game.  
Go to Steam and right click on **CarX Drift Racing Online**. Go to **`Properties...`**, then click on **`BETAS`** and select a version of the game that has **(moddable)** next to the version name.

### **|** Update to the latest version
A lot of fixes are posted as patches instead of releases, so you won't find them on the list of releases. Make sure you have the latest version. Reinstall the latest release manually if needed.

### **|** Verify game files
This is one of the obvious solutions a lot of people seem to look over. If none of the mods work, then this just might be the case. To do that, click on the game in your steam library, click on the `Properties..`, go to `Local files` and click on the `Verify integrity of game files...`

### **|** .NET Framework
The mod uses the .NET Framework 4.6.2. Usually this is something you should already have installed. However it won't hurt to try. Download it from the [Microsoft website](https://dotnet.microsoft.com/download/dotnet-framework/net462). You will need the [.NET Framework 4.6.2 Runtime](https://dotnet.microsoft.com/download/dotnet-framework/thank-you/net462-web-installer)

### **|** Visual C++ Redistributable
This is described in the installation process, however if you for some reason missed it, this might be exactly the solution you are looking for.  
The mod relies on the **Visual C++ Redistributable for Visual Studio 2015, 2017 and 2019**. If the mod doesn't appear in game or you get the following error:  
![vcredisterror](https://cdn.discordapp.com/attachments/561211887900033044/810289048018616370/redist.png)  
even if your installation 100% correct, this might be the cause. However only resort to this if KiNO is the only mod that isn't working. You will need the x64 version of the VC Redist that you can also download from the [Miscrosoft website](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads). Download and install the [vc_redist.x64.exe](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads).

> 📌**Note:** after installing **.NET Framework** and **Visual C++ Redistributable** you might have to restart your PC for it to work.

### **Still having issues? Get the log.**
### **For BepInEx**

**|** 1. Go to your CarX Drift Racing Online folder and find the file called `doorstop_config.ini`.  
**|** 2. Open the file with any text editor and find a following line:  
```
redirectOutputLog=false
```
**|** 3. Change the value from **false** to **true** like in the example bellow:
```
redirectOutputLog=true
```
 If it's already set to **true** then skip to the next step.  

**|** 4. Start the game once. Close the game right after you load into the garage (or if you have an issue with a specific feature, close the game after trying to use the feature). You should have a file called `output_log.txt` generated inside the CarX Drift Racing Online folder.   
**|** 5. Open a ticket in [our discord](https://discord.gg/WfHAp6UupP) and send the `output_log.txt` file along with detailed explanation of the issue.  
> 📌 If the file isn't there you might have an issue with **BepInEx**, unfortunately we cannot provide support for that.

### **For Kino Loader**

**|** 1. Start the game

**|** 2. If you have an issue with a specific feature make sure to reproduce it

**|** 3. Close the game normally

**|** 4. The file will appear inside the following folder:
```
CarX Drift Racing Online/kino/output_log.txt
```
The loader will generate the file automatically so you don't have to change any values.
