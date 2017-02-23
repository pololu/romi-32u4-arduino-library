# Romi32U4 library

Version: 1.0.1<br/>
Release date: 2017-02-23<br/>
[![Build Status](https://travis-ci.org/pololu/romi-32u4-arduino-library.svg?branch=master)](https://travis-ci.org/pololu/romi-32u4-arduino-library)<br/>
[www.pololu.com](https://www.pololu.com/)

## Summary

This is a C++ library for the Arduino IDE that helps access the on-board hardware of the [Romi 32U4 Control Board](https://www.pololu.com/product/3544).

The Romi 32U4 Control Board turns the Romi chassis into a programmable robot based on the Arduino-compatible ATmega32U4 MCU.  It has an integrated AVR ATmega32U4 microcontroller, motor drivers, encoders, buzzer, buttons, and an LSM6DS33 accelerometer and gyro.

This library does not include code for accessing the LSM6DS33.  If you want to access it, you should install the separate [LSM6 library](https://github.com/pololu/lsm6-arduino).

This library is very similar to the [Zumo32U4](https://github.com/pololu/zumo-32u4-arduino-library) library.

## Installing the library

If you are using version 1.6.2 or later of the [Arduino software (IDE)](http://www.arduino.cc/en/Main/Software), you can use the Library Manager to install this library:

1. In the Arduino IDE, open the "Sketch" menu, select "Include Library", then "Manage Libraries...".
2. Search for "Romi32U4".
3. Click the Romi32U4 entry in the list.
4. Click "Install".

If this does not work, you can manually install the library:

1. Download the [latest release archive from GitHub](https://github.com/pololu/romi-32u4-arduino-library) and decompress it.
2. Rename the folder "romi-32u4-arduino-library-master" to "Romi32U4".
3. Move the "Romi32U4" folder into the "libraries" directory inside your Arduino sketchbook directory.  You can view your sketchbook location by opening the "File" menu and selecting "Preferences" in the Arduino IDE.  If there is not already a "libraries" folder in that location, you should make the folder yourself.
4. After installing the library, restart the Arduino IDE.

## Examples

Several example sketches are available that show how to use the library.  You can access them from the Arduino IDE by opening the "File" menu, selecting "Examples", and then selecting "Romi32U4".  If you cannot find these examples, the library was probably installed incorrectly and you should retry the installation instructions above.

## Classes and functions

The main classes and functions provided by the library are listed below:

* Romi32U4ButtonA
* Romi32U4ButtonB
* Romi32U4ButtonC
* Romi32U4Buzzer
* Romi32U4Encoders
* Romi32U4LCD
* Romi32U4Motors
* ledRed()
* ledGreen()
* ledYellow()
* usbPowerPresent()
* readBatteryMillivolts()

## Component libraries

This library also includes copies of several other Arduino libraries inside it which are used to help implement the classes and functions above.

* [FastGPIO](https://github.com/pololu/fastgpio-arduino)
* [PololuBuzzer](https://github.com/pololu/pololu-buzzer-arduino)
* [PololuHD44780](https://github.com/pololu/pololu-hd44780-arduino)
* [Pushbutton](https://github.com/pololu/pushbutton-arduino)
* [QTRSensors](https://github.com/pololu/qtr-sensors-arduino)
* [USBPause](https://github.com/pololu/usb-pause-arduino)

You can use these libraries in your sketch automatically without any extra installation steps and without needing to add any extra `#include` lines to your sketch.

You should avoid adding extra `#include` lines such as `#include <Pushbutton.h>` because then the Arduino IDE might try to use the standalone Pushbutton library (if you previously installed it), and it would conflict with the copy of the Pushbutton code included in this library.  The only `#include` line needed to access all features of this library are:

~~~{.cpp}
#include <Romi32U4.h>
~~~

## Documentation

For complete documentation, see https://pololu.github.io/romi-32u4-arduino-library.  If you are already on that page, then click on the links in the "Classes and functions" section above.

## Version history

* 1.0.1 (2017-02-23):
  * Changed the internal `Romi32U4Motors::maxSpeed` variable to be an `int16_t` so it can be compared to other `int16_t` variables without warnings.
  * Fixed the InterialSensors and Demo examples to not use a compass.
  * Fixed some comments.
* 1.0.0 (2017-02-06): Original release.
