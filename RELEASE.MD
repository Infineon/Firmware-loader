### fw-loader v3.0.0 Release Notes

Please refer to the README.md for a complete description of the fw-loader.

### New Features

- Delivers KitProg3 v2.00.809 firmware with:
    1. Support of PSoC64-2M and PSoC64-512K production MCUs and kits
    Note: KitProg3 v2.00.809 does not support pre-production versions of PSoC64 MCUs. If you would like to continue to work with pre-production versions, please use the previous releases of KitProg3 and fw-loader
- Support  of new CY8CKIT-064S0S2-4343W kit

### Known Issues

| ID                                | Known Issue                       | Workaround                          |
|-----------------------------------|-----------------------------------|-----------------------------------|
|  PROGTOOLS-768 | KitProg3 firmware might not be updated properly on a particular USB port on some Lenovo ThinkPad Pro Docking Station.  |  If you encounter this problem: 1. switch to a different USB port on the docking station OR 2. Update KitProg3 firmware in Bootloader mode (press the mode switch while plugging in the board). |
|  PROGTOOLS-1488 | Junk characters might be observed in a UART terminal during programming of the connected kit or after programming is competed. | Clear UART buffers after kit programming is completed.   |


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
