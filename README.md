# Hackintosh

This is a git repo of my [OpenCore](https://github.com/acidanthera/OpenCorePkg) EFI folder.
Everything was made by following the (excellent) [OpenCore Vanilla Guide](https://khronokernel.github.io/Opencore-Vanilla-Desktop-Guide/).

Shout out to MykolaG on the r/Hackintosh Discord for their help with [Windows booting](https://github.com/eramdam/hackintosh/commit/d15d29f647c305db44c1188222cbd3f53f172deb) and [Apple RTC issue on poweroff](https://github.com/eramdam/hackintosh/commit/c1922b0f254289a8ac59ce65211f1624583b1a4e).

Feel free to re-use this configuration if you have the same CPU + motherboard combo and an AMD GPU.

**Disclaimer**: You'll obviously want to re-generate new SMBIOS informations and not re-use those in the file as-is!

## Hardware configuration

[PCPartPicker Part List](https://pcpartpicker.com/list/cqKD7T)

| Type             | Item                                                                                                                                                                                                 |
| :--------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **CPU**          | [Intel Core i9-9900K 3.6 GHz 8-Core Processor](https://pcpartpicker.com/product/jHZFf7/intel-core-i9-9900k-36ghz-8-core-processor-bx80684i99900k)                                                    |
| **CPU Cooler**   | [NZXT Kraken X53 73.11 CFM Liquid CPU Cooler](https://pcpartpicker.com/product/PVfFf7/nzxt-kraken-x53-7311-cfm-liquid-cpu-cooler-rl-krx53-01)                                                        |
| **Motherboard**  | [Asus ROG STRIX Z390-I GAMING Mini ITX LGA1151 Motherboard](https://pcpartpicker.com/product/Tmprxr/asus-rog-strix-z390-i-gaming-mini-itx-lga1151-motherboard-rog-strix-z390-i-gaming)               |
| **Memory**       | [Corsair Vengeance RGB Pro 32 GB (2 x 16 GB) DDR4-3200 Memory](https://pcpartpicker.com/product/L7qhP6/corsair-vengeance-rgb-pro-32gb-2-x-16gb-ddr4-3200-memory-cmw32gx4m2c3200c16w)                 |
| **Storage**      | [Samsung 970 Evo 1 TB M.2-2280 NVME Solid State Drive](https://pcpartpicker.com/product/JLdxFT/samsung-970-evo-10tb-m2-2280-solid-state-drive-mz-v7e1t0baw)                                          |
| **Storage**      | [Samsung 970 Evo 1 TB M.2-2280 NVME Solid State Drive](https://pcpartpicker.com/product/JLdxFT/samsung-970-evo-10tb-m2-2280-solid-state-drive-mz-v7e1t0baw)                                          |
| **Video Card**   | [Sapphire Radeon RX 5700 XT 8 GB PULSE Video Card](https://pcpartpicker.com/product/3YTzK8/sapphire-radeon-rx-5700-xt-8-gb-pulse-video-card-11293-01-20g)                                            |
| **Case**         | [NZXT H210 Mini ITX Tower Case](https://pcpartpicker.com/product/x7hmP6/nzxt-h210-mini-itx-tower-case-ca-h210b-w1)                                                                                   |
| **Power Supply** | [EVGA SuperNOVA G2 650 W 80+ Gold Certified Fully Modular ATX Power Supply](https://pcpartpicker.com/product/9q4NnQ/evga-power-supply-220g20650y1)                                                   |
| **Custom**       | [OEM Dell Wireless DW1560 802.11ac Broadcom BCM94352Z M.2 NGFF WIFI Card 6XRYC](https://pcpartpicker.com/product/fM4NnQ/oem-dell-wireless-dw1560-80211ac-broadcom-bcm94352z-m2-ngff-wifi-card-6xryc) |

## What works

- iCloud
- iMessages
- FaceTime
- App Store
- Sleep
- Onboard Audio
- Ethernet
- Bluetooth
  - Continuity / Handoff
  - Copy-paste across devices — although it's finnicky at times. But it's also like this on my real Macs so I'm not worried.
- Wi-Fi
  - AirDrop
- Netflix/DRM in Safari (haven't tested other apps but I expect it to work)
- Sidecar (albeit finnicky at times..)
- Booting into Windows with OpenCore

## What doesn't work / didn't test

- Audio over HDMI / DisplayPort

## Config quirks

- Bluetooth worked for the "most part" with the latest version of [BcrmPatch](https://github.com/acidanthera/BrcmPatchRAM) but it wasn't reliable at all. [Switching to 2.3.0d3](https://hologos.github.io/brcmpatchram3-v2.5.0-bcm94352z-dw1560-is-broken/) fixed it for me. https://github.com/eramdam/hackintosh/commit/cca820532536e6e97631b829a4b8c768e2a740dc

## System Information

<details>

![](meta/about-mac-screenshot.png)
![](meta/neofetch-screenshot.png)

</details>

## [Benchmarks](./docs/benchmarks.md)

## USB Ports

| Enabled | Ports | Type                  | Description                          |
| ------- | ----- | --------------------- | ------------------------------------ |
| [ ]     | HS01  | USB 2 Type C + Switch | Case USB Type-C                      |
| [ ]     | HS02  | USB 2 Type C + Switch | Rear USB Type-C                      |
| [ ]     | HS03  | USB 3                 | Rear USB 3.1 Gen 2 (red) - right     |
| [ ]     | HS04  | USB 3                 | Rear USB 3.1 Gen 2 (red) - left      |
| [x]     | HS05  | USB 2                 | Rear USB 2 (black) - right           |
| [x]     | HS06  | USB 2                 | Rear USB 2 (black) - left            |
| [x]     | HS07  | USB 3                 | Rear USB 3.1 Gen 1 (blue) - right    |
| [x]     | HS08  | USB 3                 | Rear USB 3.1 Gen 1 (blue) - left     |
| [ ]     | HS09  | USB 3                 | Front USB 3.1 Gen 1                  |
| [ ]     | HS10  | ???                   | ???                                  |
| [x]     | HS11  | Internal connector    | NZXT LED Controller                  |
| [x]     | HS13  | Internal connector    | RGB LED Lightning - Aura Motherboard |
| [x]     | HS14  | Internal connector    | Bluetooth/Wifi - Dell                |
| [ ]     | SS01  | USB 3.1 Type C        | Case USB Type-C (orientation A)      |
| [ ]     | SS02  | USB 3.1 Type C        | Case USB Type-C (orientation B)      |
| [x]     | SS03  | USB 3                 | Rear USB 3.1 Gen 2 (red) - right     |
| [x]     | SS04  | USB 3                 | Rear USB 3.1 Gen 2 (red) - left      |
| [ ]     | SS05  | USB 3.1 Type C        | Rear USB Type-C (orientation A)      |
| [x]     | SS06  | USB 3.1 Type C        | Rear USB Type-C (orientation B)      |
| [x]     | SS07  | USB 3                 | Rear USB 3.1 Gen 1 (blue) - right    |
| [ ]     | SS08  | USB 3                 | Rear USB 3.1 Gen 1 (blue) - left     |
| [x]     | SS09  | USB 3                 | Front USB 3.1 Gen 1                  |
