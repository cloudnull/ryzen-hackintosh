# OpenCore EFI for AMD Ryzen Hackintosh

## Specification
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen 3 1200 |
| Motherboard | ASRock AB350 K4 |
| Memory | 8GiB DDR4 2133 |
| GPU | Sapphire Pulse RX 580 8G |
| WiFi & Bluetooth | AirPort Extreme  (0x14E4, 0x111) |
| OS Disk (NVMe) | SAMSUNG MZNTY128HDHP 128GB |

> No audio was listed because the onboard HDAudio controller is not supported, and I didn't want to use additional Kext's. To provide audio a USB DAC is being used. 

| **Software** | **Version** |
| ------------ | ----------- |
| macOS version | 10.15.5 |
| OpenCore version | 0.5.9 |

## Drivers & Kexts
- [[Bootloader] OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [[Resources] Picker GUI](https://github.com/acidanthera/OcBinaryData/tree/master/Resources)
- [[Patch] AMD_Vanilla](https://github.com/AMD-OSX/AMD_Vanilla)
- [[Driver] OpenRuntime](https://github.com/acidanthera/OpenCorePkg)
- [[Driver] OpenCanopy](https://github.com/acidanthera/OpenCorePkg)
- [[Driver] HFSPlus](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
- [[Kext] Lilu](https://github.com/acidanthera/Lilu)
- [[Kext] VirtualSMC](https://github.com/acidanthera/VirtualSMC)
- [[Kext] WhateverGreen](https://github.com/acidanthera/WhateverGreen)
- [[Kext] RealtekRTL8111](https://bitbucket.org/RehabMan/os-x-realtek-network/downloads/)

## Not working
- Hypervisor.framework (VirtualBox and XCode iOS emulator works)

## How to use
1. Create directory "EFI" in your EFI partition (e.g. pendrive or hard drive)
2. Clone this repo and paste directiories "BOOT" and "OC" onto created directory
3. Download [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) to generate unique SMBIOS information. Run it and select **Generate SMBIOS**, as model select **iMacPro1,1**.
4. Open config.plist with [**ProperTree**](https://github.com/corpnewt/ProperTree) and go to PlatformInfo > Generic. Set MLB (Board Serial), SystemSerialNumber (Serial) and SystemUUID (SmUUID) to generated values.
5. Make USB installer with [**this guide**](https://dortania.github.io/OpenCore-Desktop-Guide/installer-guide/)
6. Boot it!  

> You must update the `SystemSerialNumber`, `ROM`, `MLB`, and `SystemUUID` in the `config.plist` file. Faliure to update these values will create an unreliable / unstable environment.

## Additional guides

Need additional help, jump into the discussion on [**AMD-OSX Discord**](https://discord.gg/EfCYAJW) or use the [**Forum**](https://forum.amd-osx.com)  

###### How to create a USB guide
- Creating USB installer: [**\*click\***](https://dortania.github.io/OpenCore-Desktop-Guide/installer-guide/)

###### Zen specific notes

Check this out if you have problems with install/boot macOS, kernel panic or another system related issues check OC configuration guide

- OpenCore configuration: [**\*click\***](https://dortania.github.io/OpenCore-Desktop-Guide/AMD/zen.html)

###### Other Issues 

If something additional does not work (USB ports, iServices, DRM/Netflix) check Post-Install guide

- Post-Install: [**\*click\***](https://dortania.github.io/OpenCore-Desktop-Guide/post-install/)

#### Proof of Life

![Screenshot](/screenshot.png?raw=true)
