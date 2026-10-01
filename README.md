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
| **devices** | redmi 12 5g, poco m6 pro 5g, redmi note 12r (codename `sky`), any region |
| **build type** | user build, signed with private keys, selinux enforcing, encrypted |
| **kernel** | linux 5.10.260, built from source |
| **firmware** | not included, you need stock hyperos 2 firmware ([details](docs/firmware.md)) |
| **install** | fastboot (one command) or recovery sideload |
| **google apps** | included, it's pixelos |
| **maintainer** | [once-human](https://github.com/once-human) |

downloads live on sourceforge because github caps release files at 2 gb. every [release](https://github.com/once-human/pixelos-sky/releases) here links straight to them.

## screenshots

<!-- to show the gallery: add the images to screenshots/17/ (names in screenshots/README.md), then delete the two comment marker lines around the gallery below, and the "coming soon" line -->

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
  <img src="screenshots/17/08-geekbench.png" width="200">
</p>

-->

coming soon

## quick install

if you've flashed roms before, this is all you need. first time? read the [full guide](docs/install-fastboot.md), it's short.

1. bootloader unlocked, stock **hyperos 2** firmware on the phone (OS2.0.210 tested)
2. google **platform-tools 35 or newer** on your pc
3. phone in fastboot mode (power + volume down), plugged in
4. don't extract the zip, just run:

```bash
fastboot -w update PixelOS_sky-17.0-20260930-1940-fastboot.zip
```

it flashes everything in one go and reboots by itself. first boot takes 5 to 10 minutes.

prefer recovery? [sideload guide](docs/install-recovery.md). already on this rom? [updating](docs/updating.md).

## docs

| page | what's in it |
|---|---|
| [before you start](docs/before-you-start.md) | what you need, read this once |
| [install with fastboot](docs/install-fastboot.md) | recommended way, step by step for windows, linux and mac |
| [install with recovery](docs/install-recovery.md) | sideload from orangefox |
| [updating](docs/updating.md) | new build over an old one, keeps your data |
| [firmware](docs/firmware.md) | which firmware you need and how to get it |
| [back to stock](docs/back-to-stock.md) | going back to hyperos |
| [what works](docs/status.md) | device status and known issues |
| [troubleshooting](docs/troubleshooting.md) | stuck somewhere? check here |
| [faq](docs/faq.md) | root, ota, banking apps and the usual questions |
| [reporting bugs](docs/bug-reports.md) | how to grab logs so bugs actually get fixed |
| [building](docs/building.md) | build it yourself from source |

## repo layout

```
pixelos-sky/
├── README.md            you are here
├── CHANGELOG.md         what changed in every build
├── CREDITS.md           everyone who made this possible
├── docs/                guides (install, update, firmware, faq...)
│   └── images/          pictures used inside the guides
├── releases/            release notes for every build
├── screenshots/         rom screenshots, one folder per version
└── .github/             issue templates
```

## source

| part | repo |
|---|---|
| manifest + build script | [once-human/local_manifests](https://github.com/once-human/local_manifests) |
| device tree | [once-human/device_xiaomi_sky](https://github.com/once-human/device_xiaomi_sky/tree/seventeen) |
| hardware/xiaomi | [once-human/android_hardware_xiaomi](https://github.com/once-human/android_hardware_xiaomi/tree/seventeen) |
| vendor | [topexguy/vendor_xiaomi_sky](https://github.com/topexguy/vendor_xiaomi_sky) |
| kernel | [topexguy/kernel_xiaomi_sky](https://github.com/topexguy/kernel_xiaomi_sky) |
| rom | [pixelos-aosp](https://github.com/PixelOS-AOSP) |

## credits

this rom stands on a lot of other people's work. huge thanks to [topexguy](https://github.com/topexguy), lostark13, mo_faza, mr_agness, [anonytry](https://github.com/anonytry), [jendermine](https://github.com/jendermine) and the pixelos and lineageos teams.

full list with who did what: [CREDITS.md](CREDITS.md)

## heads up

flashing a custom rom is your call and your responsibility. that said, this rom never touches your bootloader or firmware, so fastboot mode always keeps working and you can always [go back to stock](docs/back-to-stock.md).

**never relock your bootloader while on this rom.** that's the one thing that can actually brick your phone.
