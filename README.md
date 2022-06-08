## **Sound Mods & Audio Overriding**
### Some of the terms and their meanings in this article;
* "AudioSelectionStrategy" ("sequential" or "random"): Selection strategy for multiple override samples.
If you have more than one sounds, you can choose "random" to randomize them, if you have only one sound, you can simply use "sequential"
* Mod.json: is a required file that informs the game engine how to set up and use a mod. You can find example template in this article.
* Audio Event IDs: Every event has different IDs.
In order for the game to choose the sound it should play at that moment, it must first know its ID.
And so do you, to start to change them, you must identify the exact sound first.

### Audio Type
* Use only WAV format and either "48000hz" or "44100hz" sample rate. 
* Check the last section of this article for more info and recommended tools.

***This article only contains info for simple ones. There may be another one for TitanOS, Announcher kind of stuff. Process is almost the same but more complicated.***

## • How to make sound mods? Useful for simple ones. 

First you need to identify the exact sound. There's a command for this: **"ns_print_played_sounds 1"**
It will show all the "audio events" that are happening at that moment on the console. 

For example, use your Grapple and open the console the ID will be **"pilot_grapple_fire"** this one is an easy one, but there are some other tweaks too.
### A console example:
> ![audioeventexample](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/audioeventeample.png)

### Some other examples: If you use grapple on a surface, the impact sound will be something else. (Just in case if you ever want to change them too.)
* Concrete impact: **"concrete_grapple_impact_1p_vs_3p"**
* Solidmetal impact: **"solidmetal_grapple_extract_1p_vs_3p"**
* Dirt impact: **"dirt_grapple_impact_1p_vs_3p"**
* Wood impact: **"wood_grapple_impact_1p_vs_3p"**

Like I said, all weapons and boosts have different events IDs on different surfaces.
That's why you must identify the exact event/s.

**NOTE:** "ns_print_played_sounds 1" will show you every event ID. Not just in-match ones.
* For example the sound when you move the cursor to an option it will be "menu_focus", and clicking sound will be "menu_accept" or main menu music "mainmenu_music"
* These are just couple of them, you can find any EventID and change them with the method I will explain here.

## • It's time to make the mod itself.
When you successfully identified your event, and i assume you have your sound file ready.

First of all, mod folder must contain "audio" folder and "mod.json"
If you don't know how to make a mod.json, you can just download one of the sound mods and edit, or just copy this template and edit it.

**Example of a mod.json:**
```
{
  "Name": "MOD NAME HERE",
  "Description": "DESCRIPTION HERE",
  "Version": "1.0.0",
  "LoadPriority": 2
}
```

* **An example screenshot:**
>![modjson](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/mod.json.png)

***Note: Version number is not important if you don't want to release the mod publicly.***

## • Audio Folder
* **Audio Folder example:**
>![audiofolder](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/folderexample.png)

**Audio folder must contain your audio files as WAV format either "48000hz" or "44100hz" sample rate and folder name must be the Event ID.**

### **For example based on Rwyn's Kraber reload sound mod.**
 Here is these 2 are Kraber's reload sound ID, you will use whatever the sound you want to replace:
 There are 2 different files in this case because the reload process consists of two parts. The mag comes "out" first and then goes back "in."
 
* **weapon_kraber_reload_magin** (folder, your wav file must be in it)
* **weapon_kraber_reload_magin.json** (don't forget to edit)
* **weapon_kraber_reload_magout** (folder, your wav file must be in it)
* **weapon_kraber_reload_magout.json** (don't forget to edit)

**And also these .json files should be edited too. It must contain "EventID" and "AudioSelectionStrategy"
Example of an (eventIDhere).json:**
```
{
	"EventId": [ "weapon_kraber_reload_magin" ],
	"AudioSelectionStrategy": "sequential"
}
```

**An example screenshot of an EventID Json file:**
>![EventIDJson](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/eventmodjsonexample.png)


## **After the whole process you should have these 2 files with the all additions I just explained.**
![ModFolderOverall](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/ModFolderOverall.png)

# • Creating Your Sound
* Recommended tool: Audacity

Open/Add your audio as a track to Audacity and set your sample rate to either 48000hz or 44100hz. In Audacity, select your entire track, open the effects dropdown menu, then click Change Speed. In the dialog set either Speed Multiplier to 0.918 or Percent Change to -8,200. After that, export your track as .wav and make sure you don’t add any metadata.

## • Installation 
* Once you are done with the mod, copy or drag the folder (which contains audio folder and mod.json) to "Titanfall 2/r2Northstar/Mods" and that's all.
