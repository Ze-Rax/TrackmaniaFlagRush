![FlagRush Logo](Assets/logo_nobackground.png)

**FlagRush** is a Trackmania gamemode where two teams compete in an arena to capture a flag and bring it to the enemy base.

## How to use

1. Setup a dedicated server. ([Tutorial](https://forums.ubisoft.com/showthread.php/2242192-Tutorial-Trackmania-2020-Dedicated-Server))
2. Clone the repository:
	-	If you have `git` installed: `git clone https://github.com/Ze-Rax/TrackmaniaFlagRush`
	- Manual Download: [Download Link](https://github.com/Ze-Rax/TrackmaniaFlagRush/archive/refs/heads/main.zip), then extract the zip archive.
3. Place the `Scripts`, `MapTypes` and `Modes` folders into your dedicated server's `UserData` folder.
4. In `UserData/Maps/Campaigns/tracklist.txt` replace the `<gameinfos>` section to include the FlagRush gamemode:
```
	<gameinfos>
		<game_mode>0</game_mode>
		<script_name>TrackMania/FlagRush.Script.txt</script_name>
	</gameinfos>
```
5. Make sure you've set up the mode settings and maps as you wish. Once the server starts up, you should now be able to play FlagRush!

## Community

Join us in our [Discord Server](https://discord.gg/J6ApdyRqEZ)!

The project is licensed under the [MIT License](LICENSE).