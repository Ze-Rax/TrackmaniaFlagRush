# ![FlagRush Logo](Assets/png/mark.png)

*FlagRush* is a community made Trackmania gamemode, in which two teams compete in an arena to capture a flag from a flagspawn near the center of the map and score it in the base of the opposing team. The mode is recommended to be played with balanced teams of about 4 players each.

## Where to play?
As of today, we're hosting a couple of public server in the [Official Trackmania FlagRush Club](https://www.trackmania.com/clubs/42) in game. You are free to join and casually play with your friends or with other players that happen to be present.

If you want to host your own server, the following section explains how to set up a server.

## Server How-to
Setting up a dedicated server with FlagRush is not much more complicated than setting up a server with a regular official gamemode. This guide will not go into detail about how to set up regular server, so please refer to [this wiki](https://wiki.trackmania.io/en/dedicated-server) for more details.

To host the *FlagRush* gamemode on your dedicated server you have to add the necessary script files to it. The script files are included in this repository. We recommend downloading our dedicated server resources from the assets sections of the [latest release](https://github.com/Ze-Rax/TrackmaniaFlagRush/releases/latest), where an appropriately named zip-file should be available. Simply Extract its content into the `UserData` directory of your dedicated server.

> ℹ️ If you want to use the current development state of the gamemode, you may also clone or download the repository directly and copy the contents of the [`DedicatedServer`](https://github.com/Ze-Rax/TrackmaniaFlagRush/tree/dev/DedicatedServer) directory to your dedicated server instead. The development branch should be stable.

With the dedicated server resources added to your server, you can now adjust the server configuraiton to start the server with the *FlagRush* gamemode. To do so, you can simply adjust an existing match settings configuration or create a new one and set the script name to our gamemode.

```
<?xml version="1.0" encoding="utf-8" ?>
<playlist>
	<gameinfos>
		<script_name>Modes/TrackMania/FlagRush.Script.txt</script_name>
	</gameinfos>

	<!-- Other configuration... -->
</playlist>
```

You also need to provide at least one valid *FlagRush* map for the server to start. A [curated list](https://trackmania.exchange/mappackshow/1155) of *FlagRush* maps can be found on ManiaExchange.

The gamemode exposes an extensive list of settings to adjust several aspects of the gameplay experience. These can also be adjusted in the match settings configuration file. Refer to the documentation for a [list of the available settings together with their description](./Documentation/Mode%20settings.md).

> ℹ️ We provide a simple default configuration and a map in the dedicated server resources that should work out of the box: [`FlagRush.MatchSettings.txt`](./DedicatedServer/Maps/MatchSettings/FlagRush.MatchSettings.txt). You may use it when starting your server or adjust it to your liking.

## Maps
A [curated list](https://trackmania.exchange/mappackshow/1155) of *FlagRush* maps is available on ManiaExchange. A list of all compatible maps on ManiaExchange can be found [here](https://trackmania.exchange/mapsearch2?query=maptype%3A+flagrusharena).

Additionally, you can also create your own maps. A detailed [Mapping Guide](./Documentation/Mapping%20guide.md) can be found in the documentation.

## Community
Join us in our [Discord Server](https://discord.gg/J6ApdyRqEZ)! Also join our [Trackmania FlagRush Club](https://www.trackmania.com/clubs/42).

Mode developed and managed by the *FlagRush*-Team:
- Ze-Rax
- Reaby
- Geekid
- Rxelux

The project is licensed under the [MIT License](LICENSE).
