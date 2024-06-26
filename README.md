## About this Repository:
This is an archive of the Cheat Menu Framework mod from before the rename and further modularization. There will be no further changes to the code here.

# Modular Cheats Mod (a.k.a MCM)
An newer, module-based version of the Cheats Mod.

## Compatibility:
Minimum required game version: 0.8.1.0+

<details>
<summary>Hotkeys:</summary>

F3: Unequip All Equipment (SHIFT+F3: Force Unequip) [Requires addon module]<br/>
F4: Toggle Auto-Bandage [Requires addon module]<br/>
F5: Toggle Infinite Main Stats (Individual options in the menu) [Requires addon module]<br/>
F6: Add 99,999 Trade Points<br/>
F7: Heal a wound (at random)<br/>
F8: Heal<br/>
F9: Show Cheats Menu<br/>
</details>

## Before installing the mod:
Ensure that the old cheat mod and the dependency are not installed as they are not compatible with this mod and will result in crashes.

Now make sure you can answer yes to the following questions:
1. Have you set the game path in NyxLauncher?
2. Have you launched the game to the title screen at least once?

## After installing the mod:
1. Did your archive extractor of choice add a folder with the archive filename? <------- For this one, if you answered yes, the mod will NOT work regardless of if it shows up in nyxlauncher.

## Notice:
Modular Cheat Mod does not nor has it ever provided the console. That feature is built into the game (See `Data/Scripts/Frames/RVscript/520_YanflyF10.rb` within the game files)

## Important Information:
Any archive I share must be extracted how I say (if applicable), not into a folder with the archive name. The file/folder structure within is exactly how it needs to be for where it is to be extracted.

## Known Issues:
- Hive Hearts summoned on maps without H_BIOS storypoints crash the game. Only summon them if you wish to farm them on their actual maps. (If anyone knows how to recreate these storypoints in code if they don't exist in the current area, feel free to make and share a patch to the Summon feature)
- Having all 3 Infinite Stats cheats enabled causes lag to a noticeable degree. (Configurable variant ONLY)
- Some things don't change when changing languages. This is a problem with even the game itself, so restart after switching languages.
- [Will NOT be changed] There is no default language fallback implemented in the mod, so if you use the MTL in the game itself, you MUST create the MTL folder in the mod too. This is by design as the mod relies on the language as set by the game. The MTL tool can be tricked into translating the mod, but the language the tool uses as a source is Google Translated from English and will be inaccurate. The only languages included in the mod that are confirmed accurate are English (being my native language) and Russian (see Credits spoiler)

## Planned changes (lower number = highest priority):
- Move features into their own CheatModules. (The Pregnancy addon is a sample of how that will look) - Once this change is fully implemented I'll be giving the mod version numbers starting from 1.0
- Rename the mod to Cheats Menu Framework (CMF for short) once the mod reaches v1.0
- Major optimization of the Infinite Stats cheats (Configurable variant ONLY) [On-hold]
- Redesign the menu to match the pause menu (maybe even add a Cheats entry to the pause menu to free up a hotkey) [TBD]
<hr/>

## Changelog:
<details>
<summary>Changelog</summary>

- Cleaned up code indentation.
- Renamed dependency to 99998_Lib_DebugMenu
- Move fixes related to scenes into 99998_Lib_DebugMenu
- Added trigger_debug_window_entry to 99998_Lib_DebugMenu.
  (Only installing the dependency gives a standard Debug Menu.)
- Commented out the remaining Battle Test code as it was causing issues in its current state.
- Changed all instances of @autoheal to $autoheal
- Moved `$autoheal = false` out of `class Scene_Base` to make it global.
  (Makes persistent while the game is running.)
- F5 now plays a different sound depending on the state of $autoheal
- Add an option to give 99 levels.
- Moved the race change options into a new submenu (Change Race)
- Added the ability to toggle whether or not Lona gets dirty (persistent through saving/loading)
- Added Abominations to race menu.
- Switched to modular format.
- Added a cheat settings loader. (Saves to and loads from `GameCheats.ini` in the game's root folder next to `Game.ini`, `GameLona.ini` and `GameMods.ini`)
- Autoheal state is now persistent via the settings loader. Added a check to prevent cheat running before the main menu appears.
- Fixed support skills not able to be used on others bug in NoFriendlyFire mod.
- Restored builtin Friendly Fire Avoidance.
- Removed NoItemDisappearing mod as it no longer works.
- Added projectiles back to NoFriendlyFire from original.
- Improved toggling of the Dirty stat. Moved to new spot (see below)
- Split AutoHeal cheat into individual stats. Hotkey toggles all 3 together, if toggled individually in the menu the hotkey will reverse the state of those options (Kept for those who just want all 3 stats to be infinite)
- Added F1, F2, F3, F4 as usable Input triggers.
- Lvl99 cheat now sets the level directly and sets experience to only what is needed for getting to lvl 99
- Add Trait Points now only adds 999 trait points, 9999 was severely overkill.
- Made it possible to use the Confirm key/button without breaking stealth (requires "Into Shadows" trait)
- New "Toggle Cheats" option in menu, can be easily added to from other mods (see `2000_CheatModule_*.rb` for examples). Toggles include:
  - Dirty Stat - Toggles whether or not Lona can get dirty. Now properly toggles. State is saved in save files, not in the `GameCheats.ini` file.
  - Auto-Bandage - Toggles the automatic treatment of wounds. (`2000_CheatModule_AutoBandage.rb`)
  - Infinite Health - Toggles auto-heal. (`2000_CheatModule_InfiniteMainStats.rb`)
  - Infinite Food - Toggles auto-feed. (`2000_CheatModule_InfiniteMainStats.rb`)
  - Infinite Stamina - Toggles auto-rest. (`2000_CheatModule_InfiniteMainStats.rb`)
- New hotkey (F3) to unequip unequipable equipment.
  Shift+F3 to force unequip (unequips equipment not normally unequipable).
- Fixed - check that prevent autocheats running when not ingame. Should work with all saves now, regardless of what game version the save was started in.
- A few bugfixes, reorganized a few things and adjusted ScriptLoad priorites.
- More bugfixes, added Item, Weapon, Armor inventory editors, changed 100 modifier key from CTRL to ALT as it wasn't working with CTRL.
- Made it easy add to the main menu of Cheats Mod from other mods. See `1500_CheatModule_InvEdit.rb` for example.
- Summon menu now only lists NPC's. Certain NPC's will crash the game if killed on the wrong map.
- Merged Morality options into an editor. Also colorized (Green=Good, White=Neutral, Red=Evil)
- "Toggle Cheats" now show if they are on/off.
- Added module that adds abom skills when changing race to Abomination, removes abom skills when changing to non-abom races.
- Added module that adds the ability to change Lona's Hair Color.
- Re-structured the Modular Mod Loader version of the mod.
- Limited Hair Color Editor to range of 0-5, auto-wraps around to 0 or 5 respectively.
- Removed extra mods from othermods that shouldn't of been included.
- Inverted the Skill Roster paging direction. - Removed in favor of the official bugfix.
- Added CG/Achievement Unlock module, decided to leave this as a non-GUI option, commands to unlock/reset CG's and Achievements are as follows:
  CheatUtils.unlock_cg
  CheatUtils.unlock_ach (Make sure to install the UnlockTool in the `Required Modules` section as it fixes the ear rape from using this command)
  CheatUtils.reset_cg
  CheatUtils.reset_ach
- Disabled cheat entries during disclaimer screen.
- Infinite Stats cheats implementation upgrade (settings editable only from GameCheats.ini or console if you know what you are doing): (needs optimizing, causes slightly noticable amount of lag)
- Configurable regen limits [percentage of current max stat value] (Defaults: Health - 20%, Stamina - 40%, Food: 10%) [0.20, 0.40, 0.10]
- Configurable regen rates [percentage of current max stat value] (Defaults: Health - 1%, Stamina - 0.2%, Food: 0.5%) [0.01, 0.002, 0.005]
- Regen modes:
  - Regen only while below limit. (Default) [OnlyBelow]
  - Regen to full upon dropping below limit. [DropsBelow]
- Added JoiPlay support, uncomment `$JOIPLAY_MODE = true` in `main.rb`:
  Disables all hotkeys except the menu.
  Checks for F8 (CR button) instead of F9. - Regressed as completely unnecessary.
- Translation support for text within Modular Cheats Mod. (Restart the game after switching languages)
- Forgot to swap the appropriate lines in main.rb, fixed. Please re-download. Also once again removed some other mods that were not supposed to be in the upload.
- Improved the fix in `main.rb`. Now I won't need to mess with which lines are commented or not ;)
- RUS DeepL translation replaced with manual translation, many thanks Zhong Xina | z洪ξ那  :)
- Morality cheat now works correctly, was editing the display stat only (needed to edit both the display and the storage)  o_O
- There are now 2 variants of the Infinite Stats cheat:
  - Variant 1: Simple version that is not configurable, just adds 999 like the old versions did.
  - Variant 2: The indev configurable version.
- RUS translation update: flaws fixed. Thanks Zhong Xina | z洪ξ那
- Configurable Infinite Health Cheat: using wrong stat for max health value, fixed.
- `CheatUtils` class changed to module. Initial declaration moved from `CheatMod.rb` to `Utils.rb`
- Unused dependency code removed, remaining class merged into CheatMod.rb (Dependency credit will remain for historical reasons)
- Added new cheat: Infinite Money (AKA Trade Points)
- Fixed - Unlock Tool module no longer plays sounds when unlocking all achievements. Make sure to get the update from the `Required Modules` section.
- Split included modules out into their own downloads.
- Updated Race Changer to support Pure Moot (yes the tail). Compatibility with previous game versions potentially definitely broken... Feedback required Confirmed by feedback.
- Renamed `main.rb` to `__init__.rb`, wrapped mod specific code into a module.
- Fixed - Forgot to add `FileGetter.` to `load_from_list` function call in CheatsMod module.
- Fixed - getTextInfo wrapped into CheatsMod module. All scripts using it have been updated.
- New CheatModule: Sea Witch Awaken Skill - When using the Race Changer to change race to either Pre or True Deepone, the Awaken skill is learnt, for other races it is removed.
- Removed - Pregnancy submenu in favor of the new CheatModule which replaces it.
- Removed - UnlockTool translations removed as a previous update negated the need to translate the CheatModule.
</details>

## Mod Managing:
<details>
<summary>Mod Management Instructions:</summary>

Note: Other mods not required, they are just what is in my load order.

1. ![](/../Assets/instruc_1.png)

2. ![](/../Assets/instruc_2.png)

3. ![](/../Assets/instruc_3.png)

</details>

<hr/>

<details>
<summary>Credits:</summary>

- darkprizm (for the original Cheats mod)
- SomeoneElseE (for the updated version of the Cheats mod and used as the initial codebase of MCM)
- Tektaara (for the dependency and the summon fix)
- forgotp (for being a central point to find the Cheats mod, dependency and the summon fix)
- Teravisor (for the code to toggle the Dirty stat, NoFriendlyFire mod, and the Summon Menu mod that the original Cheats mod was based on)
- DocNITE (for the code used in the translation support)
- Zhong Xina | z洪ξ那 (for the RUS manual translation)
</details>
