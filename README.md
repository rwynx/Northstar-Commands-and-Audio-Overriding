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

## • STEP 1

First you need to identify the exact sound. There's a command for this: **"ns_print_played_sounds 1"**
It will show all the "audio events" that are happening at that moment on the console. 

For example, use your Grapple and open the console the ID will be **"pilot_grapple_fire"** this one is an easy one, but there are some other tweaks too.
### A console example:
> ![audioeventexample](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/audioeventeample.png)

### All weapons, boosts, tacticals have different events IDs on different surfaces. That's why you must identify the exact event/s. Impact examples based on Grapple:
* Concrete impact: **"concrete_grapple_impact_1p_vs_3p"**
* Solidmetal impact: **"solidmetal_grapple_extract_1p_vs_3p"**
* Dirt impact: **"dirt_grapple_impact_1p_vs_3p"**
* Wood impact: **"wood_grapple_impact_1p_vs_3p"**

**NOTE:** "ns_print_played_sounds 1" will show you every event ID. Not just in-match ones.
* For example the sound when you move the cursor to an option it will be **"menu_focus"**, and clicking sound will be **"menu_accept"** or main menu music **"mainmenu_music"**
* After every sound, you can check the console to **identify** it.
* These are just couple of them, you can find any **EventID** and change them with the method I will explain here.

## • STEP 2
When you successfully identified your event and have the audio file/s ready. It's time to making it.

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
>![modjson](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/eventjsonexample.png)

***Note: Version number is not important if you don't want to release the mod publicly.***

## • Audio Folder
* **Audio Folder example:**
>![audiofolder](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/audiofolder2.png)

***Audio folder must contain your audio files as WAV format either "48000hz" or "44100hz" sample rate and folder name must be the Event ID.***

### **For example let's say we are making a Grapple sound mod;**
 
* **event_id_here** (folder, your .wav file must be in it)
* **event_id_here.json** (don't forget to edit)

**JSON files must contain "EventID" and "AudioSelectionStrategy"**
* Example .json based on this imaginary mod:
```
{
	"EventId": [ "pilot_grapple_fire" ],
	"AudioSelectionStrategy": "sequential"
}
```

**Screenshot version;**
>![EventIDJson](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/grappleeventexample.png)


## **After the whole process you should have these 2 files with the all additions I just explained.**
![ModFolderOverall](https://raw.githubusercontent.com/rwynx/audio-overriding-northstar/main/Images/ModFolderOverall.png)

# • Creating Your Sound
You can either use online web tools or Audacity (or any other sound editor software)
Set your sample rate to either 48k hz or 44.1k hz. Export your track as WAV format and make sure there is no metadata in the file. 

## • Installation 
* Basic methods apply.
* Once you are done with the mod, copy or drag the folder (which contains audio folder and mod.json) to "Titanfall 2/r2Northstar/Mods" and that's all.
