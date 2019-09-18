### Fw-loader v2.2 Release Notes

Please refer to the README.md for a complete description of the fw-loader.

### New Features

\- Supports new kits: CY8CPROTO-064-SB, CY8CPROTO-062S2-43012,
CY8CKIT-062S2-43012

\- Delivers KitProg3 v1.12 firmware with the following:

1.	Added support of new kits into KitProg3 and DAPLink: CY8CPROTO-064-SB, CY8CPROTO-062S2-43012 and CY8CKIT-062S2-43012
2.	Added programming of external memory via DAPLink 
3.	Changed the switching to DAPlink mode – as of v1.11 use 'Mode Select' switch to cycle through the three modes: Bulk, HID and DAPLink. Note: the Custom App switch is deprecated and does not perform any action.
4.	Replaced DAPlink HID with Bulk endpoints that improves performance

KitProg3 v1.12 fixes a defect that prevented transition to DAPLink mode on some kits.

### Known Issues

-   None

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

© Cypress Semiconductor Corporation, 2019.
