## **Sound Mods & Audio Overriding**
### Some of the terms and their meanings in this article;
* "AudioSelectionStrategy" ("sequential" or "random"): Selection strategy for multiple override samples.
If you have more than one sounds, you can choose "random"
* Mod.json: mod_info.json is a required file that informs the game engine how to set up and use a mod. You can find examples in this text.
* Audio Event IDs: Every event has different IDs.
In order for the game to choose the sound it should play at that moment, it must first know its ID.
And so do you, to start to change them, you must identify the exact sound first.

## • How to make sound mods? Useful for simple ones. 
***There may be another one for complicated TitanOS, Announcher kind of stuff.***

First you need to identify the exact sound. There's a command for this: **"ns_print_played_sounds 1"**
It will show all the "audio events" that are happening at that moment on the console. 

For example, when you use your Grapple: **"pilot_grapple_fire"** or when you don't want to change that
sound but the impact sound, it would be something like this: **"concrete_grapple_impact_1p_vs_3p"** or
**"solidmetal_grapple_extract_1p_vs_3p"**, or maybe: **"dirt_grapple_impact_1p_vs_3p"**

There is something important here, as you can see these all starts with "concrete, solidmetal, dirt" etc.
All weapons and boosts have different events IDs on different surfaces.
That's why you must identify the exact event and that's why this command is very useful.

## • It's time to make the mod itself.
When you successfully identified your event, it's time to start making it.

* Mod folder must contain "audio" folder and "mod.json"
If you don't know how to make a mod.json, you can just download one of the sound mods and edit it.

**Example of a mod.json:**
```
{
  "Name": "MOD NAME HERE",
  "Description": "DESCRIPTION HERE",
  "Version": "1.0.0",
  "LoadPriority": 0
}
```

* • **An example screenshot:**
>![modjson](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/mod.json.png)

***Note: Version number is not important if you don't want to release the mod publicly.***

## • Audio Folder
* **Audio Folder example:**
>![audiofolder](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/folderexample.png)

**Audio folder must contain your audio files as WAV format and folder name must be the Event ID.**

### **For example based on Rwyn's Kraber reload sound mod.**
 Here is weapon_kraber_reload_magin is Kraber's reload sound ID, you will use whatever the sound you want to replace:

* **weapon_kraber_reload_magin** (folder, your wav file must be in it)
* **weapon_kraber_reload_magin.json** (don't forget to edit)
* **weapon_kraber_reload_magout** (folder, your wav file must be in it)
* **weapon_kraber_reload_magout.json** (don't forget to edit)

**And also these .json files should be edited too. It must contain "EventID" and "AudioSelectionStrategy"
Example:**
```
{
	"EventId": [ "weapon_kraber_reload_magin" ],
	"AudioSelectionStrategy": "sequential"
}
```

**An example screenshot of an EventID Json file:**
>![EventIDJson](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/eventmodjsonexample.png)
