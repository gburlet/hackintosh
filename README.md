# B360 i7-8700 RX 6600 Hackintosh Build

[![OpenCore 0.8.4](https://img.shields.io/badge/OpenCore-0.8.4-green)](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.8.4)
[![MacOS Monterey 12.5](https://img.shields.io/badge/macOS-12.5-9cf)](https://www.apple.com/macos/monterey/)

> :file_folder: Download latest EFI from [Releases](https://github.com/gburlet/hackintosh/releases)

> **Please Note**: This is a personal build that's configured for my exact hackintosh hardware. YMMV

I followed the [Dortania OpenCore Guide](https://dortania.github.io/getting-started/) and various forum posts to get this operational.

![About_publiic](https://user-images.githubusercontent.com/1033190/193471674-dc5d13c1-2359-4dcf-bb83-a550087990b8.PNG)

## Hardware Specs

|         Component | Details                                            |
| ------------: | :------------------------------------------------- |
|         Board | Asus TUF B360-Pro Gaming (WiFi)                                 |
|           CPU | Intel Core [i7-8700](https://ark.intel.com/content/www/us/en/ark/products/126686/intel-core-i78700-processor-12m-cache-up-to-4-60-ghz.html) 3.2GHz 12MB (Coffee Lake)  |
|        Memory | Corsair Vengeance LPX D4 2x16GB (DDR4 2666MHz)      |
|           NVMe | WD Black gen2 M.2 SSD 250GB                   |
|  GPU | Gigabyte AMD [Radeon RX 6600](https://www.amazon.ca/GIGABYTE-Graphics-WINDFORCE-Cooling-GV-R66EAGLE-8GD/dp/B09J2NCD2L) 8GB     |
|         iGPU  | Intel UHD Graphics 630                              |
| Audio | [Integrated] ALC887-VD Analog + Digital |
| Ethernet | [Integrated] Intel I219V Gigabit LAN Controller |
| Wireless | [Fenvi FV-T919](https://www.amazon.ca/gp/product/B08JQ6GPGM) Broadcom BCM94360CD |
| Bluetooth | [Fenvi FV-T919](https://www.amazon.ca/gp/product/B08JQ6GPGM) Broadcom BCM94360CD |
| Cooling | Corsair H60 Liquid Cooling |

Note: Asus Tuf B360-Pro Gaming motherboard also has integrated Wifi and Bluetooth [Intel Wireless-AC 9560](https://www.intel.ca/content/www/ca/en/products/sku/99446/intel-wirelessac-9560/specifications.html). Wifi worked with kexts, but Bluetooth (and Airdrop, etc.) did not work no matter what I tried, so I picked up the native Broadcom wireless card instead.

- Total Hackintosh Cost: **$1,032 CAD**
- Mac Pro Tower 2022 Base Model (Intel Xeon W-1390P, Radeon Pro W5500) Cost: **$7,499 CAD**

## EFI Details

OpenCore 0.8.4

| Kext  | Notes |
| ------: | :------- |
| Lilu | Required, must be first |
| VirtualSMC | Required, must be second |
| WhateverGreen | Required for GFX |
| SMCProcessor | Monitoring Intel CPU temp |
| SMCSuperIO | Monitoring fan speed |
| RadeonSensor | Monitoring GPU temp, required by SMCRadeonGPU |
| SMCRadeonGPU | Monitoring GPU temp |
| AppleALC | Enable onboard audio ports |
| IntelMausi | Enabled onboard ethernet network adapter |
| USBToolBox | Used for USB mapping, required by UTBMap |
| XCHI-unsupported | Needed for USB port mapping on my mobo |
| UTBMap | USB Mapping (see below) |

### USB Mapping

You'll **100%** need to do your own USB Mapping on your machine or the hackintosh will not work. Do not just copy paste UTBMap.kext for your build unless you have the **exact** same motherboard.

## Stability

I was able to get everything working after a lot of fiddling.

| Feature | Works |
| ------: | :---- |
| USB Ports | :white_check_mark: |
| Wifi | :white_check_mark: |
| Bluetooth | :white_check_mark: |
| Airdrop | :white_check_mark: |
| Airplay | :white_check_mark: |
| Onboard Audio | :white_check_mark: |
| GPU HDMI Audio (monitor speakers) | :white_check_mark: |
| Sleep | :white_check_mark: |
| Shutdown / Restart | :white_check_mark: |

The biggest issue for this motherboard was that MMIO whitelisting was required for consistent booting. Without going through that process, maybe 1 in 3 boots would result in getting stuck at ([EB|#LOG:EXITBS:START])[https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/extended/kernel-issues.html#stuck-on-eb-log-exitbs-start] when booting. More info on this in the github wiki.

## Install Notes

See the github wiki for more detailed install notes.
