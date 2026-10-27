# OpenSkater test builds

OpenSkater is an engine reimplementation of the classic Tony Hawk's Pro
Skater games (THPS1 to THPS4 and their many versions), written in C++20 with
SDL3 and OpenGL. It reimplements the original skater physics, tricks,
careers and goals, and **imports the levels, skaters, music and sounds from
your own legally owned copies of the games**.

**No game data is included** in these downloads or in this repository, and
none will be provided. To play, you need your own copies of the games.

OpenSkater is an independent project. It is not affiliated with, endorsed
by or connected to Activision, Neversoft, Electronic Arts or any other owner
of the games it supports. All trademarks belong to their owners.

> **These are test builds.** They come straight from development, are
> unfinished, and will have bugs. Saves and settings may be reset between
> builds. Please report what you find (see [Reporting bugs](#reporting-bugs)).

## Downloads

Get the newest build from **[Releases](../../releases)**. Each release has:

| File | For |
|---|---|
| `openskater-<date>-<commit>-windows-x86_64.zip` | Windows 10/11, 64-bit |
| `openskater-<date>-<commit>-linux-x86_64.tar.gz` | Linux, 64-bit (glibc 2.35 or newer) |
| `ffmpeg-source-<version>.tar.gz` | the source of the included ffmpeg (you don't need it to play) |
| `SHA256SUMS` | checksums of the files above |

Unpack the archive anywhere you can write to (not `C:\Program Files`).
Nothing needs installing: ffmpeg for the importer is included. Everything
OpenSkater writes stays in that folder:

```
openskater(.exe)      the game
osimport(.exe)        the importer (the game runs it for you)
osgames(.exe)         the game's Games screen on the command line
oscheck(.exe)         checks imported packs
ffmpeg(.exe)          converts music and movies for the importer (reduced LGPL build)
games.json            every game version OpenSkater recognises
gamecontrollerdb.txt  extra gamepad mappings
fonts/                HUD fonts (Noto Sans, SIL Open Font License)
import/               put your games here
data/                 created by the first import: imported packs, settings, career saves
openskater.log        (Windows) the game's log, written on each start
```

To check a download: `sha256sum -c SHA256SUMS --ignore-missing` (Linux) or
`Get-FileHash <file>` (PowerShell) and compare with `SHA256SUMS`.

## System requirements

- **CPU:** 64-bit x86 (x86-64).
- **GPU:** with OpenGL 3.3 core profile drivers (most GPUs from about 2010
  on, including integrated Intel/AMD graphics).
- **Windows:** Windows 10 or 11, 64-bit. No runtimes to install (the
  programs use only Windows' own DLLs).
- **Linux:** x86-64 with glibc 2.35 or newer (Ubuntu 22.04, Debian 12,
  Fedora 36, Arch, SteamOS 3 and later), X11 or Wayland, and the usual
  desktop libraries (OpenGL/Mesa or your GPU driver; PipeWire, PulseAudio
  or ALSA for sound). These are loaded at run time, as on any desktop.
- **Disk space:** imported packs need about 0.5 to 1 GB each for THPS1,
  THPS2 and THPS2X, about 4.5 GB for THPS3 and up to 11 GB for THPS4 with
  every platform imported, plus your game images.
- A gamepad is recommended (Xbox, PlayStation, Switch and most others work).

## Supported games

**Minimum recommended set:** THPS2X (Xbox), THPS1 (PlayStation, USA) and
THPS2 (PlayStation, USA). These three give the most complete experience:
both original careers and the 2X remaster with its own career and five extra
levels. THPS1 plays without THPS2X; with THPS2X imported, THPS1 skaters
use THPS2X's animations by default. Add the Dreamcast THPS1 and THPS2
for higher-detail models and textures in those games, and THPS3/THPS4 Xbox
if you want to try the later games.

Status: **playable** = Free Skate and the career work from start to end;
**partial** = levels and skaters work, the career is incomplete;
**experimental** = Free Skate only or command line only, expect problems.
Where a version merges into another one's pack, its levels, skaters and
textures can be chosen under *Options > Platform Look*.

| Game | Version | Files | Status | What it adds | Recommended |
|---|---|---|---|---|---|
| THPS1 | PlayStation USA | `.cue`+`.bin`, `.chd` | playable | the base THPS1 pack: 9 levels, 12 skaters, the career (plays on its own; THPS2X adds its animations and stats, and level background sounds) | **Yes**, the THPS1 base |
| THPS1 | PlayStation Europe (*Tony Hawk's Skateboarding*) | `.cue`+`.bin`, `.chd` | playable, merges into THPS1 | 3 songs only on this release | Optional: the European songs |
| THPS1 | PlayStation Japan | `.cue`+`.bin`, `.chd` | playable, merges into THPS1 | revised School, retextured Rowley and Warehouse wall, Japanese menu art | Optional: Japan-only look |
| THPS1 | Dreamcast USA / Europe | `.chd` | playable through the PlayStation career, merges into THPS1 | higher-detail skaters, boards and textures, used where they have more detail | **Yes**, best THPS1 assets |
| THPS1 | April 9, 1999 prototype | `.cue`+`.bin` | experimental: Free Skate only, own pack | 4 levels not in the retail game and 6 earlier layouts, early skaters | Optional: unique prototype levels |
| THPS1 | N64 (USA, Rev 1) | `.z64` | partial, own pack | the N64 versions of 9 levels, N64 models and sounds; skaters need THPS2X | Optional: N64 look |
| THPS1 | N-Gage v2.8 | game folder | experimental: Free Skate only, Tony Hawk only | little: its decks and levels exist elsewhere | No, nothing unique |
| THPS2 | PlayStation USA | `.cue`+`.bin`, `.chd` | playable | the base THPS2 pack: 11 levels, 35 skaters, the career, Create Skater, premade parks | **Yes**, the THPS2 base |
| THPS2 | PlayStation Japan | `.cue`+`.bin`, `.chd` | playable, merges into THPS2 | a Japan-only deck and a sign in School II | Optional |
| THPS2 | PC USA | `.iso` | playable, merges into THPS2 | Freeway, Rasta, 12 extra decks, full-length songs, THPS1 levels as extras (textures are the same resolution as the PlayStation's) | Yes: unique level, skater and longer songs |
| THPS2 | PC Korea | `.iso` | playable, merges into THPS2 | the four Fin.K.L. skaters and 7 Fin.K.L. songs | Optional: unique skaters and songs |
| THPS2 | Dreamcast USA | `.chd` | playable through the PlayStation career, merges into THPS2 | higher-detail skaters, boards and textures; Trixie | **Yes**, best THPS2 assets |
| THPS2 | N64 USA | `.z64` | partial, own pack | the N64 versions of 9 levels, N64 models and sounds | Optional: N64 look |
| THPS2 | March 2000 demo (US / Europe / Australia) | `.cue`+`.bin` | experimental: Free Skate only, own pack | an early Marseille with a different layout, demo physics rules, unique sounds | Optional: prerelease content |
| THPS2 | E3 demo (May 9, 2000) | `.cue`+`.bin` | experimental: Free Skate only, own pack | 9 early levels with different geometry, 26 early outfits, an earlier song mix | Optional: prerelease content |
| THPS2X | Xbox | extracted disc folder | playable | 5 levels only in 2X (Club, Construction, Skatepark Florida, Skyline, Subway), THPS1 levels in a THPS2-style career, high-detail models and textures, extra decks | **Yes**, needed for the THPS1 prototype and Dreamcast THPS1 |
| THPS3 | Xbox (Europe) | `.iso` | partial: career with classic goals and competitions; scripted goals and native physics missing | the THPS3 base pack; Skater X, Oil Rig | Yes, if you want THPS3 (the base) |
| THPS3 | PC | CD or install folder | partial, merges into THPS3 | Doomguy, extra sounds | Optional |
| THPS3 | PlayStation 2 (Europe) | `.iso` | partial, merges into THPS3 | the Paris level, skater effects | Optional: unique level |
| THPS3 | PlayStation 2 (Japan) | `.iso` | partial, merges into THPS3 | three Japan-only skaters, about 20 decks | Optional: unique skaters |
| THPS3 | GameCube (Europe) | `.iso`, `.ciso` | partial, merges into THPS3 | an alternative look, extra sounds | No, nothing unique |
| THPS3 | PlayStation USA | `.cue`+`.bin` | partial: no complete career; own pack | the PlayStation THPS3 (9 levels, Wolverine) | Optional: a different game |
| THPS4 | Xbox USA | `.iso` | partial: every level is reachable, about half the goals work; no Create Skater | the THPS4 base pack and its skaters | Yes, if you want THPS4 (the base) |
| THPS4 | PlayStation 2 USA (v2.01) | `.iso` | partial, merges into THPS4 | an alternative look | No, nothing unique |
| THPS4 | GameCube USA | `.iso`, `.ciso` | partial, merges into THPS4 | an alternative look, the GameCube skaters | Optional |
| THPS4 | PC | install media or folder | partial, merges into THPS4 | an alternative look | No, nothing unique |
| THPS4 | PlayStation USA | `.cue`+`.bin` | partial: about 30 of 196 challenges; own pack | the PlayStation THPS4 (8 levels) | Optional: a different game |
| Spider-Man | PlayStation USA | `.iso` | playable as skaters (needs THPS2) | Spider-Man (with his costumes), Venom, Carnage and others as skaters in THPS2 | Optional: fun extra skaters |
| THUG | PC | install folder | experimental: Free Skate and some challenges; command line only (needs THPS4) | 15 levels, the THUG skaters and 76 songs | Not yet |
| THUG2 | PC | install CDs (merged) or folder | experimental: Free Skate only, no music yet; command line only | 16 levels, the THUG2 pros and secret skaters | Not yet |
| Skater XL | board mods (deck, grip, wheels) | mod folders | playable | community deck, grip and wheel graphics | Optional |

Not importable in these builds: Skate 3, THPS2 Game Boy Advance,
THPS3 N64, THPS HD, LEGO Island and the other games. Some of them are being
researched, and none of that work is part of these builds.

## Getting started

### 1. Get your games ready

You need your **own, legally owned** copies of the games: images you made
of your own discs, dumps of your own cartridges, or your installed PC games.
OpenSkater recognises each version by its file sizes and checksums, and
still imports other good dumps, shown as "Unverified dump".

Put them in the `import` folder next to the game (subfolders are fine).
The formats each version is read from are in the table under
[Supported games](#supported-games). A few notes:

- Disc images: `.cue` with its `.bin`, `.iso` or `.chd`. PlayStation discs
  can be `.cue`/`.bin` or `.chd`; Dreamcast discs must be `.chd`.
- N64 cartridges must be `.z64` (big-endian). `.v64`/`.n64` dumps are
  recognised but must be converted to `.z64` first.
- **THPS2X** is imported from the disc's files, not the `.iso`: extract
  your Xbox disc to a folder (one that contains `default.xbe` and
  `CDParks.txt`), for example with extract-xiso.
- PC games: the CD's contents or the installed game's folder.
- `.zip` files are recognised but not read: unzip them first.

Some versions build on others. The Games screen orders the imports and
says when something is missing:

- **THPS1 PlayStation** (USA, Europe, Japan) imports on its own. If
  THPS2X (Xbox) is imported or in `import/`, import it first: THPS1 then
  also gets THPS2X's animations (the default) and stats.
- **THPS2X first** for the THPS1 prototype and Dreamcast THPS1. The
  Dreamcast versions also need the PlayStation version of the same game
  imported first.
- THPS2 PlayStation USA is the base of the THPS2 pack. THPS2 PC, Japan,
  Dreamcast and Spider-Man need it.
- THPS3 Xbox and THPS4 Xbox are the bases of their packs; the other
  platforms merge into them as alternative looks.

### 2. Import (the easy way)

1. Start the game: on Windows double-click **`openskater.exe`**; on
   Linux run `./openskater` in the folder.
2. With nothing imported yet, the game opens **Main Menu > Games**. It lists
   every version it knows, with what it found in `import/`:
   **AVAILABLE** (ready), **NEEDS DATA** (something else is needed first;
   the details say what), **IMPORTED**, **UPDATE** (a newer importer
   exists for it) or **MISSING**.
3. Choose **Import All Available**. (If you add games while the game is
   running, choose **Rescan** first.) Each import takes from under a minute
   to a few minutes. The log is shown on the right. A failed import leaves
   everything already installed untouched.
4. When it is done, go back to the main menu and pick **Free Skate** or a
   **Career**.

Add more games to `import/` at any time and import them from
**Main Menu > Games**.

### Updating

When a new test build changes how a game is imported (a fix to levels,
skaters, textures...), the game notices at start-up and asks: **Import
now** re-imports what changed (with what depends on it) and shows the
progress, **Later** asks again next time, **Don't ask again** turns the
check off. **Options > Imports** sets this: **Ask** (default),
**Automatic** (re-import without asking) or **Off**. The Games screen
shows those versions as **UPDATE**; `osgames update` does the same from
the command line (`osgames update --dry-run` lists what it would do).
Keep the game discs in `import/` so updates can run.

### 3. Import from the command line (optional)

`osgames` does exactly what the Games screen does, without a window. Run
it in the OpenSkater folder. It uses `data/` and `import/` next to it.

Windows (PowerShell, in the OpenSkater folder):

```powershell
.\osgames.exe scan              # what is in import\ and what each version needs
.\osgames.exe plan all          # the order it would import in, and what is missing
.\osgames.exe import all        # import everything available
.\osgames.exe update            # re-import what a new build changed
.\osgames.exe import thps2-ps1-usa   # or one version, by the id scan shows
.\oscheck.exe                   # check every imported pack
```

Linux:

```sh
./osgames scan
./osgames plan all
./osgames import all
./osgames update
./osgames import thps2-ps1-usa
./oscheck
```

Options: `--import-dir <folder>` scans another folder (can be given more
than once), `--data <folder>` imports somewhere other than `data/`, and
`--no-hash` skips the checksum check (faster; the dump is then not verified).
Full usage: `osgames --help`.

`oscheck` loads every imported skater and level and checks them (skeletons,
textures, restarts that land on the ground). It prints a summary and exits
with code 1 if it finds a problem. `oscheck --only thps2` checks one pack;
add `--verbose` for every item. Please attach its output to import bug
reports.

`osimport` is the importer itself. The Games screen and `osgames` choose
its arguments for you, so you should not need it; `osgames plan all`
prints the exact commands it would run. For reference, typical ones (Linux
shown; on Windows use `.\osimport.exe` and `data\packs`):

```sh
./osimport thps2x "import/THPS2X" pack data/packs
./osimport "import/Tony Hawk's Pro Skater (USA).cue" pack data/packs --thps2x "import/THPS2X"   # --thps2x optional
./osimport "import/Tony Hawk's Pro Skater 2 (USA).cue" pack data/packs --thps2x "import/THPS2X"
./osimport pc "import/Tony Hawk's Pro Skater 2 (PC).iso" pack data/packs
./osimport dc "import/Tony Hawk's Pro Skater 2 (USA).chd" pack data/packs
./osimport n64 "import/Tony Hawk's Pro Skater 2 (USA).z64" pack data/packs
./osimport thps3 xbox "import/Tony Hawk's Pro Skater 3 (Xbox) (Europe) (En,Fr,De).iso" pack data/packs
./osimport thps4 xbox "import/Tony Hawk's Pro Skater 4 (USA).xiso.iso" levels data/packs
```

THPS3 and THPS4 take several steps each (levels, music, sounds, skaters,
tricks); the Games screen runs all of them in order, so use it (or
`osgames`) for those. `osimport --help` lists every command.

THUG (PC) is experimental and not imported by the Games screen or
`osgames`. To try it, import THPS4 first, then run these with the THUG
installation folder (the one with `Game/THUG.exe`), in this order:

```sh
./osimport thug pc "import/Tony Hawk's Underground" music data/packs
./osimport thug pc "import/Tony Hawk's Underground" sounds data/packs
./osimport thug pc "import/Tony Hawk's Underground" levels data/packs
./osimport thug "import/Tony Hawk's Underground" roster data/packs
```

THUG2 (PC) is experimental in the same way. It needs nothing else
imported. Point `install` at the folder with your THUG2 CDs' files merged
(the one with `Tony Hawk's Underground 2.msi` and the `.cab` files); it unpacks the game into
`data/cache/thug2-pc`, which the next two commands read:

```sh
./osimport thug2 install "import/Tony Hawk's Underground 2" data/cache/thug2-pc --cab Pre.cab,AllOth~1.cab,Models.cab,levels.cab
./osimport thug2 pc data/cache/thug2-pc/Game/Data levels data/packs
./osimport thug2 data/cache/thug2-pc/Game/Data roster data/packs
```

Imported packs are made from your games: **do not share your `data/`
folder or the packs in it.**

## Playing

Pick **Career** (each game's own goals, competitions and unlocks), **Free
Skate** (any level, no timer), **2 Player** (Trick Attack, Graffiti,
H-O-R-S-E, Tag) or the **Park Editor** from the main menu. THPS2's
**Create Skater** is in the menus once THPS2 is imported. **Network Play** (direct IP, 2 to 8 players in Free Skate) is on the main
menu and the pause menu. *Options* has video settings (resolution, fullscreen,
VSync, anti-aliasing, a PS1 look), sound, HUD style and per-game rule
presets.

| Action | Keyboard | Gamepad |
|---|---|---|
| Steer, crouch / brake | arrows or WASD | d-pad / left stick |
| Ollie (hold to charge) | Space | Cross / A |
| Flip, grab, grind / lip | J, L, I | Square / X, Circle / B, Triangle / Y |
| Spin | Q, E | L1, R1 |
| Next restart point | Backspace | Select / Back |
| Pause menu | Escape | Start |
| Menus | arrows, Enter, Escape (back) | d-pad, Cross / A, Circle / B |
| Toggle UI / stats overlay | F1 / F3 | |

In 2 Player, gamepads 1 and 2 control players 1 and 2; player 1 can also
use the keyboard. Combos, specials and tricks follow the original game of
the level and skater you choose (the rule preset can change that).

Command-line options (`openskater --help`) include
`--data <folder>`, `--skater thps2x:hawk` (pack:skater) and `--headless`.

## Reporting bugs

Report bugs in this repository's **[Issues](../../issues)**. Please include:

- the build (the date and commit in the archive name) and your OS, GPU;
- the game version(s) you imported, and the output of `oscheck` for import
  or content bugs;
- what you did, what happened, and what you expected (the original game's
  behaviour if you know it); a screenshot or video helps a lot;
- for crashes, the log: `openskater.log` in the OpenSkater folder on
  Windows, or the terminal output on Linux (run `./openskater` from a
  terminal).

Never attach game files, imported packs or anything from `data/packs`.

## Known limitations

- **THPS1 and THPS2** (and THPS2X) are the most complete: levels, skaters,
  careers, goals and tricks. Expect visual and gameplay differences from the
  originals in places.
- **THPS3 and THPS4** import their levels, skaters, music and sounds, but
  native gameplay (scripts, some tricks and restarts, goals) is partial.
- The **N64, N-Gage and PlayStation THPS3/THPS4** versions and the demos
  have incomplete careers or none (see the table above).
- **THUG and THUG2 (PC)** are listed under DEV TOOLS in the Games screen:
  experimental, not imported by Import All Available. THUG2's skaters use
  OpenSkater's own trick set for now.
- THPS2 Game Boy Advance, THPS HD and the other games are not importable.
- No macOS build yet.
- Settings, careers and created skaters live in `data/` and may be reset by
  a future build when their format changes.

## License

Test builds. The OpenSkater source code will be released under
GPL-3.0-or-later. The libraries, runtimes and fonts included in each
download keep their own licenses; see `THIRD_PARTY_NOTICES.txt` in the
download.

OpenSkater is not affiliated with, endorsed by or connected to Activision,
Neversoft, Electronic Arts or any other owner of the games it supports. All
trademarks belong to their owners. No game data is included; you need your
own legally owned copies of the games, and you must not share the packs you
import from them.
