# Changelog - Dark Colony Ultimate installer

The features the patcher `patcher/Apply-DarkColonyPatches.ps1` adds to the game and the bugs it fixes, and the same
for the installer itself. Dates are the commit dates in the two repositories the patcher is generated from,
[Dark-Colony](https://github.com/endotermic/Dark-Colony) and
[Dark-Colony-Server](https://github.com/endotermic/Dark-Colony-Server); how every fix was found is in the latter's
`docs/DC16_DISPLAY_AND_RESOLUTION.md`, and `INSTALL.CMD -List -Detail` prints every fix with every byte it changes.

The patcher builds two executables: **Dark Colony Ultimate** (from the Council Wars original `ENGEXP16.EXE`: Council
Wars plus the Dark Colony, Academy and OZI campaigns) and **Dark Colony Map Editor** (from `maped.exe`). Installer
versions exist since 2 October 2026; the history before that is dated. Versions that changed nothing for the player
(2.5: how the package is distributed; 2.6: a picture that no screen reaches no longer ships) are not listed.

## Installer versions

### 2.4 - 5 October 2026

- **No intro movie at start-up** (fix `intro`): the main menu comes up at once; DARK COLONY and COUNCIL WARS each
  play their own intro right before the campaign starts.

### 2.3 - 5 October 2026

- Dark Colony Ultimate plays the whole Dark Colony campaign (DARK COLONY and ACADEMY in its menu, their saves under
  LOAD GAME), so the separate Classic executable "Dark Colony.exe" is no longer built. The installer knows two
  executables.

### 2.2 - 5 October 2026

- Bugfix: OZI MISSIONS works in a game folder that has no `ozisave\` folder yet - the installer creates it and its
  marker file.

### 2.1 - 5 October 2026

- **The soundtrack is ripped from your discs**: audio tracks 2-5 of both CDs (from a `.bin` / `.cue` image or a real
  drive) are encoded to MP3 with Windows' own encoder, so the music plays in the game. An `.iso` holds the data track
  only.

### 2.0 - 5 October 2026

- **Install the game from the two original discs**: a checkbox on the welcome page (ticked by itself when no game
  folder is found) adds a "Game discs" page - a disc image (`.iso`, `.bin`, `.cue`) or a mounted / real drive for each
  disc and the install folder. The right discs are checked, the game is copied (about 480 MB), the executables are
  built in the new folder. An interrupted install can be resumed into the same folder. Also on the command line
  (`-InstallDir`, `-CouncilWarsDisc`, `-DarkColonyDisc`).

### 1.6 - 3 October 2026

- **Frame limiter** (fix `fps`): never more than 60 frames per second - under Wine and on monitors above 60 Hz the
  battlefield scrolled and the cursor animated several times too fast.
- **Battlefield pointer animation at the menus' pace** (fix `pointer`).

### 1.4 - 3 October 2026

- Bugfix: **no save in a network battle** (fix `netsave`) - such a save could never rejoin the relay game.

### 1.3 - 3 October 2026

- **One LOAD GAME for every campaign**: the saves of Academy, Dark Colony, Council Wars and the OZI missions in one
  list, newest first, with date, time, name and campaign. The main menu becomes five rows per column; MULTI PLAYER WAR
  is labelled CUSTOM NET WAR.

### 1.2 - 3 October 2026

- `DEFAULT_SERVER.TXT` names the relay (`name=`) as well as its address; both online screens show a Name: line. A file
  with your own relay address is never overwritten.
- Bugfix: a start-up crash at the cursor lock.

### 1.1 - 2 October 2026

- Bugfix: under a Turkish or Azerbaijani Windows regional format the interface set was written wrong - the battlefield
  was laid out like a menu, with the tabs and the DAYS count drawn inside the map.

### 1.0 - 2 October 2026

- **REPLAY ONLINE GAME**: watch the battles the relay recorded, from any participant's seat.
- **Tracer bullets**: the human trooper and the Lieutenant fire a visible streak, the Gray trooper keeps its bolt at
  every weapon upgrade level, the Gray commander's pistol fires the Gray bolt.
- Bugfix: a HUD script of one resolution could end up under the frame of another ("interface elements are not in
  place"); every resolution now has its own interface folder and a run removes every other size's folder.
- Bugfix: at 1024x768, 1280x720 and 1280x1024 the camera snaps to a half tile, so the marker and ground clicks are
  aligned.
- The installer shows its version and build number.

### Before the version numbers (14 September - 1 October 2026)

- **1 Oct 2026** - the installer becomes a classical setup wizard (Welcome, Options, one page per executable, Ready to
  patch, Finished). **The battlefield interface, light (classic) or dark (console style)**, is chosen on the options
  page next to the resolution, nothing preselected. Everything a screen size changes is one fix. Default game speed
  150 % is back. The map editor un-greys **everything** the editor shipped greyed out (ten new unlocks). A realistic
  Mars backdrop under the main menu and every pre-battle screen.
- **28-30 Sep 2026** - the battlefield HUD, the save / options / objectives / quit dialogs and the clock dial redrawn
  in the console style of the menus; main menu opening order; fast screen loads; six chat lines with a sound; the
  games DPI-aware; 1920x1080 and 1920x1200 added; **ONLINE WAR** (29 Sep). Bugfixes: ONLINE WAR lost the connection
  when entering a room; at 1280x720, 1920x1080 and 1920x1200 the lower chat line sat inside the bottom bar and a black
  line showed over the bar.
- **25 Sep 2026** - one-click installer: `INSTALL.CMD`, all executables in one wizard, the builds named "Dark Colony
  Ultimate.exe" and "Dark Colony Map Editor.exe", desktop shortcuts, the high-resolution icon. Dark Colony Ultimate
  plays both discs' music with a DC / CW / ALL choice in the battlefield options. Bugfixes: a network game started
  after OZI MISSIONS went out of sync; Ultimate and Classic players desynced at the first Gray commander rally; the
  game asserted at start-up under Wine on `sound\sound2.dat`.
- **23 Sep 2026** - Council Wars plays the **original Dark Colony campaign** from its main menu; ACADEMY saves go to
  the Dark Colony folder.
- **22 Sep 2026** - sound files load from any folder depth; the CD soundtrack from MP3 files; maps narrower than the
  screen; 3840x1080 (32:9); the window gets a progress box and a success / failure message.
- **21 Sep 2026** - camera clamped at battle start; window restore after minimising; the **screen resolution
  drop-down** with the interface data built at patch time; an already patched exe chosen as "original" is redirected
  to the untouched one beside it; a missing file is named instead of asking for the CD.
- **18 Sep 2026** - the game no longer touches the CD drive at all (no more "No Disk" box or hang on PCs with a
  not-ready drive D:).
- **15 Sep 2026** - the **map editor** joins the patcher (the ozi_ns unlocks, in English) with the Atlantis block
  set, so New Map -> Atlantis works out of the box; fixes whose data files are missing are greyed out as
  "[RESOURCES NOT FOUND]" instead of producing an exe that fails at start-up.
- **14 Sep 2026** - the patcher: the patched executables rebuilt from the untouched originals fix by fix, every byte
  edit readable with its reason, SHA-256 of original and result checked; fixes that only work together are refused
  apart; the untouched originals run beside the patched exes from the same folder.
- **9-13 Sep 2026** (before the patcher, as hand-patched builds) - 1024x768; Windows pointer hidden; 32 MiB memory
  pool; OZI MISSIONS menu mode; default game speed 150 %; two-monitor start-up hang fixed; centred battlefield
  dialogs and a moving day/night clock hand.

## Dark Colony Ultimate - bugs fixed

- **No CD, and no CD path at all** (`nocd`; 28-30 Sep 2025, 18 and 21 Sep 2026). The game refused to start and greyed
  out most menu buttons without its CD, and Council Wars threw the player out of a running game. Bypassing the test
  was not enough: the game still read the drive letter recorded at install time, probed `D:\dc\anim.dat` with a write
  test at start-up, at every menu screen and during battle, fell back to the CD for missing files and asked to
  "insert the CD" - on a PC where D: is a card reader, an empty DVD drive or a sleeping second disk Windows' "No
  Disk" box appeared behind the full-screen game (a black screen that looked like a hang) or the game stalled. The
  whole CD machinery is gone; a missing file is reported as "FILE NOT FOUND / <name>" with a line in `error.log`
  instead of a CD prompt that waited forever.
- **Windows pointer stays hidden** (`cursor`; 10 Sep 2026). The system pointer flickered over the game's own cursor on
  a modern Windows: an arrow on the loading screen, a block in the menus and in battle.
- **Local memory pool 11.5 MB -> 32 MiB** (`pool`; 10 Sep 2026). At the HD sizes the screen backgrounds and extra
  sprite banks exhausted the game's memory arena ("SMalloc: Out of memory in local pool").
- **Two-monitor start-up hang** (`ddraw`; 13 Sep 2026, cursor-lock crash 3 Oct 2026). With two monitors the mode switch
  made DirectDraw drop every surface a second later and the game asserted into a message box hidden behind the full
  screen: black screen, apparent hang. The start-up continues and the game's own per-frame restore repairs the
  surfaces. Also removes a start-up crash at the cursor lock.
- **Fast screen loads** (`palette`; 28 Sep 2026). Every screen change cost 512 full-screen surface transfers on
  Windows 11 (1.4-1.5 s at 1024x768, 3.2-3.5 s at 1920x1200 - every menu loaded slower the larger the resolution).
  The palette conversion is computed in place; screens change in a fraction of a second.
- **Camera clamped at battle start** (`camera`; 21 Sep 2026). With the enlarged HD view, a start position within 11
  tiles of the far map edge crashed the game the moment the battlefield appeared (hidden behind the full screen; a
  relay then dropped the player). Hit on the live server with start position 0 of "Plink - O"; Armageddon, Circle of
  Friends, Olympus Mons and others were affected the same way.
- **Maps narrower than the screen** (`widemap`; 22 Sep 2026). A view wider than the map (64-tile maps at 1280x800 and
  up, every map at 3840x1080) made the terrain drawer read outside the map (a crash at the top and bottom rows), lit
  and scanned the wrong rows, silenced the ambient sounds and sent units to the far side of the map on a click in the
  black margin. The view is centred on the map and every map read stays inside it.
- **Window restore after minimising** (`restore`; 21 Sep 2026). After Alt+Tab or the Win key the game stayed
  minimised although active, or came back as a black window at desktop resolution. Alt+Tab and the taskbar bring it
  back; a minimised game no longer burns a whole processor core, and a multiplayer client stays in the game meanwhile.
- **Sound files load from any folder depth** (`longpath`; 22 Sep 2026, Wine part 25 Sep 2026). Installed under a long
  path (a ZIP extracted under Downloads and moved deeper) the game died five seconds after start with "FILE NOT FOUND /
  A sound file is missing" and an empty file name. The error now names the file, and the game starts from any path.
  Also fixes the start-up assert on `sound\sound2.dat` under Wine.
- **No save in a network battle** (`netsave`; 3 Oct 2026). The Game Option tab offered Save Game (and F11) in a network
  battle, and loading such a save resumed a solo game against frozen opponents instead of rejoining the relay game.
  Saving is off while a network game runs; campaign, skirmish and training battles save as before.
- **Frame limiter** (`fps`; 3 Oct 2026). The game was paced only by the monitor's vertical blank. Under Wine the loop
  ran at 350-380 frames per second - the map crossed in a quarter of a second, the cursor flickered - and a 144 Hz
  monitor was 2.4 times too fast. Never more than 60 frames per second; a 60 Hz Windows monitor is unchanged.
- **Battlefield pointer animation at the menus' pace** (`pointer`; 3 Oct 2026). In battle the crosshair cycled 30
  times a second, twice as fast as in the menus. The battlefield steps it every 33 ms like the menus.
- **DPI-aware** (part of `icon`; 27-28 Sep 2026). Windows scaled the full-screen picture by the desktop's display
  scaling: at 150 % a 1920x1080 or 1920x1200 game was shown at 1.5x with two thirds off the screen, and 1024x768,
  1280x720 and 1280x800 as a two-thirds picture in the top-left corner. The game is per-monitor DPI-aware and is shown
  1:1 at every resolution.
- **Network games stay in sync** (`ozi`; 25 Sep 2026). A network game started after OZI MISSIONS used the pack's
  balance tables and desynced against every other player; a Gray commander's rally animation desynced Ultimate
  against Classic players. A network game always starts in the Dark Colony mode, and the commanders of all campaigns
  rally in their stand pose.
- **ONLINE WAR no longer loses the connection when entering a room** (`online`; 29 Sep 2026).

## Dark Colony Ultimate - features

- **Any screen resolution** (`resolution`; 9-14 Sep 2026, more sizes 22 and 27 Sep 2026). 1024x768 (4:3), 1280x1024
  (5:4), 1280x720 (16:9), 1280x800 (16:10), 1920x1080 (16:9), 1920x1200 (16:10) or 3840x1080 (32:9) instead of the
  hard-wired 640x480 - a battlefield of 28x23 tiles at 1024x768 (2.9x the stock view) and more at the larger sizes,
  the HUD at its native size on the right and bottom edges, the menus letterboxed over the Mars backdrop in a grey
  panel frame, movies stretched to 16:9 across the full width, the day/night clock on the rebuilt HUD. The installer
  writes the interface set for the chosen size itself. The sizes with your monitor's aspect ratio are marked
  "recommended for your screen"; 640x480 (original) is still available.
- **Dark battlefield interface** (`console`; 28-30 Sep 2026, a choice since 1 Oct 2026). The brushed-metal HUD redrawn
  in the console style of the menus: grey pipework frame, buttons on red-ringed black plates with the original unit
  and building portraits, black dialogs with grey tube frames, a redrawn day/night dial with sun and moon. Or keep the
  **light (classic)** interface, the original metal frame at the new size.
- **Default game speed 150 %** (`speed`; 10 Sep 2026, back since 1 Oct 2026). The GAME SPEED slider still changes it
  in game; multiplayer speed comes from the relay, saved games keep their own.
- **Original CD soundtrack from MP3 files** (`music`; 22 Sep 2026, DC / CW / ALL 25 Sep 2026). The music was never a
  file - the game played the CD's audio tracks, so without a CD-ROM drive it was silent for good and the music slider
  did nothing. The game plays `MUSIC\TRACK02-05.MP3` and `exp\music\track02-05.mp3` (ripped from your discs by the
  installer) with whole-disc repeat as the original, the slider sets the volume, and the battlefield options get a
  MUSIC row: DC, CW or ALL (all eight tracks shuffled). The campaign you start sets the default.
- **Main menu opens in order** (`menuorder`; 28 Sep 2026): the DC logo, the DARK COLONY title, the button wave top to
  bottom, the credits - the original ran the buttons first and showed the brand mark last.
- **Battlefield chat: six lines, announced** (`chat`; 28 Sep 2026). In a network battle only the two newest chat lines
  were shown, silently. Up to six lines stay on screen and every new line plays the mission-message sound.
- **DARK COLONY and OZI MISSIONS menu modes** (`ozi`; 10 Sep 2026, DARK COLONY 23 Sep 2026, tracers 2 Oct 2026).
  **OZI MISSIONS**: the 22 missions of the 2010 ozi_ns mission pack (11 Human, 11 Gray, with their briefings, story
  texts, units and sounds) play from the main menu, saves in `ozisave\`. **DARK COLONY** and **ACADEMY**: the original
  Dark Colony campaign and its training missions from the Council Wars executable, saves in `save\`. **Tracer
  bullets**: the human trooper and the Lieutenant fire a visible streak, the Gray trooper keeps its glowing bolt at
  every upgrade level, the Gray commander's pistol fires it too.
- **No intro movie at start-up** (`intro`; 5 Oct 2026). The game played the Council Wars intro before the menu whatever
  you were going to do, and the Dark Colony intro was never played by this build. The menu comes up at once; DARK
  COLONY plays the Dark Colony intro and COUNCIL WARS the Council Wars intro right before the race and name screen;
  ACADEMY, OZI MISSIONS and LOAD GAME play nothing; SPACE skips as before.
- **High-resolution icon** (`icon`; 25 Sep 2026). The exe carried a 32x32 16-colour icon that Windows blew up into a
  blur on the desktop, in Explorer and on the taskbar; now every size from 16 to 256 pixels, and the game window and
  the taskbar show it too.
- **ONLINE WAR** (`online`; 29 Sep 2026). A room browser for the free relay server at the top of the right menu
  column: the relay's rooms with map, terrain, seats, players, bots and status; pick one and the usual lobby follows.
  TLS-encrypted on port 8889; the relay's name and address come from `DEFAULT_SERVER.TXT`, so your own relay (or a
  LAN relay without a certificate) is one line away. The relay's bots are the game's own AI ("AI Mercenary", "AI
  Marauder", ...). CUSTOM NET WAR and the network play itself are untouched.
- **REPLAY ONLINE GAME** (`online`; 2 Oct 2026). The battles the relay recorded (the newest 50: date, map, terrain,
  seats, players, length) and the eight players of the selected one; REPLAY plays the battle back from that player's
  seat with his fog of war - scroll the map, open the dialogs, watch.
- **One LOAD GAME for every campaign** (`online`; 3 Oct 2026). The saves of Academy, Dark Colony, Council Wars and the
  OZI missions in one list, newest first, with date, time, name and campaign; LOAD resumes the chosen one in its own
  campaign. The save files stay where the game writes them.

## Dark Colony Map Editor - features

Every control and menu item the original editor shipped greyed out works (the code behind them was always complete);
the functional part of the Polish ozi_ns editor, without the translation, and then everything else.

- **15 Sep 2026** - New Map: the **Atlantis, Training Set and Special Set** block sets (`blocksets`; the installer
  ships the Atlantis set, so New Map -> Atlantis works out of the box; Training and Special still need the ozi_ns
  pack's files); Team Attributes: **Team Colour and Allies** (`teams`); Troop Attributes: the **Healer row**
  (`healer`); Troop Attributes: a close box instead of a sizing border (`troopsframe`).
- **25 Sep 2026** - the **high-resolution icon** (`icon`); the editor had none at all.
- **1 Oct 2026** - Team Attributes: **AI Type and AI Slots** (`race`); Scenario Stats: the **Campaign scenario type**
  (`campaign`; until now the only way to a multiplayer map was to press Multiplayer once, with no way back); File
  menu: **Super Gen, Load MED File, Save MED File** (`medfiles`; the editor's own document format, the only one that
  keeps trigger names); the **Block Type menu** (`blockmenu`); Team Attributes menu: the **City State and Troop
  Attributes dialogs** (`teamdialogs`; their menu entries pointed at nothing and are re-pointed to the dialogs);
  Troops menu: **Human and Alien Leutenant** placeable (`lieutenants`; matters for campaign scenarios, where no
  commander is generated); Artifacts menu: the **six single artifacts** (`artifacts`); the **Lights menu**
  (`lights`); the **Trigger tool and Edit Trigger String** (`trigger`); the **Flag tool and AI Flags menu**
  (`aiflags`). **Warning:** `aiflags` is a dead feature - the released game has no flag object and a placed flag
  becomes a player-0 mining tower; leave it unticked unless experimenting.
