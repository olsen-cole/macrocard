# Design Process
Inspired by the numerous over-engineered business cards that I've seen on [Hackaday](https://hackaday.com/tag/business-card), I wanted to design a card useful enough to stick around the office. Combining my love of DIY input devices with a bit of CAD experience, I decided to design a business card-shaped macropad.

## Initial Design Choices
Design choices were made primarily due to cost, ease of manufacturing, and simplicity.

- The nice!nano microcontroller was selected over an integrated SoC or a microcontroller with castellated pads due to cost and ease of assembly.

- A low profile ec11 encoder was selected over a slimmer mouse wheel encoder due to the direct support within ZMK.

## Board Design

I first designed a PCB with flux.ai. The circuit required for this project was simple enough to require only two layers due to the small amount of I/O. 

![PCB](https://github.com/olsen-cole/macrocard/blob/main/assets/PCB.jpg)

Although it is possible to surface mount a board with female through-hole connections, I opted for right angle headers to surface mount the nice!nano.

![nice!nano](https://github.com/olsen-cole/macrocard/blob/main/assets/nice!nano.jpg)

The other notable components used for this project were a simple four leg RGB LED, mouse microswitches, a 10mm plum shaft encoder, and a 602020 LiPo battery. Finally, a low profile switch was added to disconnect the battery during storage.

![PCB with components](https://github.com/olsen-cole/macrocard/blob/main/assets/pcb_with_components.jpg)

## Firmware Design

Before ordering PCBs, I started working on the firmware to confirm that the circuit would work. The two big keyboard firmware projects with support for the NRF52840 are ZMK and BlueMicro. Initially, I began development with BlueMicro as it could remember the last active layer on powerup. However, I required ZMK for a more complex layer system.

ZMK development took some time. I first started working on the layers, of which I was able to create three "modes" out of layers which could be accessed by pressing a combination of two out of the three keys. 

Once the layers were functional, I began implementing the [zmk-smart-toggle behavior](https://github.com/caksoylar/zmk-smart-toggle?tab=readme-ov-file) to enable the window/tab switcher. This allowed for a sleek implementation of the alt-tab shortcut on a rotary encoder. Finally, I implemented the [zmk-rgbled-widget](https://github.com/olsen-cole/zmk-rgbled-widget) to give feedback on the active layer, bluetooth connectivity, and battery status.  

After compiling a working firmware, I began implementing a forked version of the RGB LED widget as I was not satisfied with the lack of PWM brightness control. I accomplished this by implementing the PWM functionality provided by zephyr, the project that zmk is built on.

## Shell Design

Once the firmware was completed, I ordered the PCBs and began working on a shell. I decided to implement bending tops for the keyswitches. After some testing, I found a thickness of 0.4mm allowed for a somewhat durable hinge without adding too much resistance to the keypress.

My first prototypes of the shell included a two part extension of the switch. After testing, I found that I could print the extension in place.

![switch](https://github.com/olsen-cole/macrocard/blob/main/assets/switch.jpg)

The final component of the shell is the encoder knob. I wanted a large knob that hovered over the top of the macropad. However, as the shell would need to lift up from the macropad to disassemble, I needed a way to remove the knob. I decided to cut the knob into a top and a base, joined with a magnet. To prevent tolerance issues, I added a taper in the connection.

![knob base](https://github.com/olsen-cole/macrocard/blob/main/assets/knob_base.jpg)

## Future Work

My first regret with this project is the shell. Most over-engineered business card projects are simply the PCB itself, no shell. However, I did need some way to display skills more relevant to mechanical engineering. It did also give me experience designing flexible and print-in-place components.

My second regret was using flux.ai. Although it is perfect for quickly designing boards, it lacked many advanced features. It also lacked a schematic export. In the future, I'll stick to KiCad.

For version two of this project, I will select components to keep the lowest profile possible.

* Onboard Controller
    * NRF52840 QFAA
    * Charging and regulator circuits similar to nice!nano
* LIR2032 LiPo battery
    * Build battery protection into board
    * SMD Coin cell clip, <8mm height
* Horizontal mouse scroll wheel as rotary encoder
    * Low profile (<2.8mm)
    * Custom ZMK configuration as the EC11 is the only supported encoder
* Kailh PG1316 Switches
    * Low profile (<5mm with keycap)