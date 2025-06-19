# Setting up ALBW for Archipelago

## Preface

If you came here to troubleshoot while joining or hosting a sync, I recommend switching to another game for that sync and troubleshooting later.

The setup is a little finnicky and the reason it doesn't work on your machine can have lots of different reasons.

You don't wanna be the person who is troubleshooting for an hour while the rest is waiting on you.

## Platform disclaimer

##### Windows

This guide should work flawlessly for any machine running Windows 10+.

##### Linux

For Linux, I recommend getting the `.tar.gz` version of Archipelago; this guide should work for that version. The `AppImage` version is more complex and I might make a guide for that in the future, but currently this guide will not work.

## What you need

- [ ] The latest version of [Azahar](https://azahar-emu.org/) ([GitHub releases](https://github.com/azahar-emu/azahar/releases))
- [ ] A decrypted The Legend of Zelda: A Link Between Worlds ROM of the North American release.
- [ ] All 3 files of the latest release of [albw-archipelago](https://github.com/randomsalience/albw-archipelago/releases) by randomsalience.
  - `A.Link.Between.Worlds.yaml` (you can have Archipelago generate a template yaml as well after setting up the other two)
  - `albw.apworld`
  - `albwrandomizer.zip`
- [ ] Some patience and perseverance.

## Setting up Archipelago

If you have somehow come to this guide and not already installed Archipelago, click [here](https://archipelago.gg/tutorial/) for in-depth guides on Archipelago and how to use it.

First you want to open the Archipelago data folder, by opening the Archipelago launcher and clicking on `Browse Files`. In there, you should have a bunch of folders and ArchipelagoXXXXXXXX.exe files.
The folders we are interested in are:

- `custom_worlds`
- `lib`
- `Players`

In `custom_worlds`, you simply drag and drop the `albw.apworld` file.

In `lib`, we want to extract the _contents_ of the `albwrandomizer.zip`. It should be a folder called `albwrandomizer`.

Finally, in `Players` you place the `A.Link.Between.Worlds.yaml` file. This yaml file contains your options, and you will want to adjust those, or at the very least change the Player name in there. I recommend [VSCode](https://code.visualstudio.com/) or [Notepad++](https://notepad-plus-plus.org/) for this.

<sub>You can name this file anything you'd like, it doesn't have to be A.Link.Between.Worlds.yaml, I'm just maintaining this name for the guide.</sub>

If you have done all this, Archipelago should be set up properly, and should look like the following outline:

<pre>
Archipelago
├─ custom_worlds
│  └─ albw.apworld
├─ lib
│  └─ albwrandomizer
│     ├─ __pycache__
│     └─ ...
├─ Players
│  └─ A.Link.Between.Worlds.yaml
└─ ...
</pre>

## Setting up Azahar

Now that you have Archipelago set up correctly, we can move on to setting up Azahar so that it's ready for ALBW.

Assuming you have Azahar installed properly, we want to set up 3 things to be able to play ALBW in Archipelago.

- Dumping a valid patchable ROM
- Creating a patch folder
- Turning on RPC server
- Duplicating your ROM (optional)

### Dumping a valid patchable ROM

This guide does not condone piracy, and as such will not help with finding illicit ROMs. Instead we will focus on dumping a legal game from 3DS hardware.

The ROM we need should be in the _North America_ region. If you already have a ROM, you can quickly see if it's of North American region by opening up Azahar and adding an application directory pointing to the ROM. Under "Region" it should say "North America", if it doesn't, you will need a different ROM.

##### Dumping and decrypting a ROM

There is a very in-depth guide [here](https://3ds.hacks.guide/dumping-titles-and-game-cartridges.html) that explains in detail how to dump a ROM and what you need, which I recommend you follow to the tee if you don't want to accidentally brick your 3DS. At the very bottom of the same guide [here](https://3ds.hacks.guide/dumping-titles-and-game-cartridges.html#encrypting-decrypting-a-cia-file), there is also a guide on how to decrypt ROMs. You have to follow these steps as well to be able to use it for Archipelago.

### Creating a patch folder

Assuming you now have decrypted North American version of ALBW in `.3ds` format, we can continue with creating a patch folder that you will need to randomize your game and connect to the Archipelago client.

To do so, you will need a `.apalbw` file.

##### Getting a .apalbw file

To get your `.apalbw` file, Archipelago will need to generate a seed. Again, I recommend doing this in a test gen or for a solo run before trying to do this while joining or hosting a sync, to avoid having to troubleshoot while other players are waiting on you.

If you are joining a sync, you can get this file from the host. Ask them for the zip file, or the `.apalbw` file inside the zip.

If you are doing a solo run or hosting a sync, we will first need to generate a seed. To do this, simply click on `Generate` in the Archipelago Launcher, and click on `Browse Files` after that and browse to the `output` folder. In there you will find a `AP_xxxxxxx.zip` file, which will contain your `.apalbw` file. If you instead got an error trying to generate, refer to the troubleshooting section below.

##### Creating a patch folder

Now that you have your `.apalbw` file, either drag your file onto the Archipelago Launcher, or click on `Open Patch` in the launcher. This will open a file select that will ask you to point to the patch (only if you clicked on "Open Patch"), and next another file select that will ask you to point to your ROM (only when doing this for the first time). After you did this, you will find a `AP_xxx...\_P#\_Player.zip` file next to your ROM file.

##### Loading your mod

Back in Azahar, click on `File > Open Azahar Folder`. In there, you will see folder named `load`, if you don't, create one. In the `load` folder, you will see a folder named `mods`, again if it's not there, create that as well.

In the `mods` folder, you will want to extract the _contents_ of the `AP_xxx...\_P#\_Player.zip` file we just made.

If done properly, it should look something like this:

<pre>
Azahar
├─ load
│  └─ mods
│     └─ 00040000000EC300
│        ├─ romfs
│        ├─ code.ips
│        └─ exheader.bin
└─ ...
</pre>

### Turning on RPC server

Azahar has an RPC server that allows the ALBW patch to connect to Archipelago. By default, it's turned off and it won't connect. To turn it on, simply go to `Azahar > Emulation > Configure > Debug` and `Enable RPC server`.

### Duplicating your ROM file (optional)

Azahar does not allow you to use `.3ds` files to play games, only `.cci` files, but we need a `.3ds` file to patch. As such, you might find it handy to duplicate your `.3ds` rom (copy > paste), and simply changing the file extension from `.3ds` to `.cci`. This works perfectly fine, and will allow Azahar to run the game.

If you have done all these steps correctly, you should be able to simply start the game in Azahar, and connect to your Archipelago sync. If working correctly, the Archipelago Client should say `Connected` and all the `Room Information` below. If you do not see `Emulator connected`, refer to the troubleshooting section below.

## Troubleshooting

### Generating exceptions

##### Exception: No world found to handle game A Link Between Worlds

If you get this error trying to generate, check if your Archipelago folder matches this outline:

<pre>
Archipelago
├─ custom_worlds
│  └─ albw.apworld
├─ lib
│  └─ albwrandomizer
│     ├─ __pycache__
│     └─ ...
├─ Players
│  └─ A.Link.Between.Worlds.yaml
└─ ...
</pre>

The location of the `albw.apworld` file and `albwrandomizer` folder are very specific, and need to be exactly in the places they are in the outline.

If your folder structure matches the outline, see if either the `.apworld` or `albwrandomizer` are outdated.

<sub>If you are trying to do this on Linux, please use the `.tar.gz` version of Archipelago instead of `AppImage`. This outline will _not_ work on the `AppImage` version.</sub>

### Azahar crashes

##### Playing ALBW after extracting into load/mods

If Azahar crashes when loading ALBW after extracting your mod folder into `load/mods`, follow these steps:

1. Make sure you used a valid ROM to patch your game. If the ROM was not decrypted, and of North American region, the patch will not work and instead crash Azahar.
2. Make sure you extracted to the correct location. See the "Loading your mods" section for an outline of how your folders should look like.
3. See if Azahar crashes even when removing the `00040000000EC300` folder from `load/mods`. If it does, you might want to troubleshoot Azahar instead.
4. See if any game loads in Azahar if you have any other games. If they don't, you might have screwed up your `load/mods` folder previously and corrupted Azahar's game data. You will need to delete your `%Appdata%/Azahar/nand/data` folder. This will delete all your save files so make sure to make a backup of this folder if you want to keep any save files.
5. If none of these steps worked, you can ask for further help in the Archipelago Discord at the channel `future-game-design > The Legend of Zelda: A Link Between Worlds`.

### Connecting to emulator...

Make sure you have enabled the RPC server in Azahar by going to `Emulation > Configure > Debug` and enabling RPC server.
