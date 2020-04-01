### fw-loader v2.3.0 Release Notes

Please refer to the README.md for a complete description of the fw-loader.

### New Features

- Delivers KitProg3 v1.20 firmware with the following:
    1. Improved performance over SWD in KitProg3 modes
    2. KitProg3 HID mode is no longer part of mode switching. The Mode Switch (SW3) button now switches between KitProg3 bulk and DAPLink modes. If you need to use KitProg3 HID mode, use the fw-loader command line to activate that mode.
    3. Add support of DAPlink mode for MiniProg4 probe. Note: mass storage functionality is not available in this case
    3. Bug fixes
- Bug fixes 

### Known Issues

| ID                                | Known Issue                       | Workaround                          |
|-----------------------------------|-----------------------------------|-----------------------------------|
|  PROGTOOLS-768 | KitProg3 firmware might not be updated properly on a particular USB port on some Lenovo ThinkPad Pro Docking Station.  |  If you encounter this problem: 1. switch to a different USB port on the docking station OR 2. Update KitProg3 firmware in Bootloader mode (press the mode switch while plugging in the board). |
|  PROGTOOLS-1488 | Junk characters might be observed in a UART terminal during programming of the connected kit or after programming is competed. | Clear UART buffers after kit programming is completed.   |
| PROGTOOLS-1490  | PSoC6 and PSoC4 kits with KitProg3 1.20 may hang after multiple rapid erase, program or read operations happening in sequence via openOCD. As results, you might see LIBUSB_ERORR_TIMEOUT in openOCD log files. |  Re-connect the kit physically. |


### More information

-   [fw-loader
    README.md](https://github.com/cypresssemiconductorco/Firmware-loader/blob/master/README.md)

-   [Kitprog3 User
    Guide](https://www.cypress.com/documentation/development-kitsboards/kitprog-user-guide)

-   [ModusToolbox Software Environment, Quick Start Guide, Documentation, and
    Videos](https://www.cypress.com/products/modustoolbox-software-environment)

-   [ModusToolbox Device Configurator Tool
    Guide](https://www.cypress.com/ModusToolboxDeviceConfig)

-   [Cypress Semiconductor](http://www.cypress.com)

© Cypress Semiconductor Corporation, 2019-2020.
