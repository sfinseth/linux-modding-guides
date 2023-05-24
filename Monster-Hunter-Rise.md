# Getting Monster Hunter: Rise to load mods

## Prerequisite: REFramework

REFramework is a requirement for all other mods for Monster Hunter: Rise/Sunbreak and you can get it from [Nexusmods](https://www.nexusmods.com/monsterhunterrise/mods/26).

Once it's downloaded, extract it and then the file `d8input.dll` needs to be placed in the install folder for the game. Easiest way to get there is to navigate to the game on Steam, right click it and under manage, click `Browse local files`.

Copy the file `d8input.dll` and paste it into the base of the Monster Hunter: Rise installation folder that opened when you clicked `Browse local files`.

Following this all that's left is to tell Steam to load the dll in addition to the game - to do this we use a custom launch option in steam.

Right click the game in Steam and select `Properties`. In the `General` section that opens by default there's an inut field for `LAUNCH OPTIONS` - in this field write: `WINEDLLOVERRIDES="d8input.dll=n,b" %command%` and you're done.

Now when you launch the game, REFramework should load and create a folder called `autorun` in your game folder. Any other mods you want to use can be placed in this `autorun` folder and that's all.

Some of my personal favourite mods are:
* [VIP Dango Tickets](https://www.nexusmods.com/monsterhunterrise/mods/92)
    * Causes all Dango to have a 100% activation rate when using a ticket.
*  [Randomized Hub Music](https://www.nexusmods.com/monsterhunterrise/mods/526)
    * Randomises the music played in the Hub so you're not always listening to the same music. Allows you to select which tracks to include/exclude 