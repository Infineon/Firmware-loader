### Fw-loader v2.3.0 Release Notes

Please refer to the README.md for a complete description of the fw-loader.

### New Features

- Delivers KitProg3 v1.20 firmware with the following:
    1. Improve performance over SWD in KitProg3 modes
    2. Hide KitProg3 HID mode - use the Mode Switch (SW3) button or FW-loader command to switch among   KitProg3 bulk and DAPLink modes. If need to use KitProg3 HID, use FW-loader command only.
    3. Add support of DAPlink mode for MiniProg4 probe. Note: mass storage functionality is not available in this case
    3. Bug fixes
- Bug fixes 

### Known Issues

-   KitProg3 firmware might not be updated properly on a particular USB port on some Lenovo ThinkPad Pro Docking Station. If you encounter this problem:
    1. switch to a different USB port on the docking station OR
    2. Update KitProg3 firmware in Bootloader mode (press the mode switch while plugging in the board)

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
