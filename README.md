Firmware-loader
===============

NOTE: if you cannot transition to DAPLink mode using CY8CPROTO-062-4343W, then get [Firmware-loader 2.2.01](https://github.com/cypresssemiconductorco/Firmware-loader/releases/tag/2.2.01.243) or newer, which fixes that problem.

### Overview

FW-loader is a cross-platform command line tool you can use to easily switch
back and forth between legacy KitProg2 and current KitProg3 on Cypress kits.
KitProg3 extends the kits' capabilities and adds DAPLink support. Click the
[Release](https://github.com/cypresssemiconductorco/Firmware-loader/releases)
button to download the latest release. Source code for Firmware-loader is not
available.

There is a package for each of the following operating systems:

-   linux
-   macos
-   windows

From the release page, download and unzip the appropriate zip archive for your OS. You can put the tool in any convenient location. ModusToolbox 1.1 installed an earlier version of the tool here: *install-dir/tools/fw-loader-2.1*.

After installing, open a command window in the tool's bin directory, and follow the
instructions below.

On Linux OS, run the udev_rules\\install_rules.sh script before the first run of
the FW-loader.

**Command-line Options**

**--help (or no arguments)** - Displays the list of supported commands with
their descriptions.

**--device-list** – Displays the list of connected devices.

**--update-kp3 [device-name]** – Update the firmware of the specified device to KitProg3.

**--update-kp2 [device-name]** – Downgrades the firmware of the specified device to KitProg2.

**--mode <mode> [device-name]** – Switches KitProg3 mode of the specific device. Supported modes are: 'kp3-hid', 'kp3-bulk', 'kp3-bootloader', 'kp3-daplink'.

If you have only one device attached, the [device-name] is optional. Where a device name is required, use the device name from the "--device-list" command.

**Mode switching in KitProg3**

Push the mode switch button on the kit to rotate among the supported modes.

![](.//media/ModeSwitchingDiagram.png)

If a kit does not support DAPLink mode, this mode is skipped.

In addition, the CY8CKIT-062S2-43012 kit supports a special operating mode that allows for two UART connections, rather than a single UART plus bridging (e.g. USB-I2C or USB-SPI). 

You cannot enter UARTx2 if the kit is in DAPLink mode. When the kit is in CMSIS-DAP Bulk or HID mode,  press and hold the mode switch for at least two seconds. In this mode the amber LED blinks at 2 Hz. To exit, press and hold the mode switch for at least two seconds. You return to CMSIS-DAP HID mode. 

### Notes

1.  KitProg2 supports two modes: Proprietary and CMSIS DAP. Only the Proprietary
    mode supports the bootloader. You must be in Proprietary mode for KitProg2
    to be visible to the FW-loader. Use the Mode Switch button to switch
    KitProg2 to Proprietary mode.

2.  For KitProg3, use the Mode Switch (SW3) button or FW-loader command to switch among KitProg3
    bulk, KitProg3 HID, and DAPLink modes

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

### More Information

[Fw-loader Release Notes](https://github.com/cypresssemiconductorco/Firmware-loader/blob/master/RELEASE.MD)
