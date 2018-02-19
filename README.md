# USB to Floppy-Disk Drive Adapter

This project provides the CAD files for an STM32-based floppy-disk controller that can be attached to the back of an ordinary 3.5 inch floppy-disk drive and connected to a USB host via micro USB port.

## Configuration

The adapter can be used in several different hardware configurations that can be selected via solder bridges.

The following drive types are supported:

- PC drives
- IBM PS/2 drives
- drives with shugart interface

Drives that only use the 5V line and consume less than approx. 480mA can be powered via USB, other drives have to be powered externally.

J5    | J6    | J7       | Use case
------|-------|----------|---------
▒▒░▒▒ | ▒▒░▒▒ | ▒▒░▒▒░▒▒ | PC drive, externally powered
▓▓▓▓▓ | ▒▒░▒▒ | ▒▒░▒▒░▒▒ | IBM PS/2 drive without 12V line
▒▒░▒▒ | ▓▓▓▓▓ | ▒▒░▒▒░▒▒ | PC drive, USB-powered
▒▒░▒▒ | ▒▒░▒▒ | ▓▓▓▓▓░▒▒ | pin 4 and 6 shorted, for shugart drives that do not use pin 4
▒▒░▒▒ | ▒▒░▒▒ | ▒▒░▓▓▓▓▓ | 12V on pin 4, for PS/2 drive

The power connector J3 can be used as either input or output.

## Programming via Serial Wire Debug Interface

Pin on J4 | Function
----------|---------
1 | 3.3V
2 | SWDIO
3 | SWCLK
4 | GND
