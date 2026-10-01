<div align="center">

# pixelos for sky

unofficial pixelos for the **redmi 12 5g**, **poco m6 pro 5g** and **redmi note 12r**

[download](https://github.com/once-human/pixelos-sky/releases/latest) &nbsp;|&nbsp;
[install guide](docs/install-fastboot.md) &nbsp;|&nbsp;
[what works](docs/status.md) &nbsp;|&nbsp;
[faq](docs/faq.md) &nbsp;|&nbsp;
[report a bug](docs/bug-reports.md)

</div>

---

## latest build

| | |
|---|---|
| **rom** | pixelos 17 (android 17) |
| **build** | `17.0-20260930-1940` |
| **devices** | redmi 12 5g, poco m6 pro 5g, redmi note 12r (`sky`), any region |
| **type** | user build, signed, selinux enforcing |
| **kernel** | 5.10.260 |
| **firmware** | stock hyperos 2 ([details](docs/firmware.md)) |
| **install** | fastboot or recovery |
| **google apps** | included |
| **benchmarks** | geekbench 7: 810 / 2093, antutu 12: 685k ([details](docs/performance.md)) |
| **maintainer** | [once-human](https://github.com/once-human) |

## screenshots

<!-- gallery: upload images to screenshots/17/, then remove the two comment marker lines around the block below and the "coming soon" line -->

<!--
<p align="center">
  <img src="screenshots/17/01-home.png" width="200">
  <img src="screenshots/17/02-lockscreen.png" width="200">
  <img src="screenshots/17/03-quick-settings.png" width="200">
  <img src="screenshots/17/04-settings.png" width="200">
</p>
<p align="center">
  <img src="screenshots/17/05-about-phone.png" width="200">
  <img src="screenshots/17/06-wallpaper-styles.png" width="200">
  <img src="screenshots/17/07-camera.png" width="200">
  <img src="screenshots/17/08-recents.png" width="200">
</p>
-->

coming soon

## quick install

flashed roms before? this is all you need. first time? follow the [full guide](docs/install-fastboot.md).

1. bootloader unlocked, stock **hyperos 2** on the phone
2. **platform-tools 35 or newer** on your pc
3. phone in fastboot mode (power + volume down), plugged in
4. don't extract the zip, just run:

```bash
fastboot -w update PixelOS_sky-17.0-20260930-1940-fastboot.zip
```

reboots by itself. first boot takes 5 to 10 minutes.

recovery instead? [sideload guide](docs/install-recovery.md). already on this rom? [updating](docs/updating.md).

## docs

| | page | |
|---|---|---|
| **start** | [before you start](docs/before-you-start.md) | what you need |
| | [unlock the bootloader](docs/unlock-bootloader.md) | if it's still locked |
| | [firmware](docs/firmware.md) | which hyperos version you need |
| | [downloads](docs/downloads.md) | which file to grab and where |
| **install** | [fastboot](docs/install-fastboot.md) | recommended |
| | [recovery](docs/install-recovery.md) | orangefox sideload |
| | [updating](docs/updating.md) | new build, keep your data |
| **help** | [what works](docs/status.md) | status and known issues |
| | [troubleshooting](docs/troubleshooting.md) | stuck somewhere |
| | [faq](docs/faq.md) | root, updates, banking apps |
| | [performance](docs/performance.md) | benchmarks, build by build |
| | [reporting bugs](docs/bug-reports.md) | logs and what to include |
| **other** | [back to stock](docs/back-to-stock.md) | going back to hyperos |
| | [building](docs/building.md) | build it yourself |

## repo layout

```
pixelos-sky/
├── docs/              all guides
├── releases/17/       release notes, one file per monthly build
├── screenshots/17/    screenshots and benchmarks of pixelos 17
├── CHANGELOG.md       what changed, build by build
└── CREDITS.md         the people behind this rom
```

## source

| | |
|---|---|
| manifest | [once-human/local_manifests](https://github.com/once-human/local_manifests) |
| device tree | [once-human/device_xiaomi_sky](https://github.com/once-human/device_xiaomi_sky/tree/seventeen) |
| hardware | [once-human/android_hardware_xiaomi](https://github.com/once-human/android_hardware_xiaomi/tree/seventeen) |
| vendor | [topexguy/vendor_xiaomi_sky](https://github.com/topexguy/vendor_xiaomi_sky) |
| kernel | [topexguy/kernel_xiaomi_sky](https://github.com/topexguy/kernel_xiaomi_sky) |

## credits

huge thanks to [topexguy](https://github.com/topexguy), lostark13, mo_faza, mr_agness, [anonytry](https://github.com/anonytry), [jendermine](https://github.com/jendermine) and the pixelos and lineageos teams. who did what: [CREDITS.md](CREDITS.md)

## heads up

flashing a custom rom is your call. read [before you start](docs/before-you-start.md) once and you'll be fine.

**never relock your bootloader while on this rom.**
