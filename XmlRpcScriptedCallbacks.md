# FlagRush Xml-Rpc Scripted Callbacks

Note: Callback names and payload are subject to change and may be editied in the future. Changes will be noted in the changelog for the mode.

## Events

These events are being sent via Xml-Rpc Callbacks. For the actual payload definition, see [Structs](#Structs).

## Flag related events

### FlagRush.Flag.Pickup

- Sent when a Player picks up the flag from the ground or a flag spawn.
- Payload: `K_Rpc_FlagPickup`

### FlagRush.Flag.Drop

- Sent when a Player drops the flag on the ground.
- Payload: `K_Rpc_FlagDrop`

### FlagRush.Flag.Pass

- Sent when athe flag is passed between two players. This includes passes between teammates and stealing the flag from the opponent

- Payload: `K_Rpc_FlagPass`

### FlagRush.Flag.Reset

- Sent when the flag is reset to a flag spawn
- Payload: `K_Rpc_FlagReset`

### FlagRush.Flag.Scored

- Sent when the flag is scored at one of the team bases.
- Payload: `K_Rpc_FlagScored`

## Player related events

### FlagRush.PlayerDeath

- Sent when a player goes out of bounds, i.e. triggers a death trigger / „Flag reset“ landmark
- Payload: `K_Rpc_PlayerDeath`


## Match flow events

### FlagRush.Flow.MatchStart

- Sent when the match starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.MatchEnd

- Sent when the match ends.
- Payload: `K_Rpc_FlowScores`

### FlagRush.Flow.MapStart

- Sent when the map starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.MapEnd

- Sent when the map ends.
- Payload: `K_Rpc_FlowScores`

### FlagRush.Flow.RoundStart

- Sent when the round starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.RoundEnd

- Sent when the round ends.
- Payload: `K_Rpc_FlowScores`

### FlagRush.Flow.Overtime

- Sent when overtime starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.WarmUpStart

- Sent when warm up starts.
- Payload: `K_Rpc_Flow`

### FlagRush.Flow.WarmUpEnd

- Sent when warm up ends.
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
K_Rpc_TeamScore[] TeamScores;
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
}
```

```
#Struct K_Rpc_FlowScores {
Integer Time;
}
```

```
#Struct K_Rpc_Map Map;
Boolean Valid;
K_Rpc_PlayerScore[] PlayerScores;
K_Rpc_TeamScore[] TeamScores;
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
K_Rpc_Team Team;
Vec3 Position;
}
```

```
#Struct K_Rpc_FlagSpawn {
Integer LandmarkId;
Vec3 Position;
}
```

```
#Struct K_Rpc_Flag {
Vec3 Position;
K_Rpc_Player Carrier;
K_Rpc_FlagSpawn Spawn;
}
```

```
#Struct K_Rpc_TeamScore {
K_Rpc_Team Team;
Integer MatchPoints;
Integer MapPoints;
Integer RoundPoints;
}
```

```
#Struct K_Rpc_PlayerScore {
K_Rpc_Player Player;
Integer RoundPoints;
Integer MapPoints;
Integer MatchPoints;
Integer FlagsScoredRound;
Integer FlagsScoredMap;
Integer FlagsScoredMatch;
Integer FlagsStolenRound;
Integer FlagsStolenMap;
Integer FlagsStolenMatch;
Integer AssistsRound;
Integer AssistsMap;
Integer AssistsMatch;
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


