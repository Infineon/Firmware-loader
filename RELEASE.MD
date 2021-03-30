### fw-loader v3.2.0 Release Notes

Please refer to the README.md for a complete description of the fw-loader.

### New Features

- Delivers KitProg3 v2.21.1005 firmware with:
    1. Adds GPIO Bridging which implements direct single wire communication with target device via direct control of dedicated GPIO 3[5], 3[6] pins. It allows to set the state or drive modes of those pins via USB commands or read the pin state. This feature is supported on CY8CKIT-062S2-43012 , CYW9P62S1-43438EVB-01 , CYW9P62S1-43012EVB-01, CY8CKIT-064B0S2-4343W  and CY8CKIT-064S0S2-4343W  kits
    2. Adds new kits support for PMG1 product line
    3. Adds PSoC 4100S Max Pioneer Kit (CY8CKIT-041S-Max) and PSoC® 4500S Pioneer Kit (CY8CKIT-045S) kits support   
- Bugs fixing

### Known Issues

| ID                                | Known Issue                       | Workaround                          |
|-----------------------------------|-----------------------------------|-----------------------------------|
|  PROGTOOLS-768 | KitProg3 firmware might not be updated properly on a particular USB port on some Lenovo ThinkPad Pro Docking Station.  |  If you encounter this problem: 1. switch to a different USB port on the docking station OR 2. Update KitProg3 firmware in Bootloader mode (press the mode switch while plugging in the board). |
|  PROGTOOLS-1488 | Junk characters might be observed in a UART terminal during programming of the connected kit or after programming is competed. | Clear UART buffers after kit programming is completed.   |
|  PROGTOOLS-1838 | Starting from KitProg3 v2.10, when KitProg3 is in CMSIS-DAP Bulk mode, it is not possible to debug and use USB-I2C/SPI bridging (for example, in the CapSense Tuner, Bridge Control Panel) at the same time. This affects Windows OS only. It does not affect Linux or macOS users. | If you would like to use debug and USB-I2C/SPI bridging at the same time, there are two possible workarounds: 1. If performance for programming and debug is not critical,switch KitProg3 to CMSIS-DAP. 2. If you need faster performance for programming and debug, use the onboard KitProg3 for programming purposes and MiniProg4 for bridging purposes or vice versa. Both devices can be in CMSIS-DAP bulk mode. Details are in KBA231025.|
|  PROGTOOLS-1869 | In Linux OS, with KitProg3 in CMSIS-DAP HID mode, a debug session in ModusToolbox can be destroyed if you use the Firmware Loader --device-list command while debugging. This is limitation of hidapi library used on Linux. MacOS and Windows OSs are not impacted. | If you have a debug session running, don't use the firmware loader tool.  |
|  PROGTOOLS-1814 | Starting from KitProg3 v2.10, in some cases Windows 7 does not recognize the KitProg3 bridge. So the USB- I2C/SPI bridge devices are not available in either CMSIS-DAP HID or CMSIS-DAP bulk mode. | Install a digitally signed driver manually from the Windows Update Catalog. Follow steps from KBA231026.   |



### More information

-   [fw-loader README.md](https://github.com/cypresssemiconductorco/Firmware-loader/blob/master/README.md)

-   [Kitprog3 User Guide](https://www.cypress.com/documentation/development-kitsboards/kitprog-user-guide)

-   [KitProg Host Protocol Interface](https://www.cypress.com/file/520056/download)

-   [ModusToolbox Software Environment, Quick Start Guide, Documentation, and Videos](https://www.cypress.com/products/modustoolbox-software-environment)

-   [ModusToolbox Device Configurator Tool Guide](https://www.cypress.com/ModusToolboxDeviceConfig)

-   [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)

© Cypress Semiconductor Corporation, 2019-2021.
