# Arduino ISP

## Description

Simple device to remplace ISP programmer with an Teensy 2++. With this simple device you'll be able to program devices with ISP. This simple device will replace an USBasp device and make possible to

* backup microntrollers
* restore backups
* burning the bootloader on 

In this code the HB (heart beat) PIN is mapped to PIN 6 (on board Teensy LED). This way once the ArduinoISP program is loaded to the Teensy, it should blink slowly and contuniously.


## Schematic to work with an ATMega328p

Here is an example of how to wire an ATMega328p programmer. Once wired you'll be able to program the device. With this simple device you can load the Arduino Bootloader.

![Teensy2 Arduino ISP](https://raw.githubusercontent.com/Akrobate/ArduinoISP/master/assets/isp-electronic-schema.png)


## Customizations

You can add some LED to visualize the activity of the programmer:

* LED_PMODE
* LED_ERR
* RESET

In this example the **RESET** PIN was plugged on the **PIN 20**. You can change it to any other PIN.

## PlatformIO

The project can be build on PlatformIO.

`platformio.ini`

```ini
[env:teensy2pp]
platform = teensy
board = teensy2pp
framework = arduino
upload_protocol = teensy-cli
```

## Usage

Example of procedure to burn bootloader on a ATMega328p

### Building the Teensy ISP adapter

* Build the project with platformio
* upload to the teensy with platformio

### Arduino IDE for burning bootload

* Open Arduino IDE (exemple: Version: 2.3.3 on Ubuntu 22)
* For the ATMega328P select board: `Arduino Duemilanove or Diecimila` (Tools > Boards > Board Manager)
* Select the serial port, for the Teensy2++ should `/dev/ttyACM0`
* Select the porgrammer `Arduino as ISP`
* Tools > Burn Bootloader

## Important

* MISO pin of Teensy is plugged to MISO pin of the 328P
* MOSI pin of Teensy is plugged to MOSI pin of the 328P
* If you have `avrdude: Device signature = 0x000000 avrdude: Expected signature for ATMEGA328P is 1E 95 0F` Error
    * Check all the pins
    * the ATMega328 must be powered
    * the Crystal of 16Mhz must be plugged
* Burning isn't instant take a little while
* is success you should see a success toast in the Arduino IDE






