![FlagRush Logo](Assets/png/mark.png)

**`FlagRush`** is a Trackmania gamemode, where two teams compete in an arena to capture a flag and bring it to the opposing team base. The mode plays best with a team size of 4 players per team.

# Maps

## Creating maps for the mode

An explanation on how to create map for the FlagRush gamemode can be found in the [Mapping guide](./Mapping%20guide.md).

## Download existing maps for the mode

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
	- The gamemode behaviour can be customized with settings that are applied through the match settings file, see [Mode settings documentation](./Mode%20settings.md).
4. Start the server:

Linux:
```bash
./TrackmaniaServer /game_settings=MatchSettings/FlagRush.MatchSettings.txt /dedicated_cfg=dedicated_cfg.txt
```

Windows:
```powershell
TrackmaniaServer.exe /game_settings=MatchSettings/FlagRush.MatchSettings.txt /dedicated_cfg=dedicated_cfg.txt
```

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