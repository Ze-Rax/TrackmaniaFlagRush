# FlagRush Xml-Rpc Scripted Callbacks

Note: Callback names and payload are subject to change and may be editied in the future. Changes will be noted in the changelog for the mode.


## Events

These events are being sent via Xml-Rpc Callbacks. For the actual payload definition, see [Structs](#Structs).


## Flag related events

### FlagRush.Flag.Pickup

- Sent when a player picks up the flag. This includes picking it up from the ground, a flag spawn or on passes.
- Payload: `K_Rpc_FlagPickup`

### FlagRush.Flag.Drop

- Sent when a player drops the flag on the ground.
- Payload: `K_Rpc_FlagDrop`

### FlagRush.Flag.Pass

- Sent when the flag is passed between two players. This includes passes between teammates and stealing the flag from the opponent.

- Payload: `K_Rpc_FlagPass`

### FlagRush.Flag.Reset

- Sent when the flag is reset to a flag spawn
- Payload: `K_Rpc_FlagReset`

### FlagRush.Flag.Scored

- Sent when the flag is scored at one of the team bases.
- Payload: `K_Rpc_FlagScored`


## Player related events

### FlagRush.Player.Death

- Sent when a player goes out of bounds, i.e. triggers a death trigger / „FlagReset“ landmark
- Payload: `K_Rpc_PlayerDeath`


## Match flow events

### FlagRush.Flow.MatchStart

- Sent when a match starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.MatchEnd

- Sent when a match ends.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.MapStart

- Sent when a map starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.MapEnd

- Sent when a map ends.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.RoundStart

- Sent when a round starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.RoundEnd

- Sent when a round ends.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.Overtime

- Sent when overtime starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.WarmUpStart

- Sent when a warm up starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.WarmUpEnd

- Sent when a warm up ends.
- Payload: `K_Rpc_Flow`


## Structs

### Event structs

These are the structs that are actually being sent by the callbacks. Definition as in ManiaScript, sent in JSON format.

```
#Struct K_Rpc_FlagPass {
	Integer Time;
	K_Rpc_Player OldCarrier;
	K_Rpc_Flag Flag;
}
```

```
#Struct K_Rpc_FlagDrop {
	Integer Time;
	K_Rpc_Player OldCarrier;
	K_Rpc_Flag Flag;
}
```

```
#Struct K_Rpc_FlagReset {
	Integer Time;
	K_Rpc_Flag Flag;
}
```

```
#Struct K_Rpc_FlagPickup {
	Integer Time;
	K_Rpc_Flag Flag;
}
```

```
#Struct K_Rpc_FlagScored {
	Integer Time;
	K_Rpc_Player Scorer;
	K_Rpc_Player Assist;
	Integer[] TeamScores;
}
```

```
#Struct K_Rpc_PlayerDeath {
	Integer Time;
	K_Rpc_Player Player;
}
```

```
#Struct K_Rpc_Flow {
	Integer Time;
	K_Rpc_Map Map;
	Boolean Valid;
	Integer[] TeamScores;
	K_Rpc_PlayerScore[] PlayerScores;
}
```

### Subcomponent structs

These are structs that represent objects present on the server with their most relevant data, i.e. Players, Scores, Flag and so on. Used in the event structs above.

```
#Struct K_Rpc_Team {
	Integer Num;
	Text Name;
}
```

```
#Struct K_Rpc_Player {
	Text Login;
	Text Name;
	Integer TeamNum;
	Vec3 Position;
}
```

```
#Struct K_Rpc_Landmark {
	Integer LandmarkId;
	Vec3 Position;
}
```

```
#Struct K_Rpc_Flag {
	Vec3 Position;
	K_Rpc_Player Carrier;
	K_Rpc_Landmark Spawn;
}
```

```
#Struct K_Rpc_PlayerScore {
	K_Rpc_Player Player;
	Integer Points;
	Integer FlagsScored;
	Integer FlagsStolen;
	Integer Assists;
}
```

```
#Struct K_Rpc_Map {
	Text Name;
	Text Uid;
	Text AuthorLogin;
	Text AuthorName;
}
```


