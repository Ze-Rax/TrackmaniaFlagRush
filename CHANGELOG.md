## 1.3.0
+ Added XML-RPC callbacks for mode related callsbacks, see `XmlRpcScriptedCallbacks.md`
+ Added round number to the message at the start of a round.
+ Added text for time spent in overtime in the scores header.
+ Added teleport detection: The flag will be dropped, if a player teleports too far (1 block).
+ Added callvotes page to pause menu.
+ Match is reset when all players leave the server or go to spec.
* Adjusted markers for bases
	* The base you have to attack shows a crosshair icon in the color of the opposite team.
	* The base you have to defend shows a shield icon in the color of your team.
* Adjusted respawn timer UI to take spawn animation duration into account.
* Adjusted default repsawn delay to 4.0 seconds (from 3.0 seconds)
* Fix Z-Index of the UI that broke after the september Trackmania update.

## 1.2.1
+ New mode commands (Callvotes, ModeCommandsUI) for setting match/map/round points and auto team balance.
* Fix scorestable player statistics
* Bug fixes and optimizations

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

## 1.1.2
* Fixed an issue with the respawn timer constantly resetting when falling into offzone

## 1.1.1
* Fixed an small issue with the radar not displaying some players correctly when in spectator

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