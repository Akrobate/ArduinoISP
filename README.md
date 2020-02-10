# Arduino ISP

## Description

Simple device to remplace ISP programmer with an Teensy 2++. With this simple device you'll be able to program devices with ISP. This simple device will replace an usbasp device and make possible to

* backup microntrollers
* restore backups
* burning the bootloader on 

In this code the HB (heart beat) PIN is mapped to PIN 6 (on board Teensy LED). This way once the ArduinoISP program is loaded to the teensy, it should blink slowly and contuniously.


## Schematic to work with an ATMega328p

Here is an example of how to wire an ATMega328p programmer. Once wired you'll be able to program the device. With this simple device you can load the Arduino Bootloader.

![Teensy2 Arduino ISP](https://raw.githubusercontent.com/Akrobate/ArduinoISP/master/assets/isp-electronic-schema.png)


## Customizations

You can add some LED to visualize the activity of the programmer:

* LED_PMODE
* LED_ERR
* RESET

In this example the RESET PIN was plugged on the PIN 20. You can change it to any other PIN.
