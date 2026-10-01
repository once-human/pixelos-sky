# install with fastboot

the recommended way. one command, works the same on windows, linux and mac.

> first time? read [before you start](before-you-start.md).

## 1. get platform-tools (35 or newer)

| os | how |
|---|---|
| **windows** | download "sdk platform-tools for windows" from [developer.android.com](https://developer.android.com/tools/releases/platform-tools), extract it somewhere easy like `C:\platform-tools` |
| **arch linux** | `sudo pacman -S android-tools` |
| **other linux** | grab the linux zip from [developer.android.com](https://developer.android.com/tools/releases/platform-tools), distro packages are often too old |
| **mac** | `brew install --cask android-platform-tools` |

check it:

```bash
fastboot --version
```

you want `35.0.0` or higher.

**windows:** if the pc doesn't see the phone later, install the [google usb driver](https://developer.android.com/studio/run/win-usb).

## 2. download

grab `PixelOS_sky-<version>-fastboot.zip` from the [latest release](https://github.com/once-human/pixelos-sky/releases/latest). **don't extract it.**

want to make sure it downloaded fine? [check the checksum](downloads.md#check-your-download).

## 3. fastboot mode

1. power the phone off
2. hold **power + volume down** until the fastboot screen shows up
3. plug it into the pc

<!-- ![fastboot mode](images/fastboot-mode.jpg) -->

check the pc sees it:

```bash
fastboot devices
```

one line with a serial number = good. nothing? [troubleshooting](troubleshooting.md#fastboot-devices-shows-nothing).

**linux:** if it only works with sudo, use `sudo fastboot` for everything below.

## 4. flash

open a terminal in the folder with the zip:

| | command |
|---|---|
| **clean install** (from stock or another rom, wipes data) | `fastboot -w update PixelOS_sky-<version>-fastboot.zip` |
| **update** (already on this rom, keeps data) | `fastboot update PixelOS_sky-<version>-fastboot.zip` |

with the real file name, for example:

```bash
fastboot -w update PixelOS_sky-17.0-20260930-1940-fastboot.zip
```

**windows:** in powershell inside the platform-tools folder, use `.\fastboot` instead of `fastboot`, and put the zip in that same folder.

## 5. wait

you'll see something like:

```
Sending 'boot_a' ...
...
Sending sparse 'super' 1/x ...
Writing 'super' ...
...
Erasing 'userdata' ...
Rebooting ...
```

<!-- ![flashing](images/fastboot-flashing.png) -->

the phone reboots by itself. **first boot takes 5 to 10 minutes**, leave it alone.

## done

| | |
|---|---|
| stuck on boot logo 15+ minutes | [firmware](firmware.md#stuck-on-the-boot-logo) |
| keeps booting into recovery | [troubleshooting](troubleshooting.md#keeps-booting-into-recovery) |
| anything else | [troubleshooting](troubleshooting.md) |
