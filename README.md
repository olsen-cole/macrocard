# Macrocard
The macrocard is a wireless business card-shaped macropad featuring three switches, a rotary encoder, and RGB LED feedback. This macropad is designed for productivity workflows, media control, and presentation control. Current firmware for this card is only supported on Windows.

![20250730_122539](https://github.com/user-attachments/assets/0aa66051-cd45-4799-a0f4-dba6fc29a4c9)
![20250730_124026](https://github.com/user-attachments/assets/38ae322f-fac5-4339-8261-aac5f4975584)


# Keymap
This macropad has three main layers: productivity, music, and presentation.

## Productivity
Pressing keys one and two will place the macropad into productivity mode. This layer is composed of three sub-layers: window switcher, virtual desktop switcher, and tab switcher.

### Window Switcher (Cyan)
Window switcher is the sub layer that is activated by default when entering the productivity layer. This layer can be activated by pressing the first key while in the productivity layer.

#### Function: 
Rotating the knob will switch between active windows. Press the knob to select a window.

### Virtual Desktop Switcher (Yellow)
This layer can be activated by pressing the second key while in the productivity layer.

#### Function: 
Rotating the knob will switch between virtual desktops.

### Tab Switcher (Magenta)
This sub-layer can be activated by pressing the third key while in the productivity layer.

#### Function: 
Rotating the knob will switch between active tabs on supported applications. Press the knob to select a tab.

## Music (Green)
Pressing keys two and three will place the macropad into music mode.

#### Function: 
Rotating the knob will adjust volume. Pressing the knob will mute/unmute audio. The three keys control previous track, play/pause, and forward track.

## Presentation (Red)
Pressing keys one and three will place the macropad into presentation remote mode.

#### Function: 
Rotating the knob will navigate slides. Pressing the knob wil activate presenter view. The three keys will start presentation, exit presentation, and toggle blank screen.

> [!NOTE] 
> On any layer, pressing and holding the encoder switch will disconnect from the current connected device.

# Usage
ZMK has decent battery optimization. The macropad will be placed into a sleep mode when inactive for an hour. If the macropad will be stored for a week or more, turn the macropad off using the on/off switch to disconnect the battery.

> [!NOTE] 
> Since the on/off switch will disconnect the battery, charging the battery is not possible when the macropad is off.

# Battery
In order to update or re-flash firmware, connect the macropad to a computer through USB and press all three keys and the encoder switch to enter bootloader mode. If the macropad will not enter bootloader mode through the shortcut, the bootloader mode can be manually activated by shorting the RST pin to the ground pin above it. The macropad should now show as a drive. Simply copy and paste the uf2 file to apply the update.

## Troubleshooting
If any issues are encountered during or after the update process, performing a settings reset may resolve issues. To do this, first disassemble the macropad. Place the macropad into bootloader mode manually and apply the settings-reset uf2 file. Then place the macropad into bootloader mode manually and apply the update file. 
