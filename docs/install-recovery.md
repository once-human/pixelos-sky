# install with recovery

for orangefox users. no custom recovery? use [fastboot](install-fastboot.md), it's easier.

tested with orangefox ([altafyafai's build](https://github.com/AltafYafai/Action-OFRP-Builder/releases/tag/25638699166)).

> first time? read [before you start](before-you-start.md).

## what you need

| | |
|---|---|
| orangefox on the phone | linked above |
| adb on your pc | part of platform-tools, see [fastboot guide step 1](install-fastboot.md#1-get-platform-tools-35-or-newer) |
| the recovery zip | `PixelOS_sky-<version>.zip` (the one **without** `-fastboot`) from the [latest release](https://github.com/once-human/pixelos-sky/releases/latest). the `-fastboot` zip won't flash in recovery |

## steps

1. boot into recovery: phone off, hold **power + volume up**
2. **clean install only:** wipe > **format data**, type `yes`
3. open **adb sideload** and start it

<!-- ![orangefox sideload](images/orangefox-sideload.jpg) -->

4. on your pc, in the folder with the zip:

```bash
adb sideload PixelOS_sky-<version>.zip
```

5. wait till the phone says it's done. the pc side sometimes stops early (like 47%), that's fine
6. reboot to system. first boot takes **5 to 10 minutes**

## updating

already on this rom? same steps, **skip format data**. more in [updating](updating.md).

## orangefox after install

the rom comes with its own recovery, so orangefox may be replaced after flashing. want it back? flash it again the way you did before.
