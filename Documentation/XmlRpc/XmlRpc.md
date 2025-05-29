# XmlRpc

Additional to the regular Callbacks sent by common Trackmania gamemodes, FlagRush sends additional XmlRpc-Callbacks for the most important events. Those include general progression events, as well as gameplay related events. Below, a list of all callbacks and the situation in which they are sent is provided. The actual payload definition is defined through the provded Json-Schema in the `JsonSchema` subdirectory.

Warning: These Callbacks are heavily work in progress and might change with breaking changes in the future.

## Callbacks

### Progression
The following callbacks are sent when the match progresses to a new segment. Note that even though some names might be similar to the common callbacks from Nadeo gamemodes, the timing might be different due to different requriements for themode.

| Callback Name                         | Description | Payload |
| ------------------------------------- | ----------- | ------- |
| `FlagRush.Progression.Server.Start`   | Sent when the server starts. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Server.End`     | Sent when the server is shut down. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Match.Start`    | Sent when a new match starts. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Match.End`      | Sent when a match ends. | See [SegmentEndWithScores.json](./JsonSchema/Callbacks/Progression/SegmentEndWithScores.json) |
| `FlagRush.Progression.Map.Start`      | Sent when a new map starts. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Map.End`        | Sent when a map ends | See [SegmentEndWithScores.json](./JsonSchema/Callbacks/Progression/SegmentEndWithScores.json) |
| `FlagRush.Progression.Round.Start`    | Sent when a new round starts. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Round.End`      | Sent when a round ends. | See [SegmentEndWithScores.json](./JsonSchema/Callbacks/Progression/SegmentEndWithScores.json) |
| `FlagRush.Progression.Turn.Start`     | Sent when a new turn starts. This is relevant for if a round was paused. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Turn.End`       | Sent when a round ends. This is relevant for if a round is being paused. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Overtime.Start` | Sent when the overtime starts. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Overtime.End`   | Sent when the overtime ends. This happens only right before the round end is sent when overtime was running. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.WarmUp.Start`   | Sent when the warmup starts. This happens also during a pause. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.WarmUp.End`     | Sent when the warmup ends. This happens also during a pause. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Pause.Start`    | Sent when a live round is being paused. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Pause.End`      | Sent when a live round continues. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Podium.Start`   | Sent when the podium sequence starts. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |
| `FlagRush.Progression.Podium.End`     | Sent when the podium seuquence ends. | See [GenericSegment.json](./JsonSchema/Callbacks/Progression/GenericSegment.json) |

### Player
The following callbacks are sent when an important event for a given player occurs.

| Callback Name                         | Description | Payload |
| ------------------------------------- | ----------- | ------- |
| `FlagRush.Player.RequestedRespawn`    | Sent when a player requests to respawn. This is also the case if respawning is restricted due to the configured speedlimit. In that case the `success` field of the payload will be `false`. | See [PlayerRequestedRespawn.json](./JsonSchema/Callbacks/Player/PlayerRequestedRespawn.json) |
| `FlagRush.Player.Spawned`             | Sent when a player is being spawned. | See [PlayerSpawned.json](./JsonSchema/Callbacks/Player/PlayerSpawned.json) |
| `FlagRush.Player.OutOfBounds`         | Sent when a player touches an out of bounds trigger and is despawned because of that. | See [PlayerOutOfBounds.json](./JsonSchema/Callbacks/Player/PlayerOutOfBounds.json) |
| `FlagRush.Player.Eliminated`          | Sent when a player is eliminated, most likely due to moving blocks. | See [PlayerEliminated.json](./JsonSchema/Callbacks/Player/PlayerEliminated.json) |

### Flag
The following callbacks are sent when an important event for the flag occurs.

| Callback Name                         | Description | Payload |
| ------------------------------------- | ----------- | ------- |
| `FlagRush.Flag.Reset`                 | Sent when the flag is reset to a flag spawn. | See [FlagReset.json](./JsonSchema/Callbacks/Flag/FlagReset.json) |
| `FlagRush.Flag.PickedUp`              | Sent when the flag is picked up by a players. | See [FlagPickedUp.json](./JsonSchema/Callbacks/Flag/FlagPickedUp.json) |
| `FlagRush.Flag.Passed`                | Sent when the flag is passed between two players. This includes flag steals from the opposing team. | See [FlagPassed.json](./JsonSchema/Callbacks/Flag/FlagPassed.json) |
| `FlagRush.Flag.Dropped`               | Sent when the flag is dropped by a player. | See [FlagDropped.json](./JsonSchema/Callbacks/Flag/FlagDropped.json) |
| `FlagRush.Flag.CarrierTeleporte`      | Sent when the flag carrier moves more that the configurable allowed distance threshold during a single server frame. | See [FlagCarrierTeleported.json](./JsonSchema/Callbacks/Flag/FlagCarrierTeleported.json) |
| `FlagRush.Flag.Scored`                | Sent when a players scores the flag. | See [FlagScored.json](./JsonSchema/Callbacks/Flag/FlagScored.json) |
| `FlagRush.Flag.DropTimerExpired`      | Sent when the drop time of a dropped flag expires. | See [FlagDropTimerExpired.json](./JsonSchema/Callbacks/Flag/FlagDropTimerExpired.json) |
