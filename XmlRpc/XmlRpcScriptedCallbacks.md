# FlagRush Xml-Rpc Scripted Callbacks

Note: Callback names and payload are subject to change and may be editied in the future. Changes will be noted in the changelog for the mode.

These events are being sent via Xml-Rpc Callbacks. For the actual payload definition, see the related [Json schemas](JsonSchema/events/).


## Flag related events

### FlagRush.Flag.Pickup

- Sent when a player picks up the flag. This includes picking it up from the ground, a flag spawn or on passes.
- Payload: [`flagPickup.schema.json`](JsonSchema/events/flag/flagPickup.schema.json)

### FlagRush.Flag.Drop

- Sent when a player drops the flag on the ground.
- Payload: [`flagDrop.schema.json`](JsonSchema/events/flag/flagDrop.schema.json)

### FlagRush.Flag.Pass

- Sent when the flag is passed between two players. This includes passes between teammates and stealing the flag from the opponent.

- Payload: [`flagPass.schema.json`](JsonSchema/events/flag/flagPass.schema.json)

### FlagRush.Flag.Reset

- Sent when the flag is reset to a flag spawn
- Payload: [`flagReset.schema.json`](JsonSchema/events/flag/flagReset.schema.json)

### FlagRush.Flag.Scored

- Sent when the flag is scored at one of the team bases.
- Payload: [`flagScored.schema.json`](JsonSchema/events/flag/flagScored.schema.json)


## Player related events

### FlagRush.Player.Death

- Sent when a player goes out of bounds, i.e. triggers an out of bounds trigger / „FlagReset“ landmark or is eliminated by means like moving blocks.
- Payload: [`playerDeath.schema.json`](JsonSchema/events/player/playerDeath.schema.json)


## Match flow events

### FlagRush.Flow.MatchStart

- Sent when a match starts.
- Payload: [`matchStart.schema.json`](JsonSchema/events/flow/matchStart.schema.json)

### FlagRush.Flow.MatchEnd

- Sent when a match ends.
- Payload: [`matchEnd.schema.json`](JsonSchema/events/flow/matchEnd.schema.json)

### FlagRush.Flow.MapStart

- Sent when a map starts.
- Payload: [`mapStart.schema.json`](JsonSchema/events/flow/mapStart.schema.json)

### FlagRush.Flow.MapEnd

- Sent when a map ends.
- Payload: [`mapEnd.schema.json`](JsonSchema/events/flow/mapEnd.schema.json)

### FlagRush.Flow.RoundStart

- Sent when a round starts.
- Payload: [`roundStart.schema.json`](JsonSchema/events/flow/roundStart.schema.json)

### FlagRush.Flow.RoundEnd

- Sent when a round ends.
- Payload: [`roundEnd.schema.json`](JsonSchema/events/flow/roundEnd.schema.json)

### FlagRush.Flow.Overtime

- Sent when overtime starts.
- Payload: [`overtime.schema.json`](JsonSchema/events/flow/overtime.schema.json)

### FlagRush.Flow.WarmUpStart

- Sent when a warm up starts.
- Payload: [`warmUpStart.schema.json`](JsonSchema/events/flow/warmUpStart.schema.json)

### FlagRush.Flow.WarmUpEnd

- Sent when a warm up ends.
- Payload: [`warmUpEnd.schema.json`](JsonSchema/events/flow/warmUpEnd.schema.json)
