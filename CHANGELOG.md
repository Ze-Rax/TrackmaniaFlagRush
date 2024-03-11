# Changelog

## 1.5.0

### General
+ Added support for new cars (Snow, Rally).
+ Added a server setting `S_ForceEnabledVehiclesCsv` to override the enabled cars.
* Replace setting `S_DropFlagOnTeleportDetection` with `S_TeleportDetectionThreshold` that takes a value to specify the maximum allowed teleport (lag) distance.
* Reduced the default teleport detection threshold to 8 meters (quarter of a block).

### MapType
+ Added the ability to select the available cars on a given map using the FlagRush settings dialog

### UI
+ Added a car selection to the scoreboard
	* Mouse users can click the respective buttons on the bottom right below the scoreboard.
	* Gamepad user can use the right stick to select the previous or car respectively.
	* Car changes are applied on spawn. If a player wants to change their car mid round, they have to respawn.

---

## 1.4.1

### Bugs and crashes
* Fix players spawning in black stadium car.
	* Since Nando removed the Royal-Animal-Skins from the gamefile, skins have been replaced with solid colored skins that are retrieved from the ingame club.

---

## 1.4.0

### General
* Manually dropping the flag in a stack of players is now considered a pass/steal instead of a drop.
- Flag steal resistance on passes between team members has been removed.
	* Picking up a dropped flag or stealing it from your opponent still gives steal resistance.
	* Steal resistance can still be achieved by dropping the flag in front of your teammates for them to pick it up.
	* A setting has been added to turn this new behaviour on or off: `S_FlagStealResistanceOnTeamPass` (Boolean)

### UI
+ Added a toggle button on the scoreboard to toggle between displaying map or match scores.
+ Fixed podium screen after december Trackmania update.
* The "Out of Bounds Trigger" is now correctly called like that in the maptype, instead of the old "Flag Reset Trigger" naming.

### Bugs and crashes
* Fixed a bug that causes a flag marker to be stuck in the center of the screen during initial warmup per map.
* Fixed a crash that happened when a player leaves the server at the same server frame as crossing a waypoint.
* Fixed "out of bounds" messages being spammed under certain conditions.
* Compatibility with Trackmania Fall update.

---

## 1.3.2

### Maptype
* Fix crash after Trackmania December update.

---

## 1.3.1

### General
* Fix multiple players being fragile after dropping the flag in a stack of players while the steal resistance is active.
* If multiple players enter a dropped flag at the same time, the opponent team of the player that dropped the flag last will have priority.

### UI
+ Added a message to the Event feed when a player respawns.
* Fix wrong scores sometimes shown on podium screen.
* Fix scoresboard to show map points in "Points" counter instead of match points.

---

## 1.3.0

### General
+ Added teleport detection: The flag will be dropped, if a player teleports too far (1 block) during one server frame
+ Added XML-RPC callbacks for mode related callsbacks, see [XmlRpcScriptedCallbacks.md](XmlRpc/XmlRpcScriptedCallbacks.md)
+ Match is reset automatically when all players leave the server or go to spec
+ Added support map specific team colors
  + Requires the new maptype
+ Added maptype requirement for podiums
* Bug fixes and optimizations

### UI
+ Added a distance indicator to the flag marker
+ Added round number to the message at the start of a round
+ Added text for time spent in overtime in the scores header
+ Added callvotes page to pause menu
+ Added an indicator for the default FlagSpawn in warm up
* Adjusted markers for bases
	* The base you have to attack shows a crosshair icon in the color of the opposite team
	* The base you have to defend shows a shield icon in the color of your team
* Adjusted respawn timer UI to take spawn animation duration into account
* MVP Screen has been replaced by a podium sequence

### Balancing
* Adjusted default flag carrier acceleration coef to 0.66 (from 0.7)
* Adjusted default flag carrier adherence coef to 0.9 (from 1.0)
* Adjusted respawn delay functionality: Respawn delay is now dependent on the amount of players in a team: `Respawn delay = Amount of player in the team * S_RespawnDelayPerPlayer (Setting) + 1.5 seconds Spawn animation`

---

## 1.2.1
+ New mode commands (Callvotes, ModeCommandsUI) for setting match/map/round points and auto team balance.
* Fix scorestable player statistics
* Bug fixes and optimizations

---

## 1.2.0
+ New Hitboxes! Completely new and very precise player hit detection.
+ Added Radar customization: Drag and move the radar around, or open the radar settings menu to change opcaity, scale and position
+ Added MVP screen at the end of a match, highlighting the best players of the match
* Flag now drops at last "safe" position when the carrier falls into offzone or a flag reset trigger. This is the last place where the flag carrier touched the ground with at least 3 wheels
* UI Overhaul
	* Completely reworked scorestable and scoresheader
	* Radar changed to circular radar
	* Height difference indicators for flag markers (worldspace and radar markers)
	* Custom ingame menu (Escape key)
* Teams now have an associated skins which is forced onto each player (Can be disabled through settings)
* Teambalance callvote is now available through the new ingame menu: `Ingame Menu (Escape key) > Teams... > Balance`
* Disabled fine extrapolation
	* We're using crude extrapolation again. Fine extrapolation was meant to improve player position prediction but apparently it lead to massive player desync where players would teleport over the whole map and be displayed at the wrong position on your screen. A side effect of this change is that the radar has a worse temporal resoluation now, since we don't have access to some variables with crud extrapolation.
	* Fine extrapolation can still be reenabled by serveradmins using the setting `S_UseCrudeExtrapolation` (Set to `False`). It will also automatically be enabled when playing with collisions, as it's needed for collisions to work.
* Some bug and crash fixes and general optimizations

---

## 1.1.2
* Fixed an issue with the respawn timer constantly resetting when falling into offzone

---

## 1.1.1
* Fixed an small issue with the radar not displaying some players correctly when in spectator

---

## 1.1.0
+ Added a radar ("minimap") on screen, which shows the location of nearby players and the flag
+ Added a flag reset trigger for mapping. If you pass it, the flag will instantly be reset at the player will be unspawned. (Similar to offzone)
+ Added a visual respawn timer which counts down how much time is left until you respawn ("reverse progress bar")
+ Added a setting for player collision (Experimental; disabled by default)
  *  Collisions have several issues. For once, TM collisions can be very weird. Apart from that there are Hitbox issues, so sometimes flagsteals from the front or back won't work! Keep that in mind, we will improve on it in the future
+ Added warnings when timelimit is about to run out (60 seconds remaining, 30 seconds remaining)
* Increased default player respawn delay: 1.5s -> 3.0s
* Flag stealing now gives priority to the opposing team, which makes it easier to steal the flag when two teammates are stacked on each other
* Disabled crude extrapolation for hopefully slightly better player synchronization
* Some optimizations have been made to make the UI more performant
* Fixed multiple bugs and crashes