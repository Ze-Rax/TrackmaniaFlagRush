# Gamemode settings

Server owners can adjust the behaviour of the gamemode to a certain extend by simply changing settings in the match settings file (sometimes also referred to as maplist) that is used when starting the server.

FlagRush provides a long list of settings to customize the experience to your liking, including settings to change the general match progression (timelimit, flag score limit, ...) or mid round gameplay (flag carrier penalties, collisions, ...).

## Match progression settings

These settings change how the general progression of a match works, i.e. how many maps or rounds to play, how long a round takes and more.

| Setting name                  | Type    | Default value | Description |
| ----------------------------- | ------- | ------------- | ----------- |
| S_NbMapsToWinMatch            | Integer | 1             | Number of maps to win a match. |
| S_NbRoundsToWinMap            | Integer | 2             | Number of rounds to win a map. |
| S_NbFlagsToWinRound           | Integer | 3             | Number of flags scored to win a round. Unlimited if <= 0.0 |
| S_RoundTimeLimitSeconds       | Integer | 360           | Round timelimit in seconds. Unlimited if <= 0.0 |
| S_UseOvertime                 | Boolean | True          | Use overtime. If the match is tied when the timelimit runs out, the round will go into overtime until a team scores the next flag. |
| S_UseWarmUp                   | Boolean | True          | Use warm up. At the beginning of the map players have to press the ready button for the match to start. If at least one player in each team is ready, a 60 second countdown starts after which the map starts. If all players are ready, a 5 second countdown start after which the map starts. |
| S_WarmUpWaitForApproval       | Boolean | False         | Wait for the approval of an admin for the warmup countdowns to start. Requires usage of ModeCommandsUI. |


## Gameplay settings

These settings change how the gameplay in a round behaves.

| Setting name                     | Type    | Default value | Description |
| -------------------------------- | ------- | ------------- | ----------- |
| S_UseCrudeExtrapolation          | Boolean | True          | Determines the method that is used by clients to extrapolate player positions. Settings this setting to False has caused major desync issues in the past and is therefore not recommended. |
| S_TrustClientSimu                | Boolean | True          | Whether to trust the physics simulation of the clients (players) or use serside physics simulation. Serverside physics simulation can cause teleporation on the client side, depending on their network connection to the server. |
| S_FlagDropStateDurationSeconds   | Real    | 8.0           | Duration in seconds that a dropped flag will stay dropped before being reset to a flagspawn. |
| S_FlagStealResistDurationSeconds | Real    | 1.0           | Duration in seconds in which the flag cannot be stolen after picking it up. |
| S_FlagSameTeamSteal              | Boolean | True          | Whether or not teammates can steal the flag from the flag carrier. |
| S_FlagStealResistanceOnTeamPass  | Boolean | False         | Whether or not to give flag steal resistance to the player when passing the flag between team members. |
| S_FlagCarrierFragile             | Boolean | True          | Whether or not the flag carrier should become fragile. |
| S_FlagCarrierAcceleration        | Real    | 0.66          | Acceleration coefficient for the flag carrier. |
| S_FlagCarrierControl             | Real    | 1.0           | Control ("Steering") coefficient for the flag carrier. |
| S_FlagCarrierAdherence           | Real    | 0.9           | Adherence ("Grip") coefficient for the flag carrier. |
| S_RespawnSpeedLimitKmh           | Real    | 30.0          | Maximum speed allowed for respawning. No limitation if <= 0.0. |
| S_RespawnDelayPerPlayer          | Real    | 1.0           | Respawn delay in seconds per player in a team: `Total respawn delay = S_RespawnDelayPerPlayer * Number of players in the team + 1.5 (spawn animation)`|
| S_DropFlagPickupPenalty          | Real    | 3.0           | Duration in seconds in which a player cannot pick up the flag after dropping it. (Other players can instantly pick it up.) |
| S_TeleportDetectionThreshold     | Real    | 8.0           | Maximum distance in meters that a player is allowed to teleport (lag) during one server frame before the flag is automatically dropped. Teleport detection is disabled for values <= 0 |
| S_UseCollisions                  | Boolean | False         | Whether or not to use physics based collisions between players. This setting is EXPERIMENTAL: Player collisions can feel and be weird and inconsistent. If enabled, server will also switch to server side simulation (See S_TrustClientSimu) and disable crude extrapolation (See S_UseCrudeExtrapolation). |
| S_ForceEnabledVehiclesCsv        | Text    | "" (blank)    | Forces the given list of vehicles to be enabled. Overrides the vehicle configuration of the map. Invalid values are ignored. Comma separated values, case insensitive and will be trimmed. Examples: `stadium,rally`, `Stadium, snow   , RaLlY` |

## Team settings

These settings change the appearance of the teams, including their names and color.

| Setting name                  | Type    | Default value | Description |
| ----------------------------- | ------- | ------------- | ----------- |
| S_Team1Name                   | Text    | "" (blank)    | Force team 1 name. Use default if blank. |
| S_Team1Hue                    | Integer | -1            | Force team 1 hue. Range [0, 359] or -1 for default. |
| S_Team2Name                   | Text    | "" (blank)    | Force team 2 name. Use default if blank. |
| S_Team2Hue                    | Integer | -1            | Force team 2 hue. Range [0, 359] or -1 for default. |
| S_UseClubTags                 | Boolean | True          | Derive teamnames from the clubtags of the players. If all players in a team have the same clubtag, the team name will be set to that club tag (without text formatting), else default names are used. Forced team names take precedence. |
| S_UseTeamSkins                | Boolean | True          | Force animal/royal skins according to the color of the teams. |


## Other settings

Administrative and miscellaneous settings.

| Setting name                  | Type    | Default value | Description |
| ----------------------------- | ------- | ------------- | ----------- |
| S_SkipMatchOnLastPlayerLeave  | Boolean | True          | Skip the ongoing match if all players leave the server or switch to spectator. |
| S_ModeCommands_AdminLoginsCsv | Text    | "" (blank)    | Ingame logins of the players that should have access to the ModeCommandsUI. ModeCommandUI provides the ability to manually reset the flag, pause ongoing rounds, set scores and more. |