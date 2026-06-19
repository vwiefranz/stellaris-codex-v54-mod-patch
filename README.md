# Stellaris Codex v54 Mod Patch Overlay

This repository contains the patch overlay and documentation for the repaired Stellaris save/playset tested after the v54 repair pass.

The included overlay is intended for an existing Steam Workshop installation of the listed mods. It does not replace the full Workshop downloads.

## Download

Use:

`stellaris_codex_v54_mod_patch_overlay.zip`

SHA256:

`4E83454C7F2FF9FFE331D28E8B221D8EC0DAC8F3E42D07F47D6E20A5CBE8A694`

## Installation

1. Close Stellaris and the Paradox Launcher.
2. Back up your Steam Workshop Stellaris folder, usually:

   `...\Steam\steamapps\workshop\content\281990`

3. Extract `stellaris_codex_v54_mod_patch_overlay.zip` into your Steam `steamapps` folder.
4. Confirm that the extracted files merge into:

   `workshop\content\281990\...`

5. Start the Paradox Launcher and use the repaired playset.

## Tested Playset

- `727000451` - More Events Mod
- `3385530791` - Real Galaxy 2.0
- `937289339` - Real Space 4.0
- `1887282318` - Real Space - System Scale
- `1873097578` - Real Space - Solar Storm
- `1918281610` - Real Space - Colour Out of Deep
- `3082164342` - Real Space - New Arcologies
- `1623423360` - UI Overhaul Dynamic

## Verification

The repaired save was loaded through the launcher, unpaused, and tested automatically for 600 seconds without a new crash. Autosaves reached `2247.01.01`, and the game was observed still running at `2247.04.01`.

Final repaired save used for testing:

`hotjoin_2243.12.18_codex_repaired_v54.sav`

## Contents

- `stellaris_codex_v54_mod_patch_overlay.zip` - ready-to-extract patch overlay
- `workshop/` - unpacked overlay tree for review
- `MOD_PATCH_MANIFEST.txt` - mod-by-mod change manifest
- `forum-post-draft.md` - ready-to-edit forum post with placeholder download link
- `README_INSTALL.txt` / `INSTALL.txt` - short installation instructions

## Notes

This patch was prepared to rescue one specific modded save that crashed after advancing a few in-game days. The documented playset and patched files should be kept together when reproducing the repair.
