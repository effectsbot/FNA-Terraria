# FNA-Terraria
This repository contains up to date builds of [FNA](https://github.com/FNA-XNA/FNA) for use with Terraria on Linux.

## Noteworthy but non-exclusive features
- Support for D3D11 renderer via DXVK Native
- Support for Wayland HiDPI scaling
- Native support for PipeWire audio

## How do I use this?
Download the tarball from the latest release, extract it, then move the extracted files into their respective directory:
```
FNA.dll and FNA.dll.config --> $HOME/.local/share/Steam/steamapps/common/Terraria
Everything in lib64 --> $HOME/.local/share/Steam/steamapps/common/Terraria/lib64
```

If you're using the Flatpak version of Steam, move them into these directories instead:
```
FNA.dll and FNA.dll.config --> $HOME/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common/Terraria
Everything in lib64 --> $HOME/.var/app/com.valvesoftware.Steam/data/Steam/steamapps/common/Terraria/lib64
```

## How do I use any of the mentioned features?
The features mentioned above require adding launch options to Terraria's properties inside of Steam. Add `%command%` to the launch options before following the instructions below.

- Add `/gldevice:D3D11` after `%command%` to enable the D3D11 renderer
- Add `SDL_VIDEO_WAYLAND_SCALE_TO_DISPLAY=1` before `%command%` to enable HiDPI scaling on Wayland (requires `SDL_VIDEO_DRIVER=wayland` to be set)
- Add `SDL_AUDIO_DRIVER=pipewire` before `%command%` to enable native PipeWire audio

## How do I revert everything back to default?
Remove the `lib64` folder inside of the game's directory, then verify the integrity of the game's files from its properties and remove all of the launch options.
