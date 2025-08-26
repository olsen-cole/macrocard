# <img width="1000" height="100" alt="bannerWhiteTransparent" src="https://github.com/olsen-cole/macrocard/blob/main/assets/banner_white_transparent.png" />

The ZMK config files for this project can be found [here](https://github.com/olsen-cole/zmk-config-macrocard).

The Macrocard is a wireless business card-shaped macropad featuring three switches, a rotary encoder, and RGB LED feedback. This macropad is designed for productivity workflows, media control, and presentation control.

> [!NOTE] 
> If you have received a Macrocard, the firmware will most likely be for Windows. To switch to Macintosh, see the firmware section.

![Front/Back](https://github.com/olsen-cole/macrocard/blob/main/assets/macrocard_front_back.jpg)
![Internal](https://github.com/olsen-cole/macrocard/blob/main/assets/macrocard_internal.jpg)

# Keymap
This macropad has three main layers: productivity, music, and presentation.

## Productivity
Pressing keys one and two will place the macropad into productivity mode. This layer is composed of three sub-layers: window switcher, virtual desktop switcher, and tab switcher.

### Window Switcher (Cyan)
Window switcher is the sub layer that is activated by default when entering the productivity layer. This layer can be activated by pressing the first key while in the productivity layer.

**Function:** Rotating the knob will switch between active windows. Press the knob to select a window.

### Virtual Desktop Switcher (Yellow)
This layer can be activated by pressing the second key while in the productivity layer.

**Function:** Rotating the knob will switch between virtual desktops.

### Tab Switcher (Magenta)
This sub-layer can be activated by pressing the third key while in the productivity layer.

**Function:** Rotating the knob will switch between active tabs on supported applications. Press the knob to select a tab.

## Music (Green)
Pressing keys two and three will place the macropad into music mode.

**Function:** Rotating the knob will adjust volume. Pressing the knob will mute/unmute audio. The three keys control previous track, play/pause, and forward track.

## Presentation (Red)
Pressing keys one and three will place the macropad into presentation remote mode.

**Function:** Rotating the knob will navigate slides. Pressing the knob wil activate presenter view. The three keys will start presentation, exit presentation, and toggle blank screen.

> [!NOTE] 
> On any layer, pressing and holding the encoder switch will disconnect from the current connected device.

# Usage
After three hours of inactivity, the macropad will enter an idle state to save energy. After six hours of inactivity, the macropad will enter a deep sleep mode. With these modes, the macropad can last a little under a month on a single charge. If you need to store the macropad, turn the macropad off using the on/off switch to disconnect the battery.

> [!NOTE] 
> Since the on/off switch will disconnect the battery, charging the battery is not possible when the macropad is off.

# Firmware
There are three firmware files—one for Windows, one for Macintosh, and one to reset. In order to update, re-flash, or change firmware, connect the macropad to a computer through USB and press all three keys and the encoder switch to enter bootloader mode. The macropad should now show as a drive. Simply copy and paste the uf2 file to apply the update.

> [!NOTE] 
> If the macropad will not enter bootloader mode through the shortcut, the bootloader mode can be manually activated by shorting the RST pin to the ground pin above it.

# Known Issues
- The macropad may fail to wake from deep sleep. Simply connect the macropad through USB and it should wake.
- The macropad will occasionally display a pink color on wake when it should be cyan. Switching the layer resolves the issue.

# Troubleshooting
If any issues are encountered during or after the update process, performing a settings reset may resolve issues. To do this, first disassemble the macropad. Place the macropad into bootloader mode manually and apply the settings_reset.uf2 file. Then place the macropad into bootloader mode manually and apply the update file. 