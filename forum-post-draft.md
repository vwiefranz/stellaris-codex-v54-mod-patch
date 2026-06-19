[PLACEHOLDER DOWNLOAD LINK: https://example.com/stellaris-codex-v54-patch.zip]

Titel: Stellaris 4.4.3 - Real Space / New Arcologies Savegame-Crash Fix fuer altes Mod-Playset

Ich hatte ein aelteres Multiplayer-Savegame, das nach Entfernen/Anpassen mehrerer Mods kurz nach Monatswechsel bzw. nach wenigen Ingame-Tagen reproduzierbar abgestuerzt ist. Der finale Teststand laeuft mit Stellaris 4.4.3 und folgendem Playset:

- More Events Mod
- Real Galaxy 2.0
- Real Space 4.0
- Real Space - System Scale
- Real Space - Solar Storm
- Real Space - Colour Out of Deep
- Real Space - New Arcologies
- UI Overhaul Dynamic

Kurzfassung
-----------
Der Crash kam nicht von einem einzelnen normalen Event, sondern von mehreren Savegame-Resten und veralteten Mod-Skripten:

- Entfernte Planetary-Station-/Orbital-Stations-Reste waren noch als Planeten, Kolonien, Bauqueues und Army-Queues im Save vorhanden.
- Ein aktiver Cosmic Storm / Particle Storm versuchte, leere Real-Space-O-Sternsysteme ohne Stern-Planet zu verarbeiten.
- Mehrere Mod-Dateien enthielten noch alte Trigger/Effekte fuer Stellaris 4.4.x.

Savegame-Reparatur
------------------
Finaler reparierter Save:
hotjoin_2243.12.18_codex_repaired_v54.sav

Wichtigste Savegame-Aenderungen:

- 18 alte Stationsplaneten aus dem entfernten Planetary-Stations-/Orbital-Stations-Kontext stillgelegt bzw. aus kritischen Listen entfernt.
- 29 Bau- und Army-Queues entfernt, deren location noch auf diese geloeschten Stationsplaneten zeigte.
- Globalen Alt-Flag has_planetary_stations_mod entfernt.
- Verwaiste Controller-/controlled_planets-Referenzen der ehemaligen Stationskolonien bereinigt.
- Kaputten aktiven particle_storm mit ID 1 entfernt, weil er leere Systeme ohne Stern-Scope tickte.
- 23 leere sc_o-Systeme repariert, indem sie je einen minimalen pc_o_star-Sternkoerper, eine leere Bauqueue und einen stabilen Namen "Codex Node <ID>" bekommen haben.
- Continue-Game wieder auf den reparierten Einstiegssave gesetzt.

Der Save wurde anschliessend automatisiert gestartet, geladen, entpausiert und 600 Sekunden Echtzeit laufen gelassen. Dabei entstanden Autosaves bis 2247.01.01 / Screenshot bei 2247.04.01, ohne neuen Crash.

Mod-Aenderungen nach Mod
------------------------
Real Space - Solar Storm
- solarstorm_scripted_triggers.txt:
  Alte Ark-Ship-Abfrage auf aktuelle military_arkship_* Ship Sizes angepasst.

Real Space 4.0
- 00_star_classes.txt:
  Fehlerhafte/alte Star-Class-Reste bereinigt, die fehlende DDS-Pfade ausloesen konnten.
- realspace_scripted_effects.txt:
  Veraltete create_pop-Nutzung auf create_pop_group migriert.
- system_ambient_effects.txt:
  Falschen Scope beim kaleidoscope_planet-Flag korrigiert, remove_planet_flag -> remove_carrier_flag.
- federations_initializers.txt:
  has_planet_flag -> has_carrier_flag fuer Earth-Check; ungueltige colossus_yards/titan_yards entfernt.
- pre_ftl_initializers.txt, special_system_initializers.txt, utopia_initializers.txt:
  Kompatibilitaetsanpassungen fuer aktuelle Pop-Erzeugung / Initializer-Scopes.
- 18_dyson_swarm.txt:
  Nicht vorhandene Cybernetics-Eventverweise entfernt.

Real Space - New Arcologies
- newarcologies_jobs.txt:
  Ungueltigen job weight modifier ersetzt: mult = value:job_weights_modifier|... -> factor = 1.25.
- newarcologies_districts.txt:
  Nicht mehr existierende convert_to-Ziele entfernt/bereinigt.

Nicht geaenderte Mods im getesteten Playset
-------------------------------------------
- More Events Mod
- Real Galaxy 2.0
- Real Space - System Scale
- Real Space - Colour Out of Deep
- UI Overhaul Dynamic

Installation der Patch-Zip
--------------------------
Die Zip ist ein Overlay fuer bereits installierte Steam-Workshop-Mods.

1. Stellaris und Launcher schliessen.
2. Zip in den Steam steamapps Ordner entpacken, z.B.:
   E:\Programme\Steam\steamapps
3. Dateien ersetzen lassen.
4. Das oben genannte Playset aktivieren.
5. Den reparierten Save v54 laden.

Wenn Steam anders installiert ist, in den Ordner entpacken, der den Unterordner
workshop\content\281990 enthaelt.
