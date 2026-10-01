# updating

new build out and you're already on this rom? you can update without losing anything. every build is signed with the same keys, so updates go straight over the top.

## pick one

| method | command / steps | data |
|---|---|---|
| **fastboot** | phone in fastboot mode, then `fastboot update PixelOS_sky-<new version>-fastboot.zip` (no `-w`!) | kept |
| **recovery** | boot recovery > adb sideload > `adb sideload PixelOS_sky-<new version>.zip`, **no format data** | kept |

that's it. the first boot after an update is a bit slower than usual.

## when to do a clean install instead

| situation | do this |
|---|---|
| the release notes say "clean flash required" | clean install ([fastboot](install-fastboot.md) with `-w`, or format data in recovery) |
| coming from a different rom, even another pixelos build | clean install |
| something's broken after the update | try a clean install before reporting it |

## don't miss new builds

on the repo page hit **watch > custom > releases**. github will ping you when a new build drops.
