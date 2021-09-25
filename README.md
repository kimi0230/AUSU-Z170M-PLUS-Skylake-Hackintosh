# ASUS-Z170M-PLUS-Skylake-Hackintosh
Opencore EFI for ASUS-Z170-PlUS and i5-6400 and MacOS Big Sur 11.1

## Hardware
| Category     | Brand                                                              |
| -------- | ----------------------------------------------------------------|
| CPU      | i5 6400                                                       |
| MB       | ASUS Z170M-PLUS                                           |
| m2 ssd   | wd blue sn550 1t                                                |
| wifi     | BCM94360CD                                                      |
| VGA      | ASUS rx5500 4g                                        |

## Install Guide
https://kimi0230.medium.com/hackintosh-big-sur11-1-skylake-i5-6400-asus-z170m-plus-45b3380ec943


## Miscellaneous
* Apple TV Can't Play
    * https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.Chart.md
* iMovies Can't Export
    * change iMac17,1 to iMac19,1
* Sleep Wake failure in EFI 
    * https://dortania.github.io/OpenCore-Post-Install/universal/sleep.html#preparations
``` shell
sudo pmset -a hibernatemode 0
sudo rm /var/vm/sleepimage
sudo mkdir /var/vm/sleepimage
sudo pmset powernap 0
sudo pmset -a standby 0
sudo pmset -a autopoweroff 0
sudo pmset proximitywake 0
sudo pmset tcpkeepalive 0
```

## Upgrade Opencore version
01. Download Latest Version Opencore
    * https://github.com/acidanthera/OpenCorePkg/releases
02. copy X64/EFI as new EFI folder
03. copy Docs/Sample.plist to new EFI/OC folder
05. copy EFI/OC/ACPI
06. copy EFI/OC/Drivers
07. Downlad new [Kexts](https://dortania.github.io/OpenCore-Install-Guide/ktext.html)
    * [AppleALC](https://github.com/acidanthera/applealc/releases)
    * AppleMCEReporterDisabler
    * [CtlnaAHCIPort](https://github.com/dortania/OpenCore-Install-Guide/blob/master/extra-files/CtlnaAHCIPort.kext.zip)
    * [IntelMausi](https://github.com/acidanthera/IntelMausi/releases)
    * [Lilu](https://github.com/acidanthera/lilu/releases)
    * [NVMeFix](https://github.com/acidanthera/NVMeFix/releases)
    * [VirtualSMC](https://github.com/acidanthera/VirtualSMC)
    * [USBInjectAll](https://github.com/Sniki/OS-X-USB-Inject-All/releases)
    * [WhateverGreen](https://github.com/acidanthera/whatevergreen/releases)
08. Modify sample.plist same as before, then change name to config.plist
09. Copy EFI to USB drive to test
10. Choise your disk name at oc picker menu not efi
11. Move efi to your system disk if boot into macOS successfully
12. `ctrl+enter` at oc picker menu. you can select your default menu.
