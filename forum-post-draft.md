Title: Stellaris 4.4.3 Save Crash Fix - Real Space / New Arcologies Mod Patch

Repository:
https://github.com/vwiefranz/stellaris-codex-v54-mod-patch

I repaired an older modded Stellaris multiplayer save that crashed shortly after loading, usually around the next monthly tick. The issue was not caused by one single event, but by a mix of stale savegame data and outdated mod script entries after the playset had changed.

Tested playset:

- More Events Mod
- Real Galaxy 2.0
- Real Space 4.0
- Real Space - System Scale
- Real Space - Solar Storm
- Real Space - Colour Out of Deep
- Real Space - New Arcologies
- UI Overhaul Dynamic

What was fixed:

- Removed broken leftovers from old Planetary Station / Orbital Station content inside the save.
- Cleared invalid construction and army queues pointing to deleted station planets.
- Removed stale controller and controlled-planet references.
- Removed a broken active particle storm that was ticking empty Real Space O-star systems.
- Repaired empty `sc_o` systems by adding minimal stable O-star bodies.
- Updated several outdated Real Space / New Arcologies script entries for Stellaris 4.4.x compatibility.

Mod patch summary:

- Real Space 4.0: fixed old pop creation effects, invalid initializer scopes, broken flag scopes, missing/invalid star-class data, and removed obsolete Cybernetics event references.
- Real Space - Solar Storm: updated Ark Ship trigger checks to current ship size names.
- Real Space - New Arcologies: fixed invalid job weight syntax and removed obsolete district conversion targets.

Mods not directly changed:

- More Events Mod
- Real Galaxy 2.0
- Real Space - System Scale
- Real Space - Colour Out of Deep
- UI Overhaul Dynamic

Verification:

The repaired save was loaded, unpaused, and tested for 600 seconds without a new crash. Autosaves reached `2247.01.01`, and the game was still running at `2247.04.01`.

Installation:

Download the overlay from the GitHub repository, close Stellaris and the Paradox Launcher, then extract the patch into your Steam `steamapps` folder so it merges into:

`workshop\content\281990`

Back up your Workshop mod folders before replacing files.
