# Potato65 Hotswap Firmware Guide  

## Flashing the Firmware

Note: The Potato65 Hotswap and Solderable keyboards come preflashed out of the box. Follow these instructions to reflash the keyboard if needed.

* The simplest way to flash your keyboard will be with the [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases). The QMK Toolbox is currently only available for Windows and macOS. If you're using Linux please follow the instructions given [here](https://beta.docs.qmk.fm/tutorial/newbs_flashing#flash-your-keyboard-from-the-command-line).

* Connect the PCB to the computer.

* Open the QMK Toolbox application.

* ![QMK Toolbox](/images/qmktoolbox.jpg "QMK Toolbox")

* Make sure that the .hex file is selected in the Local file selector. Make sure that the Microcontroller dropdown is set to atmega32u4. Check the checkbox labelled Auto-Flash.

* Now press the reset button on the back of the pcb.

You will see output similar to the following:
```*** DFU device connected: Atmel Corp. ATmega32U4 (03EB:2FF4:0000)
*** Attempting to flash, please don't remove device
>>> dfu-programmer.exe atmega32u4 erase --force
    Erasing flash...  Success
    Checking memory from 0x0 to 0x6FFF...  Empty.
>>> dfu-programmer.exe atmega32u4 flash "D:\Desktop\buildakb_potato65hs_via.hex"
    Checking memory from 0x0 to 0x3F7F...  Empty.
    0%                            100%  Programming 0x3F80 bytes...
    [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
    0%                            100%  Reading 0x7000 bytes...
    [>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>]  Success
    Validating...  Success
    0x3F80 bytes written into 0x7000 bytes memory (56.70%).
>>> dfu-programmer.exe atmega32u4 reset

*** DFU device disconnected: Atmel Corp: ATmega32U4 (03EB:2FF4:0000)
```

## Remapping keys using VIA

* Download VIA from [here](https://www.github.com/the-via/releases/releases/latest) and install it.

* Launch VIA. VIA will automatically detect the keyboard and show the current layout and keymap of the keyboard.

![VIA](/images/via.jpg "QMK Toolbox")

* On the top half, select the key you want to configure on your layout. Select the key you want to assign it as from the bottom.

* Test your configuration by switching to the Key Tester tab in VIA. On the keyboard, tap the key that you just programmed. In the Key Tester, the corresponding key should light up, showing that your keypress corresponds to the correct key.
