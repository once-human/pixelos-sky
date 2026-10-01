# PixelOS for Xiaomi sky

Unofficial **PixelOS** builds for the **Redmi 12 5G / POCO M6 Pro 5G / Redmi Note 12R** (`sky`).

| | |
|---|---|
| **Latest** | PixelOS 17 (Android 17), build `20260930-1940`: see [Releases](../../releases) |
| **Build type** | user, signed (release-keys), SELinux enforcing, encrypted |
| **Kernel** | Linux 5.10.260, built from source |
| **Firmware** | Not included: needs stock HyperOS 2 firmware (OS2.0.210 tested) |
| **Install** | Fastboot (`fastboot -w update <zip>`) or recovery sideload, tested with OrangeFox ([full guide](https://github.com/once-human/local_manifests/blob/seventeen/docs/INSTALL.md)) |
| **Source** | [local_manifests](https://github.com/once-human/local_manifests) · [device tree](https://github.com/once-human/device_xiaomi_sky/tree/seventeen) · [hardware_xiaomi](https://github.com/once-human/android_hardware_xiaomi/tree/seventeen) |

Downloads are hosted on SourceForge (GitHub limits release files to 2 GB); every release here links to them with checksums.

## Credits

- [TopexGuy](https://github.com/topexguy): sky Android 17 device, vendor and kernel trees, Signify
- Lostark13: sky device tree, original author
- mo_faza, Mr_Agness: sky bring-up
- [anonytry](https://github.com/anonytry): hardware/xiaomi, Dolby, vibrator
- [jendermine](https://github.com/jendermine): guidance, former PixelOS sky maintainer
- [PixelOS](https://github.com/PixelOS-AOSP) and [LineageOS](https://github.com/LineageOS) teams

Maintainer: Onkar Yaglewad ([once-human](https://github.com/once-human))
