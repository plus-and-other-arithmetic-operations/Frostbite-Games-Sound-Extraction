# How to dump sounds from NFS 2015 & Other Frostbite engine games - a quick walkthrough

***

## Preface

Big thanks to a certain forum & [NicknineTheEagle](https://github.com/NicknineTheEagle) for the scripts/ initial methods and emjayy for explaining it to someone in the SRP discord - their messages allowed me to understand the process better and clarify it for other people/do it myself. This method should work for other frostbite 2/3 games, should you be interested in giving it a shot.

## Prerequisites

You will need:

* [Python 3+;](https://www.python.org/downloads/)

* [NicknineTheEagle's frostbite scripts;](https://github.com/NicknineTheEagle/Frostbite-Scripts) 

* [NFSMW-Correct Car Sound Mod+Tool (most recent version);](https://nfsmods.xyz/mod/1398)

* A NFS 2015 Copy.

## Dumping the game

* Install Python 3 (64 Bits);

* Unzip the dumper files into a new folder;

* Open dumper.py with IDLE, python's GUI.

Inside you'll quickly find the lines you need to change - adjust `gameDirectory` to your game directory (should be `C:\Program Files (x86)\Origin Games\Need For Speed`) and adjust `targetDirectory` to your target directory (any will work).

![Image](https://files.catbox.moe/eikrh7.png)
>Highlighted in yellow are the fields you need to replace with your game/desired target directory. (I used an obsolete version of the dumper - yours shall not differ too much.)


![Image](https://files.catbox.moe/79t9ew.png)
> Save the script and press F5 or Run > Run Module 


Now you just need to wait for the script to run. (Took me roughly 45 mins)

## Identifying the sounds

After you've dumped the game, head over to `...\bundles\ebx\audio\cars\carengine` - this is where you'll find the audio files for each vehicle present in the game. After you picked a vehicle, open the `octanedata` folder, and copy the whole address.

**NOTE: IF A ´ocatanedata´ FOLDER DOESN'T EXIST, THIS METHOD WILL NOT WORK FOR EXTRACTING THE SOUNDBANKS OF THE CHOSEN VEHICLE.**

+ Open `ebxtottext.py` and place the address copied earlier in the `inputFolder` field.

+ The `dumpDirectory` field is self explanatory - should point to your dump directory. More explicitly, the targetDirectory specified in the dumper is the same as the dumpDirectory to be specified here.

+ The `targetDirectory` field corresponds to the folder where you want to save your .txt files.

+ The `inputFolder` field corresponds to the path to the `octanedata`, which is where the audio files you want to extract are. This path is relative to the ebx folder.

![Image](https://files.catbox.moe/0vwpy2.png)
>The fields in my case.

![Image](https://files.catbox.moe/79t9ew.png)
> Save the script and press F5 or Run > Run Module 

## Converting the sounds into a useable format

After the script finishes its execution, you should head over to targetDirectory. Once there, you will notice the soundfiles in a .gin format. In order to convert them, there's an old tool (used in previous NFS titles) which is able to decode this format and convert it to .wav.

Open the downloaded files and extract the gin decoder folder, found in
`Correct Car Sound+Tool Kit V3.5.rar\Correct Car Sound+Tool Kit\NFS Sound Mod Toolkit\GIN DECODER (Any NFS)\`

Drag the .exe file in that folder to the directory where the .gin files are, and drag them invidually to the .exe file, in order to execute the program.

If every step was followed correctly, you should now have your samples in a useable format.