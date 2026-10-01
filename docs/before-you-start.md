# before you start

read this once. it saves you from 90% of the problems people run into.

## checklist

| | what | why |
|---|---|---|
| 1 | your phone is a **sky**: redmi 12 5g, poco m6 pro 5g or redmi note 12r | this rom is built only for this phone. fastboot will refuse to flash it on anything else anyway |
| 2 | **bootloader unlocked** | no custom rom without it. use xiaomi's official mi unlock tool. the waiting period is on xiaomi's side |
| 3 | stock **hyperos 2** firmware on the phone | the rom doesn't ship firmware, it uses whatever your phone has. see [firmware](firmware.md) |
| 4 | **platform-tools 35 or newer** on your pc | older fastboot can't flash this zip in one go. check with `fastboot --version` |
| 5 | a decent usb cable, plugged straight into the pc | hubs and cheap cables cause most failed flashes |
| 6 | **backup** your stuff | a clean install wipes the phone. photos, chats, everything |
| 7 | 50%+ battery | first boot takes a while |

## which install method

| | fastboot | recovery |
|---|---|---|
| needs | a pc with platform-tools | a pc with adb + a custom recovery (orangefox) |
| steps | one command | a few taps + one command |
| recommended for | everyone, especially first install | people who already live in orangefox |
| guide | [install with fastboot](install-fastboot.md) | [install with recovery](install-recovery.md) |

both end up in the exact same rom.

## what the rom does and doesn't touch

| touched | not touched |
|---|---|
| boot, vendor_boot, dtbo, vbmeta, super (system, vendor, product etc) | bootloader, modem, firmware, persist, your imei |

so whatever happens, fastboot mode keeps working and you can always flash stock again.

## one rule

**never relock the bootloader while on a custom rom.** not with miflash "clean all and lock", not with `fastboot flashing lock`, nothing. that's how phones actually get bricked.

ready? go to [install with fastboot](install-fastboot.md).
