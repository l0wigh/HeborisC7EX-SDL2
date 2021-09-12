### Heboris C7EX - unofficial version (YGS2K EX)

This version contains the source code for Heboris C7EX. It requires a C
compiler, SDL 2.0, SDL 2.0 mixer, and SDL 2.0 image libraries to build and
play.

Example of installing dependencies on Ubuntu:

If using Git to get the source code, rather than downloading a zip of it from GitHub:
```sh
sudo apt-get install git
```

Building dependencies:
```sh
sudo apt-get install gcc cmake libsdl2-dev libsdl2-mixer-dev libsdl2-image-dev
```

#### Download, Build, and Run Without Installing

```sh
git clone https://github.com/nightmareci/HeborisC7EX-SDL2
cd HeborisC7EX-SDL2
cmake -B build -DCMAKE_BUILD_TYPE=Release
cmake --build build
./build/HeborisC7EX-SDL2
```

#### Changes

 - Port to use SDL 2.0 so it (probably) works on all SDL 2.0-supported platforms.
 - Change to a CMake build system.
 - Convert all source code from C++ to C.
 - Convert source code to UTF-8, so the Japanese comments are easy to work with
   on modern systems. Text strings used in-game remain Shift-JIS, though.
 - Move the script sources from merely being included in gamestart.c, out to
   being individually compiled. Massively improves compile time on multi-core,
   bad-single-threaded-performance systems.
 - Implement full support for configuration of all game inputs, for both
   keyboard and joystick input.
 - Implement advanced joystick input, allowing any mapping of joystick inputs
   to game inputs.
 - Convert to exclusively use fully cross-platform APIs, like SDL_render for
   hardware-accelerated graphics.
 - Implement comprehensive display mode settings. Vsync is included in this.
   Also includes scaling to fill the display, with a correct 4:3 aspect ratio
   viewport.
 - Revise how save data is managed, guaranteeing the format is identical across
   all platforms.
 - Fix the "low detail" 320x240 graphics setting.
 - Implement guaranteed-long-term-correct frame timing; part of that system is
   efficiently timed screen updates, only when appropriate.

#### Todo

This repository will be maintained for bug fixes and ports, but no major
changes will be made to the actual game's functionality for the most part. Some
simple fixes and changes may be added, and will be listed in this section if
so.

 - Implement automated packaging of builds. At least support Windows, macOS, and
   desktop Linux.
 - Save 40L player data state, or allow a custom setting to be saved and used
   by default.
 - Allow traditional TGM style scoring. Heboris inflates the scoring to
   compensate for B2B bonuses.
 - Put all configuration options into in-game menus.
 - Any other minor bugs/errors I can find.

#### Definitely Not Legal Advice

This software is copyrighted to Kenji Hoshimoto, but the distribution terms are
currently unknown. So, to be polite, only distribute it noncommercially, and
keep the source code available, because that's basically how it's been
distributed for its whole history.

## Heboris Overview

```text
Original changelog and description of heboris is included in the files
changelog.txt and heboris.txt.

----------------------------------------------------
1. 8 Selectable Rules
----------------------------------------------------
You can select 8 different rotation rules.

HEBORIS     : TGM1 and TGM2 style. Same as original heboris rotation.
TI-ARS      : TGM3 style. T and I piece have special ground kick(It works only once!).
TI-WORLD    : SRS, you can move 10 times, or rotate 8 times.
ACE-SRS     : SRS, you can move 128 times, or rotate 128 times
              Fast drop is slower than TI-WORLD.
ACE-ARS     : TGM-ACE style rotation rule. Really strange!
              Fast drop is slower than TI-ARS.
ACE-ARS2    : Same as ACE-ARS, except soft drop and hard drop.
              Fast drop is slower than TI-ARS.
DS-WORLD    : SRS, you can rotate or move infinity!
              Fast drop is slower than TI-WORLD.
SRS-X       : Original rotation rule based on SRS. But you can use Zangi-moves!
              You can move 24 times, or rotate 12 times.
              And C-botton is "180 degree rotarion" with original wall kicks.
D.R.S       : If you have ever played DTET,let's use this!
              Added T and I ground kick(only once!) to it.

----------------------------------------------------
2. Special modes
----------------------------------------------------
You can play these extra modes.

BIG MODE
 Start BEGINNER,MASTER,20G,DEVIL, or ACE mode
 with holding C botton.
 Blocks are always 2 times bigger.

SCORE TRIAL in BEGINNER mode
 Select BEGINNER mode and press Hold botton once.
 Default of BEGINNER mode is fireworks trial.
 But this is score trial.
 There are no Lv-stop before Lv100 and Lv200, and
 support Item block will appear.
 Goal is Lv300. If you reached Lv300 so quickly,
 you'll get time bonus.
 Back to Back will be better than combos...

ITEM MODE
 Select MASTER , 20G, or DEVIL mode and press Hold botton once (twice in DEVIL mode).
 Item blocks apeear,but attack items affects yourself.

HEBO+
 Select MASTER or 20G mode and press Hold botton twice.
 Sometimes pattern garbage appears.

TOMOYO E-Heart (ACE-Target)
 Select TOMOYO mode and press right arrow key once(twice).
 Other stages from other game(TGM-ACE).
 Always, place of platinum blocks are randomized.

TOMOYO F-Point
 Select TOMOYO mode and press left arrow key once.
 18 mimutes score challenge. (100 stages)

ANOTHER
 Select ACE mode and press right arrow key once.
 It's faster than ACE mode.

HELL
 Select ACE mode and press right arrow key twice.
 The speed is.....WTF!

OLD STYLE
 Select ACE mode and press right arrow key three times.
 Two kinds of old classic ###rises (Decided by "ARS or SRS")

DEVIL- (MINUS)
 If DEVIL-DOOM is too fast for you, let's try.
 Select DEVIL mode and press Right arrow once.

DEATH+
 Select DEVIL mode and press Hold botton once.
 Only one next display and no Hold!

(NOTE:You can use DEVIL- and DEATH+ together.
 And If you use HEBORIS rotation, you can train T.A DEATH.)

ROT.RELAY
 Select SIMPLE mode (40LINES or ULTRA2min) and press Hold botton once.
 Play 40LINES or ULTRA2min with ALL rotation rules.
 Top-out does not become gameover,but penalty will be added.

----------------------------------------------------
3. Add-ons
----------------------------------------------------

See the res folder and the corresponding .txt files in the subdirectories
for information regarding changing aspects of the game. You can alter the
graphics, bgm, sound effects, and backgrounds from there.

----------------------------------------------------
4. Heboris.ini
----------------------------------------------------

See this file for possible changes made to the game that may not be able
to be changed in the in-game menu. Here is where some

---------------------------------------------------
5. License
---------------------------------------------------

(c) 1998-2002 Kenji Hoshimoto
```
