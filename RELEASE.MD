### Fw-loader v2.2.11 Release Notes

Please refer to the README.md for a complete description of the fw-loader.

### New Features

- Delivers KitProg3 v1.14 firmware with the following:
    1. Support of new kits in KitProg3 and DAPLink: CY8CPROTO-064B0S3, CY8CPROTO-064B0S1-BLE and CY8CKIT-064B0S2-4343W
    2. Support JTAG communication for programming and debugging via MiniProg4 probe
    3. Bug fixes
- Improves format of displayed info after --device-list execution
- Adds possibility to update firmware on all connected kits
- Bug fixes 

### Known Issues

-   KitProg3 firmaware migth not be updated properly on a particular USB port on some Lenovo ThinkPad Pro Docking Station. If you encounter this problem:
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
