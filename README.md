# Firmware-loader

FW-loader is a cross-platform command line tool you can use to easily switch back and forth between legacy KitProg2 and current KitProg3 on Cypress kits. Upgrading FW to KitProg3 extends the kits' capabilities and adds DAPLink support. Click the [**Release**](https://github.com/cypresssemiconductorco/Firmware-loader/releases) button to download the latest release. Source code for Firmware-loader is not available. The source archives in the release are empty.

Three types of packages are available that are designed to work in the following operating systems:

- linux
- macos
- windows

Download and unzip the appropriate zip archive for your OS. Open a command window in the tool's bin directory, and follow the instructions below.

On Linux OS, run the udev_rules\install_rules.sh script before the first run of the FW loader.


**Command-line Options**

**--help (or no arguments)** - Displays the list of supported commands with their descriptions.

**--device-list** – Displays the list of connected devices.

**--update-kp3 [device-name]** – Updates the device FW to KitProg3.

**--update-kp2 [device-name]** – Updates the device FW to KitProg2.

The device name can be skipped if only one KitProg device is connected to the PC. Where a device name is required, use the device name from the "--device-list" command.


NOTES 

1.  KitProg2 supports two modes: KitProg2 Proprietary. and CMSIS DAP. Only the KitProg2 Proprietary mode supports the bootloader. You must be in KitProg2 Proprietary mode for the KitProg2 to be visible to the FW loader. Use the Mode Switch button to switch KitProg2 to Proprietary mode.

2.  KitProg3 supports two modes: CMSIS-DAP BULK and CMSIS-DAP HID. It also implements DAPLink as a custom application.     Only the KitProg3 modes support the bootloader and therefore you must be in these modes for KitProg3 to be visible to the FW loader. Use the Custom App Switch button to switch between the KitProg3 and Custom App modes.
  
3. Use the Custom App Switch button to switch between KitProg3 and Custom App and vice versa:
    - For a single-button kit (CY8CPROTO_062_4343W), press the SW3 button for more than 2 seconds and then release it.
    - For two-button kits (CY8CKIT-062-BLE, CY8CKIT_062_WIFI_BT and CY8CKIT-062-4343W ), press and release the SW4 (custom app button) button.

4.  MiniProg4 does not support KitProg2 FW. 
    The following symptoms show that KitProg2 FW is uploaded to MiniProg4:
    - The device is detected as MiniProg4 but does not operate.
    - Errors are observed while performing the "--device-list" command:
        - Error =  Timeout of Response read for the "0x90" command. The number of attempts = 2.
        - Error =  Out Endpoint is not found.

    If the KitProg2 FW is uploaded to MiniProg4 - to restore the device functionality:
    
        1. Switch the device to Bootloader mode:
            - unplug MiniProg4 from the USB
            - plug in a USB cable while pressing the Mode Switch button (SW1) on the kit
            - LED1 blinks to indicate the kit is in Bootloader mode
            - release the button
    
        2. Perform the "--update-kp3" command as described above.
