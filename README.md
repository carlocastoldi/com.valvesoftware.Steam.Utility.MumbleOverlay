# com.valvesoftware.Steam.Utility.MumbleOverlay
Installs `libmumbleoverlay.so` in `/app/utils/MumbleOverlay/lib/i386-linux-gnu/` (for 32bit games) and `/app/utils/MumbleOverlay/lib/x86_64-linux-gnu/` (for 64bit games).

## Usage
A game, in order to display the overlay, needs to be launched with the library preloaded. The game's launch options should thus be set to: `LD_PRELOAD=/app/utils/MumbleOverlay/\$LIB/mumble/libmumbleoverlay.so %command%`.

`LD_PRELOAD=/app/utils/MumbleOverlay/\$LIB/libmumbleoverlay.so:/usr/\$LIB/libGL.so.1 %command%` if the game is not linked against OpenGL library.

## Related pull requests
This extension is not officially published, yet. The following PRs still need to be discussed & merged:
* move Mumble Socket and Overlay to `$XDG_RUNTIME_DIR/mumble/`: https://github.com/mumble-voip/mumble/pull/5961
* build overlay on Linux and FreeBSD without client flag: https://github.com/mumble-voip/mumble/pull/5967
* add Mumble overlay support: https://github.com/flathub/com.valvesoftware.Steam/pull/1008
