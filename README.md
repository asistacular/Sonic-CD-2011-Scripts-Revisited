# Sonic CD 2011 Scripts Revisited
### A fork of [Rubberduckycooly's Sonic CD 2011 Script Decompilation](https://github.com/Rubberduckycooly/Sonic-CD-2011-Script-Decompilation)
&nbsp;

## How to use these scripts
Please note that you will need to build an executable from the related engine project [here](https://github.com/asistacular/Sonic-CD-2011-Engine-Revisited) to use these scripts in their current form, as they contain functionality that is not present in the original RSDKv3 decomp. Also, any assets that have been created/modified for this project are not currently available and may result in some graphical weirdness. I'm a bit cagey about providing them through GitHub because of potential copyright issues, but I will see what I can do in the future.

That said, you are free to utilize any script modifications (bugfixes, enhancements, anything!) that you find in this repository for your own projects and mods. All I ask is that you provide proper credit somewhere.  It doesn't have to be prominent or in-game anywhere, just in documentation or patch notes, etc. Happy modding!

## Current Project Goals
### Completed
+ Enhancements:
  * Replaced the high-res SEGA logo and CW logo with available 'pixel art' variants (due to reliance on the HW renderer to look clean/crisp)
  * Removed Achievements and Leaderboard options from main menu
  * Moved Soundtrack option into the options menu and condensed all remaining main menu options to fit on one screen
  * Restored PC version options menu to match the mobile version, restored staff credits and about menu, removed all links in about menu
  * Restored PC version settings menu and changed button color to a reddish-orange that is present in the menu headings
  * Removed Instructions option (due to reliance on the HW renderer to be legible)
  * Changed the PC version of the DA Garden to match the mobile version
  * Merged credits text files and removed Blit software credits, since their code is no longer present in the decomp
+ Bugfixes/slight enhancements:
  * Restored SEGA logo, CW logo screens when using PC assets
  * Corrected blank space on the title screen in widescreen when using PC assets
  * Restored ability to exit the game on PC versions
  * Overhauled title cards to display and animate correctly in multiple aspect ratios and exit the screen correctly
  * Changed title card layout of PC version special stages (derived from Sonic CD PC) to match regular stages (derived from Sonic CD MegaCD/SegaCD)
  * Corrected SS1/SS6 animated backgrounds in widescreen when using PC assets
  * Removed a column of tiles from PPZ1 present on PC version layout so that the 3D ramp looks correct in widescreen
  * Corrected the active character's palette when warping through time from underwater
  * Re-enabled correct water palette/deformation effects in TTZ when using mobile assets (SW renderer only)
  * Re-enabled the glow effect on crystals in QQZ when using mobile assets (SW renderer only)
  * Expanded the range of the MMZ boss' diagonal wing projectile to properly come from offscreen in widescreen and adjusted speed to match the original timing
### Partially Completed
+ Enhance pause functionality (in conjunction with engine additions from the related engine project)
  * Enabled fully-animated pause menu in special stages
  * Moved the pause menu into a higher DrawLayer to prevent conflict with the HUD
  * To Do: Update all in-game objects to move any non-drawing related code from ObjectDraw to ObjectMain (ugh...)
    - Progress: Special Stages, global objects, misc objects, animated tiles, parallax effects, deformation effects, boss objects - Complete; R1,R3,R4,R5,R6,R7,R8 stage objects - Pending
### Planned
+ Enhancements:
  * Select a single set of assets/stage layouts to use between PC/mobile versions
  * Merge PC/mobile only script sections to create a unified codebase
  * Use `#Screen_Std` and `#Screen_Wide` preprocessor directives to partially replace the `#Standard` and `#Mobile` directives (in conjunction with engine additions from the related engine project)
+ Bugfixes:
  * Correctly retain tiny form when warping through time in MMZ2
  * Use mobile layout or remove a column of tiles for CCZ1 and CCZ2 to extend stage area in PC version after sign post when in widescreen
  * Fix incorrect active palette displaying during pause and rapid palette switching after resuming from a paused state (in conjunction with engine additions from the related engine project)
### Possible
+ Restore original palette cycle and background planet shape in SS2
+ Slow down movement speed of various speedy (possibly bugged) UFO paths in SS2 and SS3
+ Retain shields, speed shoes and invincibility when warping through time
+ Instant time warping option
+ Option to switch between SegaCD/MegaCD and Genesis/MD sound effects
+ Option to switch between 4:3 (original) and 16:9 (wide) display area in-game, potentially using pillarboxing
+ Make some game options available from pause menu
+ Port entirety of game to RSDKv4 (the final boss!)

## From the original repository:
### A full decompilation of the scripts from Sonic CD 2011's PC port 

+ These scripts have been manually reverted back to what the original scripts could've looked like.
  * Function IDs have been reverted back into function names
  * Some functions have been given proper names
  * Functions are in the proper order
  * Default aliases have been re-added where possible
  * Mobile & haptics code has also been added into scripts via the use of `#platform:` preprocessor directives

To use these scripts in mods, first extract the Scripts folder to the exe's root directory (e.g. `[rootdir]/Scripts/`). Then, make sure the Sonic CD mod loader is fully up to date, since the mod loader loads all of the default scripts from the `Scripts/` directory. This way, mods are only required to include any scripts that have been changed.

For anyone curious about how Sonic CD's scripting language (tentatively dubbed RetroScript) works, check out the included handbook (RetroScript Handbook v3.pdf) that Rubberduckycooly made to help get people into using RSDKv3's scripting language!
