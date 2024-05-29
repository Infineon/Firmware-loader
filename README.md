Firmware-loader
===============

### Overview

FW-loader is a cross-platform command line tool you can use to upgrade the KitProg3 FW on Cypress kits or MiniProg4.
[Download the latest release](https://github.com/Infineon/Firmware-loader/releases) which includes KitProg3 v2.60.1450.

There is a package for each of the following operating systems:

-   linux
-   macos
-   windows

From the release page, download and unzip the appropriate zip archive for your OS. You can put the tool in any convenient location. ModusToolbox™ 3.2 or newer release installs this tool also, but on the GitHub repo you can find always the latest release.

After installing, open a command window in the tool's bin directory, and follow the
instructions below.

On Linux OS, run the udev_rules\\install_rules.sh script before the first run of
the FW-loader.

On the Catalina version of macOS and later, you may see a dialog what Apple cannot check this package for malicious software. If this happens, please follow [instructions](https://support.apple.com/guide/mac-help/open-an-app-by-overriding-security-settings-mh40617/10.15/mac/10.15) from Apple.

**Command-line Options**

**--help (or no arguments)** - Displays the list of supported commands with
their descriptions.

**--device-list** – Displays the list of connected supported KitProg3-based devices.

**--update-kp3 [device-name]** – Updates the Firmware of the KitProg-based device to KitProg3.

**--update-kp2 [device-name]** – Updates the Firmware of the KitProg-based device to KitProg2.

**--mode <mode> [device-name]** – Switches KitProg3 mode of the specific device. Supported modes are: 'kp3-hid', 'kp3-bulk', 'kp3-bootloader', 'kp3-daplink', 'kp3-dualuart'.
On Windows hosts ‘kp3-bulk’ mode cannot support simultaneous I2C/SPI bridging (e.g. for CapSense tuning) - switch to ‘kp3-hid’ instead.

**--info [device-name]** – Displays the device information. Device information is displayed only for KitProg3 devices which support KitProg3 Unique ID Record.

**--set-kp3-gpio-pin <pin_number> <pin_mode> <state>** - Sets desired operational mode and state on GPIO pin of KitProg3-based device

**--read-kp3-gpio-pin <pin_number>** - Displays the current state of GPIO pin of KitProg3-based device

**--set-kp3-flow-control <port_number> <mode> [full-device-name|serial-num]** - Configures the UART flow control mode of the KitProg3 UART for a KitProg3-based device. If multiple supported
KitProg3-based devices are connected, specify the full device name or serial number. This is applicable only for KitProg3-based devices where UART HW flow control is supported. These can be found in the KitProg3 User Guide.

**--get-kp3-flow-control <port_number> [full-device-name|serial-num]** - Retrieves the UART flow control mode of the KitProg3 UART for a KitProg3-based device. If multiple supported
KitProg3-based devices are connected, specify the full device name or serial number. This is applicable only for KitProg3-based devices where UART HW flow control is supported. These can be found in the KitProg3 User
Guide.

If you have only one device attached, the [device-name] is optional. Where a device name is required, use the device name from the "--device-list" command. To update firmware of all the connected KitProg3 devices use 'all' specifier.

**Mode switching in KitProg3**

Push the mode switch button on the kit to switch modes. If a kit does not support DAPLink mode, the mode switch has no effect.

![](.//media/ModeSwitchingDiagram.png)

In addition, the CY8CKIT-062S2-43012 kit supports a special operating mode that allows for two UART connections, rather than a single UART plus bridging (e.g. USB-I2C or USB-SPI). 

You cannot enter UARTx2 if the kit is in DAPLink mode. When the kit is in CMSIS-DAP Bulk or HID mode, press and hold the mode switch for at least two seconds. In this mode the amber LED blinks at 2 Hz. To exit, press and hold the mode switch for at least two seconds. You return to CMSIS-DAP bulk mode. 

### Notes

1.  KitProg2 supports two modes: Proprietary and CMSIS DAP. Only the Proprietary
    mode supports the bootloader. You must be in Proprietary mode for KitProg2
    to be visible to the FW-loader. Use the Mode Switch button to switch
    KitProg2 to Proprietary mode.

2.  For KitProg3, the Mode Switch (SW3) button switches between CMSIS DAP bulk and
    DAPLink modes. You can use the command line to get into a legacy mode, CMSIS DAP
    using HID end points.

3.  MiniProg4 does not support KitProg2 firmware. The following symptoms show that
    KitProg2 firmware is installed on MiniProg4:

    -   The device is detected as MiniProg4 but does not operate.

    -   Errors are observed while performing the --device-list command:

        -   Error = Timeout of Response read for the "0x90" command. The number
            of attempts = 2.

        -   Error = Out Endpoint is not found.

If the KitProg2 firmware is installed on MiniProg4 - switch the device to Bootloader mode to restore the device functionality:

\- unplug MiniProg4 from the USB

\- while pressing the Mode Select button on the kit, plug in the USB cable

\- the Mode LED blinks to indicate the kit is in Bootloader mode

\- release the button

Perform the "--update-kp3" command as described above.

**FOSS Packages** 

FW-Loader uses some Open Source packages. FOSS Packages are located on the https://www.infineon.com/cms/en/design-support/software/free-and-open-source-software-foss/modustoolbox-foss-packages/

### More Information

[Fw-loader Release Notes](https://github.com/Infineon/Firmware-loader/blob/master/RELEASE.MD)
