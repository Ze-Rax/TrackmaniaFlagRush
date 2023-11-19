# Mapping Guide

Mapping for FlagRush is quite different compared to mapping for modes like regular TimeAttack,
Rounds, etc. There are specific requirements that have to be met for the map to work in the mode.



## 1. Preparations

Download the mapping resources and place the contents of the "GameClient" folder into your gamedata folder usually located at `My Documents/Trackmania` or `My Documents/Trackmania2020`. This installs the required MapType-script and items you need to create maps for FlagRush. The items are also available ingame in the [official FlagRush club](https://www.trackmania.com/clubs/42/items/329884).



## 2. Setup the Map with the MapType-Script

1. Open the Advanced map editor.
	- FlagRush maps cannot be created in the simple map editor, as you cannot place the required items and select to correct MapType
2. At bottom right, select "Map Options" to open a popup menu. (Crossed wrench + screwdriver icon)
3. Click the first button: "Set Map Type"
4. Select "FlagRushArena" from the Map type-field
	- If the MapType is not at the list, select "Pick from file" and point to the `FlagRushArena.Script.txt` located in your gamedata folder (`Scripts/MapTypes/FlagRushArena.Script.txt`).
5. Click "OK" to confirm your selection and close the dialog.
6. The editor may warn you about the map containing metadata and ask you if you want to keep it or clear it. You can usually clear it without hesitation, but keeping it will also not cause any issues.



## 3. Landmarks

### Team Landmarks (Spawns and Bases) (Required)

Each team tries to score the flag at the base of the opponent team while defending their own base. This means that the base of Team 1 should be on the same side as their spawn.

Each team needs exactly one spawn (any "Start" block) and one or more nases (any "Finish" block). There have to be the same amounce of bases for both teams.

You need to assign each team to the spawns and bases by using the "Edit Block Properties"-tool (See [Configuring landmarks](#4-configuring-landmarks)).

### Flag Spawns (Required)

Flag spawns are designated checkpoints that represent potential flag spawns. Any checkpoint in the game can be used as a flag spawn, but we generally recommend using the provided FlagRush flag spawn items (small, flag, circular, glowing items). There needs to be at least one flag spawn, but you can add as many additional flag spawns to your map as you like. It is recommended to keep it somewhere in the range of 3-5 flag spawns.

The order at which flags are spawned is random. Only the initial flag spawn that is used to spawn the first flag of a round is explicitly set in the map as the "Default Flag Spawn". Flag spawns are configured by using the "Edit Block Properties"-tool (See [Configuring landmarks](#4-configuring-landmarks)).

### Global Reset Trigger (Required)

The "Global Reset Trigger" is a small black cube item. It is required for technical reasons and there has to be exactly one such trigger present on a FlagRush map. It should be placed somewhat close to the center of the map.

### Podium (Required)

A podium has to be placed somewhere on the map. The podium is an official item provided by Nadeo in the game.

### Out of Bounds Trigger (Optional)

You can set "Out of Bounds"-triggers in the map to automatically unspawns players that leave the playable area of the map. When a player crosses such a trigger, they will immediately be unspawned and the flag is dropped at the "last safe position", i.e. the last position where at least 3 of his wheels thouched the ground.

Any checkpoint, including custom created ones can be used for "Out of Bounds"-triggers. We also include a 1x1 block sized horizontal plane with the other FlagRush items that can be used as such. For more complex shapes or bigger areas it might be more benefitial to create your own custom trigger using the ingame mesh modeler.

"Out of Bounds"-triggers are configured by using the "Edit Block Properties"-tool (See [Configuring landmarks](#4-configuring-landmarks)).



## 4. Configuring Landmarks

Every landmark is initialized in an "Unused"-state which makes the gamemode ignore it. To configure the landmarks, use the "Edit Block Properties"-tool in the editor. This tool can be found in the toolbar of the mapeditor as an icon showing a cube with a gear in front of it. Now you can click on individual landmarks (checkpoint, starts, finishes) to configure them. After selecting a landmark, a context window will open on the right side of the screen to configure the selected landmark.

### Configuring Flag Spawns

Select the checkpoint that should be used as a flag spawn. In the context menu on the right side click the "Flag Spawn" button. The checkpoint is now already registered as a flag spawn. Repeat this for every flag spawn on the map.

Additionally, exactly one flag spawn on the map has to be configured as the "Default Flag Spawn" (See [Landmarks / Flag Spawns](#flag-spawns-required)). To do so, enable the "Default Flag Spawn" toggle button for one of the configured flag spawns.

### Configuring Spawns

Select the start block that should be used as a spawn. In the context menu on the right side click the button for the team that should be spawned at the given start. There has to be exactly one spawn for each team.

### Configuring Bases

Select the finish block that should be used as a base. In the context menu on the right side click the button for the team that should defend the given base. The has to be at least one base for each team and the same amount of bases per team.

### Configuring Out of Bounds Triggers

Select the checkpoint that should be used as an out of bounds trigger. In the context menu on the right side click the "Out of Bounds Trigger" Button

### Configuring the Global Reset Trigger

The global reset trigger does not have to be configured explicitly. It can just be left in the "Unused" state.

### Unused Landmarks

You can remove the functionality from a landmark again after configuring it. To do so, select the given landmark and in the context menu on the right side click the "None" button.

Additionally, multilap blocks currently have no function in the gamemode and can not be used for any of the above mentioned functions.



## 5. Team Colors

You can customize the team colors if you want them to be different from the default "blue versus red" FlagRush colors. This can be especially useful if you want to go for a different color theme on your map in general.

To ensure good visibility of the colors and consistency in our UI, we only allow changing the hue. This means grayscale and shaded team colors are not possible.

The change the colors, click the Flag icon in the toolbar of the map editor. This opens a window in the center of your screen where you can select the hues for both teams individually. You can also reset the colors to the default FlagRush colors with the respective "Reset to Default" buttons, which will make the mode use the default blue and red colors.

Note that due to the usage of gradients in our UI, the ingame visuals of the selected colors could look slightly different than expected. The car skins for the teams will be selected according to the hues of the teams automatically.



## 6. Validation

When you have placed all the required landmarks and configured them appropriatly, then the map will automatically be valid; there is no need to drive the map and clicking the green validation flag won’t even have any effect. If your map is still invalid and you don’t know why, then you can click on the red validation flag in the bottom right to get an error message telling you what requirements are not fullfilled.



## 7. Optional FlagRush name tag

By convention we use the following tag to prefix our FlagRush maps to make visually appear as such:

`$s$22e[$fffFlagRush$e22] $z`

You may adjust the colors of the brackets (`[]`) to the team colors used on the map. It is recommended to keep the map name after the FlagRush tag relatively clean so it can be read easily ingame.