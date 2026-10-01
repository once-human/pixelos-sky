# faq

## general

**is this official pixelos?**
no, unofficial. for help, ask [here](bug-reports.md), not the pixelos team.

**which phones?**
redmi 12 5g, poco m6 pro 5g and redmi note 12r, any region. same phone inside (`sky`).

**redmi 12 4g / poco m6 pro 4g / redmi note 12?**
no, different phones.

**google apps?**
included, nothing extra to flash.

**daily driver ready?**
check [what works](status.md). if what you need says yes, go for it.

## install

**fastboot or recovery?**
fastboot if unsure. [comparison](before-you-start.md#fastboot-or-recovery).

**extract the zip?**
no. flash it as is.

**need to flash firmware?**
only if your phone isn't on stock hyperos 2. [firmware](firmware.md).

**can this brick my phone?**
follow the guide and no. the one thing that really bricks a xiaomi is relocking the bootloader on a custom rom, so don't.

## using the rom

**updates inside the rom?**
no. new builds land on the [releases page](https://github.com/once-human/pixelos-sky/releases). hit **watch > custom > releases** on this repo to get pinged, then follow [updating](updating.md).

**about phone shows a different build number than the zip?**
that's normal. the zip `17.0-20260930-1940` shows up as `PixelOS_sky-17.0-20261001-0646` in settings > about phone > android version. same build.

**update without losing data?**
yes, [updating](updating.md).

**root?**
not included. magisk works the usual way: take `boot.img` out of the fastboot zip, patch it in the magisk app, then `fastboot flash boot magisk_patched.img`. keep the original `boot.img` to undo it. not something i test, so you're on your own there.

**banking apps / play integrity?**
custom roms can't pass strong integrity, that needs a locked bootloader. if a specific app refuses to work, [open an issue](bug-reports.md) with its name.

## other

**build it myself?**
yep, [building](building.md).

**mirror or repost?**
please share a link to this repo instead, so people always get the latest build and the guides.

**how to say thanks?**
star the repo, share it with other sky users, send good bug reports. and thank the people in [credits](../CREDITS.md).
