# install with fastboot

the recommended way. one command, no scripts, no extracting. works the same on windows, linux and mac.

> haven't read [before you start](before-you-start.md)? do that first, it's quick.

## 1. get platform-tools (35 or newer)

| os | how |
|---|---|
| **windows** | download "sdk platform-tools for windows" from [developer.android.com](https://developer.android.com/tools/releases/platform-tools), extract it somewhere easy like `C:\platform-tools` |
| **linux (arch)** | `sudo pacman -S android-tools` |
| **linux (debian / ubuntu / others)** | distro packages are often too old. grab the linux zip from [developer.android.com](https://developer.android.com/tools/releases/platform-tools) instead |
| **mac** | `brew install --cask android-platform-tools` |

check it:

```bash
fastboot --version
```

you want to see `35.0.0` or higher.

**windows only:** if your pc doesn't see the phone later, install the [google usb driver](https://developer.android.com/studio/run/win-usb).

## 2. download the rom

grab `PixelOS_sky-<version>-fastboot.zip` from the [latest release](https://github.com/once-human/pixelos-sky/releases/latest).

**don't extract it.** fastboot reads the zip directly.

optional but smart: check the download isn't corrupted. get `SHA256SUMS` from the same release and compare:

| os | command |
|---|---|
| linux | `sha256sum -c SHA256SUMS --ignore-missing` |
| mac | `shasum -a 256 PixelOS_sky-*-fastboot.zip` |
| windows | `certutil -hashfile PixelOS_sky-<version>-fastboot.zip SHA256` |

the hash should match the line in `SHA256SUMS`.

## 3. phone into fastboot mode

1. power the phone off
2. hold **power + volume down** until you see the fastboot screen
3. plug it into the pc

<!-- ![fastboot mode](images/fastboot-mode.jpg) -->

check the pc sees it:

```bash
fastboot devices
```

you should get one line with a serial number. nothing? see [troubleshooting](troubleshooting.md#fastboot-devices-shows-nothing).

**linux:** if it only works with sudo, use `sudo fastboot` for every command below.

## 4. flash

open a terminal in the folder where the zip is, then:

| situation | command |
|---|---|
| **clean install** (coming from stock or another rom, wipes data) | `fastboot -w update PixelOS_sky-<version>-fastboot.zip` |
| **update** (already on this rom, keeps data) | `fastboot update PixelOS_sky-<version>-fastboot.zip` |

replace `<version>` with the real file name, for example:

```bash
fastboot -w update PixelOS_sky-17.0-20260930-1940-fastboot.zip
```

**windows:** in powershell inside the platform-tools folder, use `.\fastboot` instead of `fastboot`, and either put the zip in that same folder or give the full path to it.

## 5. what you'll see

roughly this, in order:

```
Sending 'boot_a' ...
Writing 'boot_a' ...
...
Sending sparse 'super' 1/x ...
Writing 'super' ...
...
Erasing 'userdata' ...
Rebooting ...
```

(the slot letter can be `_a` or `_b`, both are fine.)

<!-- ![flashing in terminal](images/fastboot-flashing.png) -->

the phone reboots by itself when it's done. **first boot takes 5 to 10 minutes**, that's normal. leave it alone.

## done

set it up and enjoy. if something looks off, check [what works](status.md) and [troubleshooting](troubleshooting.md) before reporting.

| | |
|---|---|
| stuck on boot logo for more than 15 minutes | [firmware](firmware.md) |
| keeps booting into recovery | [troubleshooting](troubleshooting.md#keeps-booting-into-recovery) |
| any other error | [troubleshooting](troubleshooting.md) |
