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