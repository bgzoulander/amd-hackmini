# AMD Hack Mini (Gigabyte BRIX w/ Ryzen 5 4500U)
Mini-guide to get OpenCore working on a Gigabyte BRIX barebones mini-Ryzentosh

Current version: macOS Sequoia 15.5
![Screenshot_macOS_15 5](https://github.com/user-attachments/assets/8cf26a1a-75fa-4935-93a0-ba7ccc59e960)

## System configuration
| Onboard | Gigabyte BRIX GB-BRR5-4500 | Notes |
| --- | --- | --- |
| CPU | AMD Ryzen 5 4500U | Generate [SSDTs](https://github.com/corpnewt/SSDTTime) |
| GPU | Integrated (Radeon Graphics, Vega 6) | NootedRed, increase UMA frame buffer from 64 MB |
| WiFi | Intel AX200 (Wifi6) | itlwm + HeliPort |
| Bluetooth | Intel AX200 (BT 5.2) | IntelBluetoothFirmware+IntelBTPatcher >v2.5, BlueToolFixup |
| Ethernet | Realtek 8125 (2.5G) | LucyRTL8125Ethernet |
| Audio | Realtek ALC255 | AppleALC, layoutid=11 |
| USB | 5x USB A, 2x USB C (3.2) | [Map USB Ports as kext](https://github.com/USBToolBox/tool) |
| **User-added** |
| RAM | 2x16 GB Kingston FURY Impact SO-DDR4 | [Provide custom KASLR slide](https://dortania.github.io/OpenCore-Install-Guide/extras/kaslr-fix.html) |
| SSD | 1 TB WD SN770 (PCIe gen 4) | |
| SMBIOS | iMac20,1 | Allows support for NootedRed + Tahoe |

## Working
-	All main hardware, graphics + HW acceleration, HDMI/miniDP/audio output, WiFi/BT
-	Power management (sleep, fan) works OK with temperature sensor output using SMCProcessorAMD+SMCRadeonSensors

## Not tested/working
-	Ethernet [?]
-	iServices and continuity features [?]
-	Tried trulyspinach's SMCAMDProcessor+AMDRyzenCPUPowerManagement instead of the above for CPU management and clock speed readings, but was not as stable (kernel panic sometimes at boot). Either way, it makes no difference to CPU and GPU performance according to Geekbench results

## Relevant guides
-	Dortania's guide to [OpenCore](https://dortania.github.io/OpenCore-Install-Guide/)
-	ChefKissinc's guide for AMD-specific [ACPI](https://chefkissinc.github.io/guides/hackintosh/gathering-files/acpi/) and [kexts](https://chefkissinc.github.io/guides/hackintosh/gathering-files/kexts/)
-	ChrisWayg's [visual guide](https://chriswayg.gitbook.io/opencore-visual-beginners-guide)

## Credits
-	Developers ([acidanthera](https://github.com/acidanthera), [ChefKiss](https://github.com/chefkissinc), [corpnewt](https://github.com/corpnewt), too many to mention)
-	Guide authors ([Dortania](https://github.com/dortania), [ChrisWayg](https://github.com/chriswayg))

**Files provided are for reference and educational purposes only. Use them in your system at your own risk.**
