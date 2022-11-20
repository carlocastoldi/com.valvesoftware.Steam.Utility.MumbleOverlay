# com.valvesoftware.Steam.Utility.MumbleOverlay
installs `libmumbleoverlay.so` in `/app/utils/MumbleOverlay/lib32/` (for 32bit games) and `/app/utils/MumbleOverlay/lib/` (for 64bit games).

A game, in order to display the overlay, needs to be launched with the library preloaded. For example, launch options could be something like: `LD_PRELOAD=/app/utils/MumbleOverlay/lib32/libmumbleoverlay.so  %command%`.

Some steam games are not linked against OpenGL library. In that case you may need to copy `libGL.so` in flatpak'ed Steam directory and `LD_PRELOAD` it as well: e.g. `LD_PRELOAD=/app/utils/MumbleOverlay/lib32/libmumbleoverlay.so:/home/carlo/data/Steam/linux32/mumble/libGL.so  %command%`. An extension may be developed in the future.

## Related pull requests
This extension is not officially published, yet. The following PRs still need to be discussed & merged:
* move Mumble Socket and Overlay to `$XDG_RUNTIME_DIR/mumble/`: https://github.com/mumble-voip/mumble/pull/5961
* build overlay on Linux and FreeBSD without client flag: https://github.com/mumble-voip/mumble/pull/5967
* add Mumble overlay support: https://github.com/flathub/com.valvesoftware.Steam/pull/1008
