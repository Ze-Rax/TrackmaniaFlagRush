![FlagRush Logo](Assets/logo_nobackground.png)

**FlagRush** is a Trackmania gamemode, where two teams compete in an arena to capture a flag and bring it to opposing team base. Mode plays best starting with 3 vs 3 players.

# Server How-to

1. Setup Trackmania2020 dedicated server. ([Tutorial](https://forums.ubisoft.com/showthread.php/2242192-Tutorial-Trackmania-2020-Dedicated-Server))
2. Download gamemode: [main.zip](https://github.com/Ze-Rax/TrackmaniaFlagRush/archive/refs/heads/main.zip), then extract the zip archive.
   - or clone the repository, if you have `git` installed: \
  	`git clone https://github.com/Ze-Rax/TrackmaniaFlagRush`
3. Place the contents of `DedicatedServer` folder into your dedicated server's `UserData` folder.
4. Start the server:

Linux:
```bash
./TrackmaniaServer /game_settings=MatchSettings/flagrush.txt /dedicated_cfg=dedicated_cfg.txt
```

Windows: 
```powershell
TrackmaniaServer.exe /game_settings=MatchSettings/flagrush.txt /dedicated_cfg=dedicated_cfg.txt
``` 

# Mapping Guide

Mapping for FlagRush is quite different compared to mapping for modes like regular TimeAttack, 
Rounds, etc. There are specific requirements that have to be met for the map to work in the mode.

## Preparations

Place the contents of `GameClient` folder into your gamedata folder usually located at `My Documents/Trackmania`, this installs the needed MapType-script and Items you need to craft maps for FlagRush.

## 1. Setup map with according MapType-script

1. Open `Advanced map editor`.
2. At bottom right, select `Map options` to brind a popup menu
3. Click the first button: `Set Map Type`
4. Select `FlagRushArena` from the Map type-field
   - if the type is not at the list, select `Pick from file` and point to the `FlagRushArena.Script.txt` located at your computer.
6. Click `OK`

## 2. Required Landmarks

Each team tries to **defend** flag scores at their `Team Base`, and **score** the flag at the other team. This means:

  - `Team 1` wants to score at `Team 2`'s bases
  - `Team 2` wants to score at `Team 1`'s bases
  - `Team 1` wants to stop `Team 2` from scoring at `Team 1` base
  - `Team 2` wants to stop `Team 1` from scoring at `Team 2` base
  

Each team needs one `Team Spawn` (any Start block) and one or more `Team Base` (any Finish block). This means that the `Team 1` Base should be on the same side as the `Team 1` Spawn.

You need to assign each team the `Spawn` and the `Base` by using the `Edit Block Properties`-tool.

--- 

The `Flag Spawn` is a semi-transparent ball with no collision is an item that marks the location of the flag at the start of a round. Multiple flag spawns are allowed. One needs to be the Default Flag Spawn.

The `Default Flag Spawn` is required to be set on one flag spawn - if there’s just one spawn on the map, it still needs the marker. The mode has two options for flag spawns in-game; one will force only one spawn location to be used, and the other will choose randomly. If the former is selected, the Default Flag Spawn is used. Otherwise, it is ignored. 

--- 

The `Player Reset` is a smaller gold ball that is used to make sure player respawns work in a match. Just place exactly one somewhere near the middle of the map.

When you have these places, you got back to the `Edit Block Properties` menu and select the relevant option for each: `Flag` for the flag spawn, and `None` for the Players Reset item.

## 4. Validating

When you have placed all the required landmarks and configured them appropriatly, then the map will automatically be validated; There is no need to drive the map and clicking the green validation flag won’t even have any function. If you’re map is still invalid and you don’t know why, then you can click on the red flag in the bottom right; An error message should pop up, telling you requirements are not fullfilled.


## 5. Optional FlagRush name tag

There’s a map name tag for your FlagRush maps - so they visually appear as FlagRush maps by name. The tag is:

```
$s$44f「$fffFlagRush$f44」$z
```

It is recommended to keep the map name after that clean (ie, not long and wide) so it can be read easily in game.

## Community

Huge thanks to everyone who helped this project to become reality:

- `Geekid` - for ideas and contributing code
- `Reaby` - for ideas and contributing code
- `RealSpace` - for maps, mapping tutorial and ideas
- `TuplaJ` - for mapping

Join us in our [Discord Server](https://discord.gg/J6ApdyRqEZ)!

The project is licensed under the [MIT License](LICENSE).