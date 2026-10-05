# Dark Colony Ultimate - installer

*Dark Colony* (Strategic Simulations, 1997) and its expansion *The Council Wars* rebuilt for modern PCs, from **your
own original discs**. This repository is the installer only: it holds nothing of the game itself - no original
executable, no game data, no music and no patched executable.

What you get: one executable, **Dark Colony Ultimate**, with every campaign in its main menu (Dark Colony, the Academy,
Council Wars, the 22 missions of the ozi_ns pack) and one LOAD GAME for all of their saves, any screen resolution from
640x480 to 3840x1080, no CD check, the battlefield interface in the classic metal style or a new console style, the CD
soundtrack as MP3, a Windows-aware window (DPI, Alt+Tab, two monitors, fast screen loads), a frame limiter, no intro
movie at start-up, online play against players and the game's own AI through a free relay server with a replay viewer,
and the map editor with every greyed-out feature unlocked. Every fix, what it repairs or adds and when it came:
[`CHANGELOG.md`](CHANGELOG.md).

## What you need

* The two original CDs - **Dark Colony** and **Dark Colony: The Council Wars** - in a drive, or disc images of them
  (`.iso`, or `.bin` with its `.cue`). The `.bin` / `.cue` image or the real CD also carries the music: the soundtrack is
  ripped from the audio tracks and encoded to MP3 with Windows' own encoder. An `.iso` has the data track only.
* Windows 10 or 11 with Windows PowerShell 5.1 (part of Windows). Nothing is downloaded; nothing is installed beyond the
  game folder and two desktop shortcuts.

## Install

1. Download this repository as a ZIP (**Code -> Download ZIP**) and unpack it anywhere, or get the same package from
   ModDB.
2. Double-click **`INSTALL.CMD`**. Windows may warn about a file from the internet: *More info -> Run anyway*.
3. On the welcome page the box *Install the game first, from my original Dark Colony and Council Wars discs* is ticked
   by itself. Press *Next*, pick the two discs (an image file, or the drive letter of a mounted image or a real CD) and
   the install folder (*Dark Colony* in your Documents by default), press *Next* again.
4. Choose the screen resolution and the battlefield interface, press *Next* through the pages and **Patch**. The game is
   copied from the discs (about 480 MB), the soundtrack ripped and encoded, the executables built. Start the game from
   the desktop shortcut *Dark Colony Ultimate*.

Already have a game folder (for example the full [Dark-Colony](https://github.com/endotermic/Dark-Colony) repository)?
Unpack this package over it, or next to it, and run `INSTALL.CMD` there: it finds the originals and patches them in
place.

Step by step, with every page and option explained: [`PATCH_HOWTO.TXT`](PATCH_HOWTO.TXT). Command line:

```
INSTALL.CMD -InstallDir "%USERPROFILE%\Documents\Dark Colony" -CouncilWarsDisc D:\ -DarkColonyDisc "E:\Dark Colony.bin" -All -Resolution 1920x1080 -Theme dark -DesktopShortcut
INSTALL.CMD -All -Resolution 1024x768 -Theme dark          (an existing game folder beside the package)
INSTALL.CMD -List -Detail                                  (every fix with its byte edits)
INSTALL.CMD -Verify "Dark Colony Ultimate.exe"             (which fixes an exe carries)
```

## What is in the package

* `INSTALL.CMD` - the starter (runs the script below with Windows PowerShell and `-ExecutionPolicy Bypass` for that one
  run).
* `patcher/Apply-DarkColonyPatches.ps1` - the patcher (version 2.5, build 20261005.1354): a plain-text PowerShell
  script in which every byte it changes in the game's executables is listed with its reason. Open it in Notepad. It
  writes the patched executables from the untouched originals, never modifies them, and compares the result with the
  SHA-256 of the reference build. It also holds the disc file list, the disc reader and the GIF codec that builds the
  interface set for the chosen resolution.
* `patcher/game/` - the project's own data files, copied into the game folder before Dark Colony Ultimate is patched:
  the painted menu backdrops and HUD frames per resolution (`HD_SRC/<WxH>/`, seven sizes), the console-style banks and
  the redrawn clock dial of the dark interface, the logo animations re-baked for the HD sizes, the tracer bullets with
  their weapon tables, the high-resolution icon `DC_HD.ICO`, `DEFAULT_SERVER.TXT` (the relay server), the rewritten
  main-menu script, and the ozi_ns mission pack `ozi_ns/` (22 missions, briefings, texts, sounds) with the pack's units
  in `exp/`.
* `patcher/editor/` - the same for the map editor's folder: its Borland runtime DLLs and the Atlantis block set
  `scenario/atlantis.set`.
* `PATCH_HOWTO.TXT` (the player's guide), `CHANGELOG.md`, `LICENSE` (AGPLv3), this file.

Not in the package, by design: the game (every file of the two discs, including `ENGEXP16.EXE` and `maped.exe`), the
MP3 soundtrack (ripped from your discs at install time), any patched executable, and the interface-set folders
`HD_<height>P` (built on your PC by the installer).

Which disc holds which game file, and how every fix was found, is documented in the sister repositories:
[Dark-Colony](https://github.com/endotermic/Dark-Colony) (the game files and this package's source) and
[Dark-Colony-Server](https://github.com/endotermic/Dark-Colony-Server) (the relay server, the patch tools, the generator
of the script, the reverse-engineering notes). This repository is refreshed from them with
`tools/publish_installer.py` of Dark-Colony-Server.

## Credits

Dark Colony and The Council Wars are by Alternative Reality Technologies and Strategic Simulations, Inc.; this project is
not affiliated with the rights holders and distributes none of their files. The ozi_ns mission pack and the map editor
research are by ozi_ns ([darkcolony.pl](https://www.darkcolony.pl/)). The Mars backdrop uses NASA's MOLA and USGS Viking
data.

## License

The installer - `INSTALL.CMD`, the patcher script, the data files this project made in `patcher/game` and
`patcher/editor`, and the tools and notes in Dark-Colony-Server - is free software under the
**GNU Affero General Public License v3** ([LICENSE](LICENSE)): use it, change it, share it, as long as your version stays
open under the same license.

Not ours and not under that license: the game itself (the installer takes it from your discs and ships none of its
files), the ozi_ns mission pack in `patcher/game/ozi_ns` and the pack's units in `patcher/game/exp` (by ozi_ns, carried
with credit), the map editor's Borland runtime DLLs in `patcher/editor` (Borland redistributables), and the pictures
derived from the game's own art (menu backdrops with the DC logo, the metal HUD frame, the banks with the original unit
portraits) - our work on their art, shared as a mod of their game. The patched executables the installer writes on your
PC are the original 1997/98 programs with our byte changes.
