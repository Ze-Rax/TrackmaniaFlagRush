![FlagRush Logo](Assets/png/mark.png)

**`FlagRush`** is a Trackmania gamemode, where two teams compete in an arena to capture a flag and bring it to opposing team base. Mode plays best with a team size of 4 players per team.

# Maps

We recommend starting with our officially reviewed mapppacks:
- Curated Mappack: https://trackmania.exchange/mappack/view/1155/flagrush-curated-map-pool
	- Maps which have been deemed to be of good quality by the players and developers
- Proving Grounds Mappack: https://trackmania.exchange/mappack/view/1151/flagrush-proving-grounds
	- Maps which are fully functional but not up to the quality expectations of the curated mappack (yet)

You can find other compatible maps on Maniaexchange:
- All FlagRush maps on TMX: https://trackmania.exchange/mapsearch2?mtype=FlagRushArena

# Server How-to

1. Setup Trackmania2020 dedicated server. ([Tutorial](https://wiki.trackmania.io/en/dedicated-server/Setup/Windows))
2. Download gamemode: [main.zip](https://github.com/Ze-Rax/TrackmaniaFlagRush/archive/refs/heads/main.zip), then extract the zip archive.
	- or clone the repository, if you have `git` installed: \
  	`git clone https://github.com/Ze-Rax/TrackmaniaFlagRush`
3. Place the contents of `DedicatedServer` folder into your dedicated server's `UserData` folder.
	- A minimal FlagRush matchsettings file is already included in `Map/MatchSettings/FlagRush.MatchSettings.txt` together with a map.
4. Start the server:

Linux:
```bash
./TrackmaniaServer /game_settings=MatchSettings/FlagRush.MatchSettings.txt /dedicated_cfg=dedicated_cfg.txt
```

Windows:
```powershell
TrackmaniaServer.exe /game_settings=MatchSettings/FlagRush.MatchSettings.txt /dedicated_cfg=dedicated_cfg.txt
```

# Mapping Guide

Mapping for FlagRush is quite different compared to mapping for modes like regular TimeAttack,
Rounds, etc. There are specific requirements that have to be met for the map to work in the mode.

## Preparations

Place the contents of `GameClient` folder into your gamedata folder usually located at `My Documents/Trackmania`, this installs the needed MapType-script and items you need to create maps for FlagRush.

## 1. Setup map with according MapType-script

1. Open `Advanced map editor`.
2. At bottom right, select `Map Options` to open a popup menu. (Crossed wrench + screwdriver icon)
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


Each team needs exactly one `Team Spawn` (any `Start` block) and one or more `Team Base` (any `Finish` block). This means that the `Team 1 Base` should be on the same side as the `Team 1 Spawn`.

You need to assign each team the `Spawn` and the `Base` by using the `Edit Block Properties`-tool. (`Block with cogwheel` icon in the `map editor toolbar`)

---

The `Flag Spawn` is a green, semi-transparent, spehere-shaped item with no collision that marks the location of where the Flag may spawn. Multiple flag spawns are allowed but at least one has to be present. Additionally, one of the flag spawns needs to be set as the `Default Flag Spawn` using the `Edit Block Properties`-tool.
Technically any `Checkpoint` block can be used as a `Flag Spawn`, but it's recommended to use the provided item for it's point-symmetrical nature which makes it accessible from each direction the same way.

The mode has two options for how flag spawns are chosen in-match; One will force only the `Default Flag Spawn` to be used, and the other will choose a random `Flag Spawn` among all `Flag Spawns` (including the `Default Flag Spawn`).

---

The `Player Reset` is a small, gold, sphere-shaped item that is used to make sure the gamemode can register a player crossing a `Flag Spawn` or `Base` at any time in the match. This has rather complicated techinical reasons. Just place exactly one somewhere roughly near the middle of the map.

---

When you placed all required landmarks, go back to the `Edit Block Properties`-tool and select the relevant options for each:

  - For `Checkpoints` that should be used as `Flag Spawns`, select `Flag`.
  - For `Start` blocks that should be used as `Spawn`, select the according team (`Team 1` or `Team 2`).
  - For `Finish` blocks that should be used as `Bases`, select the according team (`Team 1` or `Team 2`).
  - Every landmark is initialized in an `Unused`-state which makes the gamemode ignore it. You can reset a a landmark to that state with the `None` option in the respective property editing menu. The `Player Reset` item shoud be in the unused state.

## 4. Validating

When you have placed all the required landmarks and configured them appropriatly, then the map will automatically be validated; There is no need to drive the map and clicking the green validation flag won’t even have any function. If your map is still invalid and you don’t know why, then you can click on the red flag in the bottom right; An error message should pop up, telling you what requirements are not fullfilled.


## 5. Optional FlagRush name tag

There’s a map name tag for your FlagRush maps - so they visually appear as FlagRush maps by name. The tag is:

```
$s$44f「$fffFlagRush$f44」$z
```

It is recommended to keep the map name after that clean (i.e., not too long and wide) so it can be read easily in game.

# Community

Huge thanks to everyone who helped this project to become reality:

- `Geekid` - for ideas and contributing code
- `Reaby` - for ideas and contributing code
- `Rxelux` - for ideas and contributing code
- `RealSpace` - for maps, mapping tutorial and support, map management and ideas
- `Nalax` - for map management and mapping support
- `TuplaJ` - for mapping

Join us in our [Discord Server](https://discord.gg/J6ApdyRqEZ)!

The project is licensed under the [MIT License](LICENSE).