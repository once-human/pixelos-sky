# faq

## general

**is this official pixelos?**
no, it's unofficial. built from pixelos source, but not by the pixelos team. please don't ask them for support on it, ask [here](bug-reports.md).

**which phones?**
redmi 12 5g, poco m6 pro 5g and redmi note 12r. all the same phone inside (codename `sky`), any region.

**does it work on the redmi 12 4g / redmi note 12 / poco m6 pro 4g?**
no. different phones, different codenames. fastboot will refuse to flash it anyway.

**are google apps included?**
yes. pixelos ships with them, nothing extra to flash.

**is it stable enough for daily use?**
check [what works](status.md). if the stuff you need is on the "yes" list, go for it.

## install

**fastboot or recovery?**
fastboot if you're unsure. one command and no custom recovery needed. both give you the same rom. see [before you start](before-you-start.md#which-install-method).

**do i need to extract the zip?**
no. `fastboot update` reads the zip as is. extracting it and flashing images by hand is how people break things.

**do i need to flash firmware?**
only if your phone isn't on stock hyperos 2 right now. see [firmware](firmware.md).

**will this brick my phone?**
the rom never touches the bootloader or firmware, so fastboot mode always keeps working and you can always [go back to stock](back-to-stock.md). the one real way to brick a xiaomi is relocking the bootloader on a custom rom. don't do that.

**i'm on windows and `fastboot` isn't recognized**
open powershell inside the platform-tools folder and use `.\fastboot`.

## using the rom

**will i get ota updates inside the rom?**
no, the built-in updater is for official builds. new builds get posted on the [releases page](https://github.com/once-human/pixelos-sky/releases). hit **watch > custom > releases** on this repo and github tells you when one drops. then follow [updating](updating.md).

**can i update without losing my data?**
yes, see [updating](updating.md).

**root?**
not included. magisk should work the usual way: the fastboot zip has `boot.img` inside, open the zip, take that file out, patch it in the magisk app and flash it with `fastboot flash boot magisk_patched.img`. root isn't something i test, so you're on your own there, and keep the original `boot.img` around in case you want to undo it.

**banking apps / play integrity?**
it's a signed user build with selinux enforcing, which is about as clean as a custom rom gets. strong integrity needs a locked bootloader though, so no custom rom passes that. if a specific app refuses to work, [open an issue](bug-reports.md) with the app name.

**is there a xiaomi settings app (thermal profiles, etc)?**
not in this build.

## other

**can i build it myself?**
yep, everything's open. see [building](building.md).

**can i mirror or repost the rom?**
please link to this repo or the [releases page](https://github.com/once-human/pixelos-sky/releases) instead of reuploading. that way people always get the latest build, the checksums and the guides.

**how do i say thanks?**
star the repo, share it with other sky users, and send good bug reports. and thank the people in [credits](../CREDITS.md), most of the hard work is theirs.
