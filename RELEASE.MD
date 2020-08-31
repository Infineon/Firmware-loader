### fw-loader v3.1.0 Release Notes

Please refer to the README.md for a complete description of the fw-loader.

### New Features

- Delivers KitProg3 v2.10.878 firmware with:
    1. Support an enhanced USB-I2C/SPI bridging implemented on bulk endpoints what speeds-up USB communication. Refer 'Known Issues' section below to get details about issues related to it with possible workarounds.  
- Bugs fixing

### Known Issues

| ID                                | Known Issue                       | Workaround                          |
|-----------------------------------|-----------------------------------|-----------------------------------|
|  PROGTOOLS-768 | KitProg3 firmware might not be updated properly on a particular USB port on some Lenovo ThinkPad Pro Docking Station.  |  If you encounter this problem: 1. switch to a different USB port on the docking station OR 2. Update KitProg3 firmware in Bootloader mode (press the mode switch while plugging in the board). |
|  PROGTOOLS-1488 | Junk characters might be observed in a UART terminal during programming of the connected kit or after programming is competed. | Clear UART buffers after kit programming is completed.   |
|  PROGTOOLS-1838 | Starting from KitProg3 v2.10, when KitProg3 is in CMSIS-DAP Bulk mode, it is not possible to debug and use USB-I2C/SPI bridging (for example, in the CapSense Tuner, Bridge Control Panel) at the same time. This affects Windows OS only. It does not affect Linux or macOS users. | If you would like to use debug and USB-I2C/SPI bridging at the same time, there are two possible workarounds: 1. If performance for programming and debug is not critical,switch KitProg3 to CMSIS-DAP. 2. If you need faster performance for programming and debug, use the onboard KitProg3 for programming purposes and MiniProg4 for bridging purposes or vice versa. Both devices can be in CMSIS-DAP bulk mode. Details are in KBA231025.|
|  PROGTOOLS-1869 | In Linux OS, with KitProg3 in CMSIS-DAP HID mode, a debug session in ModusToolbox can be destroyed if you use the Firmware Loader --device-list command while debugging. This is limitation of hidapi library used on Linux. MacOS and Windows OSs are not impacted. | If you have a debug session running, don't use the firmware loader tool.  |
|  PROGTOOLS-1814 | Starting from KitProg3 v2.10, in some cases Windows 7 does not recognize the KitProg3 bridge. So the USB- I2C/SPI bridge devices are not available in either CMSIS-DAP HID or CMSIS-DAP bulk mode. | Install a digitally signed driver manually from the Windows Update Catalog. Follow steps from KBA231026.   |
|  PROGTOOLS-1925 | On macOS, UART communication can fail in the CapSense Tuner with a baud rate over 115200. This occurs because the maximum baud rate supported in macOS is 230400 (defined in the termios.h system file), and next baud rate after 115200 in the CapSense Tuner is 250000. So, baud rates from 250000 to 4000000 cannot be used on macOS. | On macOS, use a baud rate of 115200 for the CapSense Tuner.   |


### More information

-   [fw-loader
    README.md](https://github.com/cypresssemiconductorco/Firmware-loader/blob/master/README.md)

-   [Kitprog3 User
    Guide](https://www.cypress.com/documentation/development-kitsboards/kitprog-user-guide)

-   [ModusToolbox Software Environment, Quick Start Guide, Documentation, and
    Videos](https://www.cypress.com/products/modustoolbox-software-environment)

-   [ModusToolbox Device Configurator Tool
    Guide](https://www.cypress.com/ModusToolboxDeviceConfig)

-   [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)

© Cypress Semiconductor Corporation, 2019-2020.
