# AzaharVR

**AzaharVR is an unofficial merge of two projects:**

- [**CitraVR**](https://github.com/amwatson/CitraVR) by [amwatson](https://github.com/amwatson) and contributors: the Quest-native OpenXR frontend that lets you play 3DS games in VR (screens as VR layers, stereoscopic rendering, controller input, the VR menus).
- [**Azahar**](https://github.com/azahar-emu/azahar) by the Azahar team and contributors: the actively maintained 3DS emulator that continues Citra, used here as the emulator core.

CitraVR was last synced to Azahar around July 2026. This repository carries CitraVR forward onto **Azahar 2126.2** (tag of 2026-10-08), roughly 130 emulator commits newer, so VR users get Azahar's compatibility and accuracy fixes. It also includes VR quick save / quick load and faster save states (proposed to CitraVR as [amwatson/CitraVR#115](https://github.com/amwatson/CitraVR/pull/115)).

> **Status: experimental.** It builds (`./gradlew assembleRelease` in `src/android`) and its unit tests pass, but headset testing is still in progress. Expect rough edges.

## Things to know

- **Save states:** since Azahar 2126.1, save states are tied to the Azahar build version. States saved with older CitraVR builds will not load here. In-game saves (the 3DS memory card) are not affected.
- **Quest only:** the VR layer targets Meta Quest 2, Pro, 3 and 3S, like CitraVR. The release APK is signed with the Android debug key.
- **Upstream sync:** the merge was done by hand on top of Azahar's `2126.2` tag. CitraVR's VR code, per-game settings UI and build/version handling are kept, and Azahar's side is taken for everything else.
- **Support:** this is not CitraVR or Azahar. Please do not ask their teams or communities for help with this fork; open an [issue here](https://github.com/zehuali/AzaharVR/issues) instead.
- **AI policy:** parts of the merge and adaptation were done with AI assistance (Claude Code). Azahar's AI policy does not allow AI-written contributions, so nothing from this fork should be submitted to Azahar.

## Credits

All credit for the work in this repository belongs to the original authors. This fork only merges and adapts their work.

- **CitraVR**: [amwatson](https://github.com/amwatson) and the CitraVR contributors, who created the Quest port, the OpenXR layer and the VR user interface.
- **Azahar**: [PabloMK7](https://github.com/PabloMK7) and the [Azahar contributors](https://github.com/azahar-emu/azahar/graphs/contributors).
- **Citra** and **Lime3DS**: the Citra Emulator Project, [Lime3DS](https://github.com/Lime3DS/lime3ds-archive) and everyone who contributed to them. Azahar and CitraVR are built on their foundation.
- All the third-party libraries under `externals/` keep their own licenses and authors.

## License

This repository is a combination of CitraVR and Azahar and keeps their licenses. See [license.txt](license.txt) and the license header in each source file (Azahar's 2126.x code is "GPLv2 or any later version"). Any copyright notices of the original authors are left as they were.

---

# Original CitraVR README

The text below is CitraVR's README, unchanged. Its links point to the original CitraVR project, not to this fork.

<h1 align="center">
  <br>
  <a href="https://github.com/amwatson/CitraVR"><img src="assets/citravr_logo.png" alt="CitraVR" width="500"></a> (Beta)
</h1>

<h4 align="center"> Play 3DS homebrew and personal game backups in 3D on the go with your Quest.
</br>
  CitraVR is a GPL-licensed, engineless OpenXR application with all source code publicly available.
</h4>

<p align="center">
  <a href="#compatabillty">Compatibillty</a> |
  <a href="#releases">Releases</a> |
  <a href="#known-issues">Known Issues</a> |
  <a href="#how-to-install-and-run">How to Install and Run</a> |
  <a href="#building">Building</a> |
  <a href="#discord">Discord</a> |
  <a href="#need-help">Need Help?</a> |
  <a href="#support">Support</a> |
  <a href="#license">License</a>
</p>

## Introduction
I originally created this project to a be a proof-of-concept of some techniques XR developers were curious about. 
Specifically:
- Building a 2D/3D hybrid app
- Creating a VR app to render 2D interactive windows without an engine
- Using VR layers to get sharp, crisp text and visuals.

CitraVR began as a Quest-native (i.e. OpenXR, without a third-party game engine) port of the [Citra 3DS emulator](https://github.com/citra-emu/citra). It seemed like a great and fun way to demonstrate all these things at once.

The original Citra project is now defunct. [Azahar](https://github.com/azahar-emu/azahar) was built on Citra's foundation and continues its development. CitraVR has since incorporated the changes from Azahar and now uses Azahar as its upstream emulator project.

The project is still small, but I'm looking for ways to improve it as time goes on.

## Features
- Stereoscopic rendering
- Broad controller support
- Large, moveable/resizeable screen
- Playable in mixed reality
- Low-overhead port
- Fully GPL-licensed, 100% independent of the Meta SDK

## Compatibillty

### HMDs
CitraVR supports the following devices:
- Meta Quest 2
- Meta Quest Pro
- Meta Quest 3
- Meta Quest 3S

### Games
For a full list of games that work well on CitraVR, please visit the [CitraVR Game Compatability List](https://docs.google.com/spreadsheets/d/1viN8_MWO1HW9QXlkT-TdCGQbH1g660mKsIp1ZTARdho/edit?usp=sharing)

### Controllers/Input 
[Touch Controller Input Bindings Diagram](https://github.com/amwatson/CitraVR/wiki/Touch-Controller-Input-Bindings)

For games that need access to more inputs, or if a player needs to access more inputs faster, CitraVR also supports a multitude of 3rd party wired USB and wireless bluetooth controllers. 

## Releases
Grab the latest release [here](https://github.com/amwatson/CitraVR/releases)

## Known Issues
See the [CitraVR Known Issues](https://github.com/amwatson/CitraVR/wiki/CitraVR-Known-Issues)

## How to Install and Run
- [How to install and run CitraVR on Quest](https://github.com/amwatson/CitraVR/wiki/Install-Run-on-Quest)
- [How to back up 3DS Games](https://github.com/amwatson/CitraVR/wiki/Backing-up-3DS-Games)

## Building
[Building for Quest](https://github.com/amwatson/CitraVR/wiki/Building-for-Quest)

## Discord 
Join the [Flat2VR](https://flat2vr.com/) discord and from there join [cvr-join](https://discord.com/channels/747967102895390741/1196505250102792232) to get access to the CitraVR community and support forums

# Need Help?
Please check our [Troubleshooting](https://github.com/amwatson/CitraVR/wiki/Troubleshooting) and [Known Issues](https://github.com/amwatson/CitraVR/wiki/CitraVR-Known-Issues) pages to see if your issue is listed.
To file a bug report or a feature request, please [submit an issue](https://github.com/amwatson/CitraVR/issues/new/choose).
Otherwise, follow the instructions for <a href="#discord">Discord</a> and post in [cvr-support](https://discord.com/channels/747967102895390741/1196505719910957176)

## Support
[Buy me a beer](https://www.buymeacoffee.com/fewerwrong)

## License
CitraVR is licensed under the GPLv3 (or any later version). Refer to the [LICENSE.txt](https://github.com/amwatson/CitraVR/blob/master/license.txt) file.
