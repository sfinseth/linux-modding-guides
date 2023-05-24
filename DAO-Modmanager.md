# Getting DAO-Modmanager working on Linux with Steam DA:O Ultimate

In order to make setting up wine prefixes easier, I used Lutris for my DAO-Modmanager prefix.

My first attempt I used the same pfx for both the game and Modmanager, but that made the game unable to start so I
did the whole thing again with a separate prefix for Modmanager.

Step by step:
1. Install DA:O Ultimate Edition through Steam
2. Start up the game and start a new game to ensure all files are correctly created (Only required if you're doing a fresh install, if you already ran the game before you're good here)
3. Download DAO-Modmanager from [Nexusmods](https://www.nexusmods.com/dragonage/mods/277)
4. Extract Modmanager to a known path (I used `~/Games/DAO-ModManager/`)
5. Open up Lutris and Add a new game using the `Add locally installed game` option

I used these settings

## Game info tab
* Name: DAO Modmanager
* Runner: Wine (Runs Windows games)

## Game options tab
Replace `<username>` with your username (type `whoami` and hit enter in a terminal to get your username)
* Executable: `/home/<username>/Games/DAO-Modmanager/DAO-Modmanager.exe`
* Working directory: `/home/<username>/Games/DAO-Modmanager/`
* Wine prefix: `/home/<username>/Games/DAO-Modmanager/`
* Prefix architecture: `Auto (default)`

## Runner Options and System options tabs
* Left at my default settings
* Hit `Save` in the upper right corner of the Lutris Window

Now run `DAO Modmanager` from Lutris and let it set up the prefix

## Configuring DAO Modmanager to work

Once DAO Modmanager is started up in our new prefix we need to ensure it can find all the correct DA:O folders. This assumes that your steam library is set to the default settings - if you have other settings change the part that is `\home\<username>\.local\share\` to reflect this. If your steam library is on another drive under `/mnt/disk1` that part would be `Z:\mnt\disk1\`.

Again, `<username>` should be replaced with your username. (`whoami` in a terminal to get it)

* Go to options tab and change these values under `Dragon Age: Origins` header:
1. Dragon Age Folder: `Z:\home\<username>\.local\share\Steam\steamapps\compatdata\47810\pfx\drive_c\users\steamuser\Documents\BioWare\Dragon Age`
2. Settings Folder: `Z:\home\<username>\.local\share\Steam\steamapps\compatdata\47810\pfx\drive_c\users\steamuser\Documents\BioWare\Dragon Age\Settings`
3. AddIns Folder: `Z:\home\<username>\.local\share\Steam\steamapps\compatdata\47810\pfx\drive_c\users\steamuser\Documents\BioWare\Dragon Age\AddIns`

* Then change these values under the `Program Path` section: (These are only necessary if you want to start DAO from the mod manager or access the console in game)
1. DAO_exe: `Z:\home\<username>\.local\share\Steam\steamapps\common\Dragon Age: Origins - Ultimate Edition\bin_ship\daoorigins.exe`
2. DAO_Config_exe: `Z:\home\<username>\.local\share\Steam\steamapps\common\Dragon Age: Origins - Ultimate Edition\bin_ship\DAOriginsConfig`
3. DAO_Toolset_exe: `Z:\home\<username>\.local\share\Steam\steamapps\common\Dragon Age: Origins - Ultimate Edition\bin_ship\DragonAgeToolset.exe`

Congratulations, you're done setting things up and can start installing mods.

## Installing mods

1. Go to [Nexusmods](https://www.nexusmods.com/dragonage/mods) and find mods you like - I'll use [Advanced Tactics](https://www.nexusmods.com/dragonage/mods/181) as an example here
2. Take your downloaded `*.dazip*` file and move it to `/home/<username>/Games/DAO-Modmanager/mods/dazip`
3. Open up DAO Modmanager from Lutris and it should show in the list of "mods in mods folder" and you can right click to install
4. Launch the game and enjoy your modded experience
