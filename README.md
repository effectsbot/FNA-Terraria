# FNA-Terraria
This repository contains up to date builds of [FNA](https://github.com/FNA-XNA/FNA) for use with Terraria on Linux.

## Features
- Support for D3D11 renderer via DXVK (replaces the older FNA3D Vulkan renderer)
- Support for Wayland HiDPI scaling thanks to sdl2-compat
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
- Add `SDL_VIDEODRIVER=wayland` before `%command%` to enable native Wayland support (scale factor is automatically detected)
- Add `SDL_AUDIODRIVER=pipewire` before `%command%` to enable native PipeWire audio

## How do I revert everything back to default?
Remove the `lib64` folder inside of the game's directory, then verify the integrity of the game's files from its properties and remove all of the launch options.
