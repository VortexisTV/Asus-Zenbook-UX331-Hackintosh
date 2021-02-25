# ASUS Zenbook UX331 OpenCore EFI Hackintosh
![](images/Zenbook.jpg)
![](images/AboutthisMac.png)

# Laptop Specifications

## *ASUS Zenbook UX331FN*
| Hardware                 | Name                                                     |
| ----------- | ----------------------------|
| CPU            | **Intel Core i5-8265U @ 1.60 GHz** |
| GPU    | **Intel UHD Graphics 620, NVIDIA MX150 (*disabled*)** |
| Memory | **8 GB DDR4** |
| Storage | **SanDisk SD7SN6S SATA M.2 256GB** |
| Sound Card     | **Realtek ALC294** |
| Touchpad     | **ELAN1200 I2C HID** |
| WiFi Card     | **Intel Dual Band Wireless-AC 8265** |

## Hardware Compatibility
OpenCore EFI might work with Zenbook models under UX333, but it's **not recommended.**     
Specifically geared towards Zenbooks with Coffee Lake laptop processors.

## Software Compatibility
As of **February 24, 2021**, it works with Mojave and above. Currently updated to `OpenCore 0.6.5`.

## Issues
1. Speakers may sound abit distorted
2. The battery may not charge all the way when booted to Mac OS. 
   - It happens to charge up to only 83%.
     - This can be solved by letting it charge all the way while leaving it turned off.
3. There is a bug where touchpad will sometimes stop working and work after a few minutes

## Everything that works perfectly at the moment
| Functions                 | Description                                                     |
| ----------- | ----------------------------|
| Intel Wi-Fi            | `Airportitlwm.kext` works well, but will give you at least a 30 MBit speed limit. |
| Bluetooth    | `IntelBluetoothFirmware.kext` is the BT driver added. |
| Sound | `alcid=21` layout ID is the only one that seems to work. Internal mic works.  |
| Battery Monitoring | `SSDT-USBX` needed for monitoring battery power for Coffee Lake laptops. |
| Screen Backlight     | `SSDT-PNLF-CFL` fixed backlight control support on Coffee Lake. `BrightnessKeys.kext` for tuning on the screen brightness using keyboard. |
| Fn Keys, Backlit Keyboard     | `AsusSMC` patches in `DSDT` enabled them.  |
| Graphics Acceleration     | `VoodooTSCSync` is required for Coffee Lake.  |
| Power Management     | `SSDT-PLUG` manages CPU power.   |
| Keyboard     | `VoodooPS2Controller.kext`  |
| Touchpad     | `VoodooI2C.kext`, `VoodooI2CHID.kext` and `SSDT-GPIO` enable the ELAN1200 touchpad. |
| Android Tethering     | `HoRNDIS.kext` works with no issues. |
| AirPlay     | Works with no issues  |

- Touchscreen (sometimes)
- Apple Services  
- Sleep
- USB

## Everything that doesn't work
- Ethernet  
- HDMI  
- Webcam
- Sidecar

## Not Tested yet
- AirDrop
