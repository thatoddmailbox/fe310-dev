# fe310-dev

![An image of the board](fe310-dev.jpg)

A development board for the SiFive [FE310 chip](https://www.sifive.com/chip-designer#fe310), a RISC-V microcontroller. Compatible with both the FE310-G000 and FE310-G002.

## Revisions
* Revision 0 - initial revision
* Revision 1 - added support for the G002, added mounting holes, fixed silkscreen labels for pins and LEDs

## Pinouts
The main pins are on the sides, and are labeled on the silkscreen. PWM capable pins are labeled with a ~, and pins with support for the SPI or UART peripherals have their functions labeled.

In the middle of the board, there are two sets of pins. The first is the JTAG header, which is partially labeled. When holding the board upright (so the "FE310 dev board" text can be read, and the USB port faces upwards), the pins are as follows:

* +3.3V
* TCK
* TDO
* TMS
* TDI
* GND

Most of these should go directly to the matching pin on your JTAG adapter. The one exception is +3.3V. If you want to power the board from your adapter, connect +3.3V to your adapter's power; however, if you want to power the board from USB (so that you can see the serial port), then leave the JTAG header's +3.3V pin disconnected.

The second set of pins has no labels. When holding the board upright, the pins are as follows:

* +1.8V
* AON_PMU_OUT_0
* AON_PMU_OUT_1
* AON_PMU_DWAKEUP_N
* AON_ERST_N
* AON_PSD_LFALTCLK
* AON_PSD_LFALTSEL
* GND

These are part of the Always-On (AON) Block of the FE310. You can check the FE310 manual for more information about these pins; however, in most cases, the only relevant pin is AON_ERST_N, which resets the chip (and is connected to the Reset button on the board).

## Known issues
See the [issue tracker](https://github.com/thatoddmailbox/fe310-dev/issues) for information about issues.