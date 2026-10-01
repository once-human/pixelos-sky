# install with recovery

for people who already use orangefox. if you don't have a custom recovery, just use [fastboot](install-fastboot.md), it's easier.

tested with orangefox ([altafyafai's ofrp build](https://github.com/AltafYafai/Action-OFRP-Builder/releases/tag/25638699166)).

> haven't read [before you start](before-you-start.md)? do that first.

## what you need

| | |
|---|---|
| a custom recovery on the phone | orangefox, linked above |
| adb on your pc | comes with platform-tools, see [install with fastboot](install-fastboot.md#1-get-platform-tools-35-or-newer) step 1 |
| the recovery zip | `PixelOS_sky-<version>.zip` (the one **without** `-fastboot` in the name) from the [latest release](https://github.com/once-human/pixelos-sky/releases/latest) |

## steps

1. boot into recovery (phone off, hold **power + volume up**)
2. **clean install only:** wipe > **format data** (type `yes` when it asks). coming from stock or another rom, you need this
3. go to **adb sideload** and start it

<!-- ![orangefox sideload](images/orangefox-sideload.jpg) -->

4. on your pc, in the folder with the zip:

```bash
adb sideload PixelOS_sky-<version>.zip
```

5. wait for it to finish. the pc side sometimes stops early (like at 47%), that's normal as long as the phone says it's done
6. reboot to system. first boot takes **5 to 10 minutes**

## updating with recovery

already on this rom? same steps but **skip format data**. your stuff stays. more in [updating](updating.md).

## good to know

flashing the rom also flashes its own recovery (on this phone the recovery lives inside the boot images). so after the first boot your orangefox is probably gone. if you want it back, flash it again the way you did before.
