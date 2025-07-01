# General Information

Read this to make sure to use Gen7 Engine correctly and without issues.

### Input Controls

On Desktop platforms (Windows/Linux), use the keyboard for input, eg. WASD keys for directionnal controls plus POML keys for additional buttons (corresponds to XYAB).

### 2D Space

Leap uses a right-hand rule, with the X axis on the horizontal axis, and Y on the vertical axis. It starts with (X:0, Y:0) at the bottom left to (X: 640px, Y: 480px) at the top right, and all objects origin are at the bottom left of the sprite. The ratio is universal (4:3), but Gen7 adapts automatically your scene for 16:9 displays.

### Test your homebrew on real hardware, not on emulators

It's recommended to test your homebrew on real hardware, as emulators tends to not reproduce the real behavior, add issues that don't exist otherwise. Plus most emulators are designed to emulate games by optimizing performance while sacrifying accuracy.
The best practice would be to test on emulators when it already works well on, then check on real hardware if you notice a new issue on your project that doesn't seem to come from you to make sure it doesn't just come from the emulator.

### If testing on emulators, pay attention to its configuration

For best results when testing on emulators, check the best configuration available to test homebrew as many offers settings on emulation accuracy etc. Also, several emulators such as Dolphin for Wii or Switch emus rely on virtual SD cards that may not be able to be manipulated inside of it. Gen7 Engine assume to read from the standard storage device for homebrew that are mostly SD cards, so you have to make sure to have your project release files on it to be executed correctly.
On Dolphin for example, you can use WinImage to manipulate the virtual SD card and update its files.

### Caution Python indentation

If you use directly Python scripting, caution your indentation settings and typing since Python is pretty nitpicky about it, and so Gen7 will not be able to run anything if it can't parse the script file because of indentation issues such as consistency.

### Mind performance gaps between platforms

One reason of your project not running on your target platform is the usage of too performance consuming assets that cannot be rendered by the host. A game running on PC can easily handle high resolution images, when the Wii or PSP that are more than 15 years old absolutely cannot. It's important to keep that in mind when developing the project, as it's better to start with lower quality assets, and then improve them by continuously testing until performance isn't anymore adequate.
For reference, the Wii platform can't handle textures of more than 512x512px, PSP is adapted to 256x256px textures, and models shouldn't be too detailed (2MB OBJ file is recommended, 10k triangles for both platforms). Of course these are just numbers concluded from several tests but you can try more detailed as long as it can be handled in the host's memory and CPUs/GPUs.

### Report issues!

It's very important to report issues to spot and fix them quickly, and improve Gen7 Engine for everyone. Please use the dedicated Github repository: https://github.com/iyenal/Gen7EngineBugReporting/issues
