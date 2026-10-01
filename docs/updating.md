# updating

new build out and you're already on this rom? update without losing anything.

| method | how | data |
|---|---|---|
| **fastboot** | fastboot mode, then `fastboot update PixelOS_sky-<new version>-fastboot.zip` (no `-w`) | kept |
| **recovery** | recovery > adb sideload > `adb sideload PixelOS_sky-<new version>.zip` (no format data) | kept |

first boot after an update is a bit slower than usual.

## clean install instead when

| | |
|---|---|
| the release notes say "clean flash required" | clean install |
| coming from a different rom, even another pixelos build | clean install |
| something's broken after updating | try a clean install before reporting |

clean install = [fastboot](install-fastboot.md) with `-w`, or format data in [recovery](install-recovery.md).

## get notified

on the repo page: **watch > custom > releases**. github pings you when a new build drops.
