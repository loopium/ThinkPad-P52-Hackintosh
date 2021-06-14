
Working on a near-perfect opencore config for my ThinkPad P73 (UHD, i7-9750H, 32 GB RAM).

All good except Battery Status and Fingerprint reader this far.

Upgraded OpenCore release to 0.7.0 and edited the config.plist to match.

Searching for patched battery ACPI files for the battery issue or I will have to 
try to make one, which seems quite a chore.

There is a rev-eng of the Synaptic Metallica MIS fingerprint device available
with some arch/AUR package. Could be portable to macOS. 



-----

[![BIOS](https://img.shields.io/badge/BIOS-1.37-brightgreen.svg)](https://pcsupport.lenovo.com/us/en/products/LAPTOPS-AND-NETBOOKS/THINKPAD-P-SERIES-LAPTOPS/THINKPAD-P52-TYPE-20M9-20MA/20M9/downloads/DS504024)
![macOS](https://img.shields.io/badge/macOS-11.0%20beta4-orange.svg)
![Clover](https://img.shields.io/badge/OpenCore-0.6.0-blue.svg)
<img align="right" src="https://www.notebookcheck.net/uploads/tx_nbc2/teaser1_25.jpg" alt="Critter" width="300">
## Status - Discontinued

## Introduction (QQ Group Chat: 97986046)

Tips: If you want to use built-in network adapter, you'd better buy a new pcie card, and I suggest DW1560 or DW1830, considering about the size and space. Also, P52 does not have whitelist upon WLAN hardware, you even do not need to modify your BIOS

## Installing Guides
- [Simplified Chinese Video Guides | Bilibili.com](https://space.bilibili.com/188733433?from=search&seid=782751373682115347)
- Thanks to z for supporting the guides video

## Releases (Until 2020/8/18)
- The latest version: V4.2
- [Download Here](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/releases/download/4.2/EFI-4.2.zip)

## Updates (Until 2020/8/18)
- Update to OpenCore 0.6.0 official version
- Support macOS 11.0 beta 4
- Fix a few minor bugs

## Updates (Until 2020/2/12)
- Add device support for P53 and P73

## Updates (Until 2020/1/22)
- RAM 32GB single slot is supported natively
- AppleALC is merged in the official version. The CODE has been merged in acidanthera's GitHub

## Updates (Until 2020/1/14)
- Happy New Year!!
- Update Clover version to r5103

## Updates (Until 2019/12/17)
- Customize the AppleALC, add Layout-ID 52 to the appleALC kext.
- Update Clover version to r5100
- Support Catalina macOS 10.15.3 beta1

## Updates (Until 2019/11/10)
- Fully supports macOS 10.15.2 Catalina
- USB3.1 supported under macOS Catalina
## Updates (Until 2019/10/7)
- Fully supports macOS 10.15 Catalina
## Updates (Until 2019/8/21)
- 10.15 beta 6 is supported
- Touchpad is supported, 5 finger-touch is detected
- Fans Speed could be detected
- Thunderbolt 3 was improved

## Updates (Until 2019/7/24)
- The new version uses ssdt, aka the hotpatch, and ThunderBolt 3 ports are supported, and eGPU is supported.
- 128G DDR4 version P52 can boot up
- Xeon E2176m version P52 can boot up
- Core i7-8750H, i7-8850H, i9-8959HK, Xeon E2176m are supported
- We are close to the perfect
- Brightness control hotkey works properly
- IR camera is disabled to avoid the default camera switched to IR camera
- Touch Screen & Stylus works

## Touchpad
- Solved with VoodooSMBus, and 5 finger could be detected
- ~~It seems that the full gesture will be enabled, I haven't tested it yet. If anyone has interest in it, try the kext, patches and instructions mentioned in the following link, [ELANSMBus](https://github.com/gokula/ELANSMBus)~~
## What do you need
- Lenovo ThinkPad P52 Series Notebook, It seems that P72 can also work with this clover, not tested
- Mojave disk image is prepared, normally .dmg file, 10.14 & 10.14.2 & 10 ver.14.3 version has been tested
- USB storage (at least 8 Gigabytes)
- Broadcom DW1560 or DW1830 WLAN PCIE card (DW1830 requires modified antenna)

## BIOS Configuration
- Boot mode: UEFI
- Display mode: Hubrid Graphics
- security boot- disabled
- Storage mode: AHCI (If you are in RST mode, you need to switch it to AHCI mode)

## Full Compatibility
- Boot clover with UEFI mode
- Built-in keyboard (partial function key and Num keyboard works well)
- native USB3 / USB2 ports (USB type-c can work, ~~but two thunderbolts has not been tested~~)
- AppleHDA native audio, Speakers + Internal Mic + Headphone
- Built in Camera
- Native power management
- Battery Status (Percentage can be displayed)
- Brightness control 
- Backlit keyboard (Use Fn + space)
- INTEL iGPU UHD 630 1536MB Vram (DGPU has been disabled by hotpatch)
- Ethernet port
- Mac App Store works normally
- CPU SpeedStep
- Sleep + Wake
- Multitouch Touchpanel
- Wireless LAN [Broadcom DW1560(OEM by Dell), DW1830(OEM by Dell), BCM94352Z(OEM by Lenovo), BCM943602BAED(OEM by Lenovo), BCM94360CS2(OEM by Apple), BCM943602CS(OEM by Apple)]
- Bluetooth
- AirDrop, AirPlay and HandOff
- Trackpoint
- 4K display (Use 4K version config)
- Thunderbolt works properly, even connecting to eGPU using graphics dock.
## Partially working devices
- ~~Touchpad can work with one finger gesture by using VoodooPS2 kext~~
- ~~in the future touchpad can work with ApplePS2SmartTouchPad kext by patching hopefully~~

## Disabled devices
- HDMI, HDMI port is connected with disabled NVIDIA DGPU (Use ThunderBolt eGPU to connect the external monitor, we recommand you using AMD Radeon RX series or Vega series)
- LTE WWAN card (L850GL)

## System Screen Shot
### System Info
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/sys.png)
### RAM Slots
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/mem.png)
### Displays
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/display.png)
### eGPU & Thunderbolt3
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/tb.jpg)
### eGPU connected via ThunderBolt3 graphics card dock
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/tbdockpv.jpg)
### Power menu
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/powermenu.png)
### USB ports
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/usb.png)
### Graphics
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/graphics.png)
### Audio
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/audio.png)
### Power
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/batt.png)
### wifi
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/wifi.png)
### Bluetooth
![image](https://github.com/liuyishengalan/ThinkPad-P52-Hackintosh/blob/master/ScreenShots/bt.png)


