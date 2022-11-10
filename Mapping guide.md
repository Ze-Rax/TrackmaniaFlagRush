# Mapping Guide

Mapping for FlagRush is quite different compared to mapping for modes like regular TimeAttack,
Rounds, etc. There are specific requirements that have to be met for the map to work in the mode.

## 1. Preparations

Download the mapping resources and place the contents of the `GameClient` folder into your gamedata folder usually located at `My Documents/Trackmania`, this installs the needed MapType-script and items you need to create maps for FlagRush.

## 2. Setup the map with the MapType-script

1. Open `Advanced map editor`.
2. At bottom right, select `Map Options` to open a popup menu. (Crossed wrench + screwdriver icon)
3. Click the first button: `Set Map Type`
4. Select `FlagRushArena` from the Map type-field
   - If the type is not at the list, select `Pick from file` and point to the `FlagRushArena.Script.txt` located in your gamedata folder (`Scripts/MapTypes/FlagRushArena Script.txt`).
5. The editor may warn you about the map containing metadata and ask you if you want to keep or clear it. You can clear it without hesitation, but keeping it will also not cause any issues.
6. Click `OK`

## 3. Required Landmarks

### Team landmarks

Each team tries to **defend** flag scores at their `Team Base`, and **score** the flag at the other team. This means:

  - `Team 1` wants to score at `Team 2`'s bases
  - `Team 2` wants to score at `Team 1`'s bases

This means that the `Team 1 Base` should be on the same side as the `Team 1 Spawn`.

Each team needs exactly one `Team Spawn` (any `Start` block) and one or more `Team Base` (any `Finish` block). There have to be the same amounce of `Team Bases` for both teams.

You need to assign each team the `Spawn` and the `Base` by using the `Edit Block Properties`-tool (See [Configuring the landmarks](#configuring-the-landmarks)).

### Flag spawns

The `Flag Spawn` is a green, semi-transparent, spehere-shaped item with no collision that marks the location of where the Flag may spawn. Multiple flag spawns are allowed but at least one has to be present. Additionally, one of the flag spawns has to be set as the `Default Flag Spawn` using the `Edit Block Properties`-tool (See [Configuring the landmarks](#configuring-the-landmarks)).
Technically any `Checkpoint` block can be used as a `Flag Spawn`, but it's recommended to use the provided item for it's point-symmetrical nature which makes it accessible from each direction the same way.

The mode has two options for how flag spawns are chosen in-match; One will force only the `Default Flag Spawn` to be used, and the other will choose a random `Flag Spawn` among all `Flag Spawns` (including the `Default Flag Spawn`). Additionally, the first flag in each round will always spawn at the default `Defautl Flag Spawn`.

### Player reset

The `Player Reset` is a small, gold, sphere-shaped item that is used to make sure the gamemode can register a player crossing a `Flag Spawn` or `Base` at any time in the match. This has rather complicated techinical reasons. Just place exactly one somewhere roughly near the center of the map.

### Configuring the landmarks

When you placed all required landmarks, go back to the `Edit Block Properties`-tool (`Block with cogwheel` icon in the `map editor toolbar`) and select the relevant options for each:

  - For `Checkpoints` that should be used as `Flag Spawns`, select `Flag Spawn`.
  - For the `Flag spawn` that should be used as the `Default Flag Spawn`, set it as `Flag spawn` first, then toggle the `DefaultFlagSpawn` toggle button.
  - For `Start` blocks that should be used as `Spawn`, select the according team (`Team 1` or `Team 2`).
  - For `Finish` blocks that should be used as `Bases`, select the according team (`Team 1` or `Team 2`).
  - Every landmark is initialized in an `Unused`-state which makes the gamemode ignore it. You can reset a a landmark to that state with the `None` option in the respective property editing menu. The `Player Reset` item shoud be in the unused state.

### Podium
The maptype requires you to place the official podium item somewhere on the map. The map will not be valid without the podium.

## 4. Validating

When you have placed all the required landmarks and configured them appropriatly, then the map will automatically be validated; there is no need to drive the map and clicking the green validation flag won’t even have any function. If your map is still invalid and you don’t know why, then you can click on the red validation flag in the bottom right; an error message should pop up, telling you what requirements are not fullfilled.


## 5. Optional FlagRush name tag

There’s a map name tag for your FlagRush maps - so they visually appear as FlagRush maps by name. The tag is:

`$s$44f「$fffFlagRush$f44」$z`

It is recommended to keep the map name after that clean (i.e., not too long and wide) so it can be read easily in game.