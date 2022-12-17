# Custom Northstar commands to change levels and stuff.

### Start a private match first and open the console, type this command: **sv_cheats 1** and to change values, replace the *"value"* with desired number.

## ✔️ Change your Titan's name:
**Command:** `script SetPersistentLoadoutValue( GetPlayerArray()[0], "titan", TITAN INDEX HERE (starts from 0), "name",                "Name Here" )`
*BE aware, if you have framework it will break this, since framework uses loadout name to store modded titan.*

## ✔️ Spawn a titan (useful for modders): 
**Command:** `script DevSpawnTitan()`
## ✔️ How to reset all your levels?
**Command:** `ns_resetpersistence` if this command doesn't work, try;
`script_ui seterrorhandler(void function() {})`

## ✔️ Change your levels & gen:

* **Weapon Level:**  `script AddWeaponXP(GetPlayerArray()[0], VALUE)`
Set **"value"** to 100000 to **max level** weapons. Must be **holding** weapons in a private match.

* **Titan Level:**  `script AddTitanXP(GetPlayerArray()[0], VALUE)`
Set **"value"** to 100000 to max level titans. Must be **in titan** in private match.

* **Pilot Gen:**  `script GetPlayerArray()[0].SetPersistentVar("gen", VALUE)`
Max **"VALUE"** is 127.
   
* **Set Pro Screen:**  `script GetPlayerArray()[0].SetPersistentVar( GetItemPersistenceStruct("WEAPON NAME") + ".proScreenKills", VALUE)`
Replace WEAPON NAME with name from the list below.

## ✔️ **Titanfall 2 Weapon List:**

### **Rifles**
* R201        //  mp_weapon_rspn101
* R101        //  mp_weapon_rspn101_og
* Hemlock        //  mp_weapon_hemlock
* Flatline    //  mp_weapon_vinson
* G2A5        //  mp_weapon_g2

### **SMGs**
* CAR        //  mp_weapon_car
* Alternator    //  mp_weapon_alternator_smg
* Volt        //  mp_weapon_hemlok_smg
* R-97        //  mp_weapon_r97

### **LMGs**
* Spitfire    //  mp_weapon_lmg
* L-STAR        //  mp_weapon_lstar
* Devotion    //  mp_weapon_esaw

### Snipers
* Kraber        //  mp_weapon_sniper
* Double Take    //  mp_weapon_doubletake
* Longbow DRM    //  mp_weapon_dmr

### Shotguns 
* EVA-8 Auto    //  mp_weapon_shotgun
* Mastiff        //  mp_weapon_mastiff

### Grenadier 
* SMR        //  mp_weapon_smr
* EPG        //  mp_weapon_epg
* Softball    //  mp_weapon_softball
* Cold War    //  mp_weapon_pulse_lmg

### Primary Pistols 
* Wingman Elite    //  mp_weapon_wingman_n
* Mozambique    //  mp_weapon_shotgun_pistol

### Secondary Pistol 
* RE-45        //  mp_weapon_autopistol
* P2016        //  mp_weapon_semipistol
* Wingman        //  mp_weapon_wingman

### Anti-Titan
* Charge Rifle    //  mp_weapon_defender
* MGL        //  mp_weapon_mgl
* Thunderbolt    //  mp_weapon_arc_launcher
* Archer        //  mp_weapon_rocket_launcher
