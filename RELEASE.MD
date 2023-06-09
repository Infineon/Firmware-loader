### fw-loader v3.5.0 Release Notes

The Firmware Loader (fw-loader) is a cross-platform command line tool you can use to upgrade the KitProg3 firmware on our kits or MiniProg4. Please refer to the README file for a complete description of the fw-loader tool.

### New Features

- Adds "--set-kp3-flow-control" and "--get-kp3-flow-control" commands to configure KitProg3 UART flow control. Note: This works only for KitProg3 devices that, by default, support KitProg3 UART Hardware Flow Control.
- Delivers KitProg3 v2.50 with UART updated drivers and port renaming. The KitProg3 drivers have been updated to provide better port naming for connectivity devices (that is, Bluetooth® devices and combo devices in embedded mode). A new PID has been allocated to Bluetooth® device-based kits to differentiate them from MCU kits. In addition to the UART drivers, CyBridge library and KitProg3 FW have also been updated to handle the new PID. Note: If you upgrade your kit to use KitProg3 version 2.50, tools from the ModusToolbox™ 3.0 tools package and earlier will not detect the kit any longer.
- Bug fixing.

### Known Issues
None

### More information

-   [fw-loader
    README.md](https://github.com/cypresssemiconductorco/Firmware-loader/blob/master/README.md)

-   [Kitprog3 User
    Guide](https://www.cypress.com/documentation/development-kitsboards/kitprog-user-guide)

-   [KitProg Host Protocol Interface](https://www.cypress.com/file/520056/download)

-   [ModusToolbox™ Software Environment, Quick Start Guide, Documentation, and
    Videos](https://www.cypress.com/products/modustoolbox-software-environment)

-   [ModusToolbox™ Device Configurator Tool
    Guide](https://www.cypress.com/ModusToolboxDeviceConfig)

-   [Cypress Semiconductor, an Infineon Technologies Company](http://www.cypress.com)

© Cypress Semiconductor Corporation, 2019-2023. This document is the property of Cypress Semiconductor Corporation, an Infineon Technologies company, and its affiliates ("Cypress"). 

