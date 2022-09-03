# B360 i7-8700 RX 6600 Hackintosh Build

[![OpenCore 0.7.8](https://img.shields.io/badge/OpenCore-0.7.8-green)](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.7.8)
[![MacOS Monterey 12.5](https://img.shields.io/badge/macOS-12.5-9cf)](https://www.apple.com/macos/monterey/)

> :file_folder: Download latest EFI from [Releases](https://github.com/gburlet/hackintosh/releases)

> **Please Note**: This is a personal build that's configured for my exact hackintosh hardware. YMMV

I followed the [Dortania OpenCore Guide](https://dortania.github.io/getting-started/) and various forum posts to get this operational.

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
| Wireless | [Integrated] [Intel Wireless-AC 9560](https://www.intel.ca/content/www/ca/en/products/sku/99446/intel-wirelessac-9560/specifications.html)         |
| Bluetooth | [Integrated] [Intel Wireless-AC 9560](https://www.intel.ca/content/www/ca/en/products/sku/99446/intel-wirelessac-9560/specifications.html) |

- Total Hackintosh Cost: **$1,032 CAD**
- Mac Pro Tower 2022 Base Model (Intel Xeon W-1390P, Radeon Pro W5500) Cost: **$7,499 CAD**

## EFI Specs

OpenCore 0.7.8

## USB Mapping

Used USBToolkit, followed [this guide](https://chriswayg.gitbook.io/opencore-visual-beginners-guide/alternatives/usb-mapping-on-windows). You can map prior to installing Mac OS in windows, or insert USBInjectAll.kext to install and check things are working before doing the full mapping.

## Stability

| Feature | Works |
| USB Ports | :white_check_mark: |
| Wifi | :white_check_mark: |
| Bluetooth | ? |
| Airdrop | ? |
| Audio | ? |
| GPU HDMI Audio | :white_check_mark: |
| Sleep | :x: |
