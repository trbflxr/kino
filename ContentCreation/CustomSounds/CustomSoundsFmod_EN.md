# Creating FMOD Banks

> [!NOTE]
> This guide is not a general FMOD Studio tutorial. It’s specifically about creating sounds that are compatible with Kino.

## Installing FMOD Studio

Before working with sound banks, you need to install a specific version of FMOD Studio.

Use [this guide](../Tools/FMODInstallation_EN.md) to install FMOD Studio.

If you already have FMOD Studio installed, make sure the version is `2.02.00`.  
If it’s a different version, you must install this exact one.

## FMOD Studio Project

You **must** use the project provided in the [Content SDK](../Tools/SDKInstall_EN.md).  
It’s located in the `Fmod` folder.

> [!WARNING]
> Any other FMOD Studio projects will not work. You **must** use the provided project.

The `kino_sounds.fspro` project contains example sounds that are currently supported by Kino.  
It’s highly recommended to look through them.

## Sound Types

Kino supports the following sound types:
* **Engine**
    * EngineRPM — engine RPM sound
    * EngineLimiter — _optional_ rev limiter sound
* **Turbo**
    * TurboBoost — (spool) controls turbo whistle or supercharger sound
    * TurboBOV — _optional_ blow-off valve and turbo flutter sound
* **Exhaust**
    * ExhaustPop — exhaust backfire / pop sound
    * ExhaustFlatshift — _optional_ sound played during flatshift (upshift without lifting)
    * ExhaustAfterburn — _optional_ sound of fuel afterburning in the exhaust

As you can see, each sound consists of multiple events.  
Some of these events are optional, and the sound can be used without them.

Each event has its own [parameters](#event-parameters), described below.

## Event Parameters

Here is a list of parameters that are currently available and supported in Kino:
* **Event Orientation** — event orientation relative to the camera **[-180 — 180]**. This lets you make the turbo louder near the hood and the exhaust louder near the rear bumper.
* **Distance** — distance to the camera **[0 — 420]**
* **Engine_RPM** — current engine RPM **[0 — 10k]**
* **Engine_Load** — current engine load **[0 — 1]**
* **Engine_HP** — current engine power output **[0 — 1.5k]**
* **Turbo_Boost** — intake manifold pressure **[0 — 1]**
* **Turbo_RPM** — turbo RPM **[0 — 1]**
* **Turbo_BOV** — blow-off valve position **[0 — 1]**
* **Turbo_BOVPower** — blow-off valve strength **[0 — 1]**.  
  At value 0, the BOV will not open, resulting in turbo flutter. The `turbo` example demonstrates how to use this parameter.
* **Turbo_Wastegate** — current wastegate position **[0 — 1]**
* **Throttle** — throttle pedal position **[0 — 1]**
* **SpeedMPH** — current vehicle speed **[0 — 200]**

Below is a list of events and the parameters they support:
* **EngineRPM**: Engine_RPM, Engine_Load, Engine_HP, Turbo_Boost, Turbo_Wastegate, Throttle
* **EngineLimiter**: Engine_RPM, Engine_Load
* **TurboBoost**: Turbo_Boost, Turbo_RPM, Turbo_Wastegate, Engine_RPM, Throttle
* **TurboBOV**: Turbo_Boost, Turbo_BOV, Turbo_BOVPower
* **ExhaustPop**: Engine_RPM, Throttle
* **ExhaustFlatshift**: Engine_RPM, Throttle
* **ExhaustAfterburn**: Engine_RPM, Throttle

## Event Creation Notes

For each event, pay attention to this section (bottom-right corner when selecting **Master**).

In particular, look at `Min & Max Distance`.  
This parameter defines how far away your sound can be heard.

Another important field is `Max Instances`.  
Set this for Exhaust and TurboBOV events to avoid wasting channels.  
Usually, 6–7 instances are enough.

![sounds_fmod_event_settings.png](../Images/Sounds/sounds_fmod_event_settings.png)

You can apply any effects to any tracks inside your event.  
However, **never** add or remove groups in Routing. FMOD is very picky here, and your sounds may simply stop working.

## Event Routing

> [!IMPORTANT]
> This step is mandatory. Without it, your sounds may not be audible or may ignore volume settings.

Before building sound banks, you need to assign your events to the correct groups.

This is done in the **Mixer** window, available via the shortcut `Ctrl + 2` or `Window -> Mixer`.

On the right side, in the routing tab, you’ll see a list of groups.  
This is where you assign your events.

![sounds_fmod_routing.png](../Images/Sounds/sounds_fmod_routing.png)

It’s straightforward: each event type is assigned to its corresponding group.  
The sound type matches the group it should be assigned to.

[Earlier](#sound-types), the supported sound types were already described.  
You can also usually tell by the event name itself.

For example, everything related to `Engine` (EngineRPM, EngineLimiter) goes into the `Engine` group, exhaust sounds go into `Exhaust`, and so on.

## Creating a Sound Bank

You can assign as many events to a sound bank as you want.  
You might add 10 different engine sounds and 10 different turbos, or just one sound of each type.

There are no hard limits here. Do what’s convenient — just avoid creating tons of banks with a single sound, or one massive bank with hundreds of sounds.

Sound banks are created in the `Event Editor` window.  
This is the main window, but if you closed it, you can reopen it via `Ctrl + 1` or `Window -> Event Editor`.

Go to the `Banks` tab, right-click, choose `New Bank`, and name it.

![sounds_fmod_bank_create.png](../Images/Sounds/sounds_fmod_bank_create.png)

To add events, switch to the `Events` tab, select the desired events, right-click, then choose  
`Assign to Bank -> Browse -> <bank name>`.

After that, the bank can be [built](#building-sound-banks).

![sounds_fmod_bank_assign.png](../Images/Sounds/sounds_fmod_bank_assign.png)

## Building Sound Banks

To build, press `F7` or go to `File -> Build`.  
The finished sound bank will appear in `Fmod/Build/Desktop`.

> [!IMPORTANT]
> Before importing the sound bank into Unity, make sure to export GUIDs.  
> This is only required if you added new events.

To export GUIDs, go to `File -> Export GUIDs...`.  
The resulting **GUIDs.txt** file will be located in `Fmod/Build`.

To build a sound pack for Kino, you **must** have both **GUIDs.txt** and the **.bank** file.  
Copy these files into your **Content SDK** folder next to `__meta`.

## Preparing Sounds for Kino

Once you’ve created events, routed them correctly, added them to a sound bank, and built it — along with GUIDs.txt — you can move on to  
**[creating a sound pack for Kino](CustomSounds_EN.md#creating-a-pack)**.