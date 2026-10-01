# before you start

read this once. saves you from most of the problems people run into.

## checklist

| | what | |
|---|---|---|
| 1 | your phone is a redmi 12 5g, poco m6 pro 5g or redmi note 12r | nothing else, not the 4g versions |
| 2 | bootloader unlocked | [how to unlock](unlock-bootloader.md) |
| 3 | stock hyperos 2 on the phone | [firmware](firmware.md) |
| 4 | platform-tools 35 or newer on your pc | `fastboot --version` to check |
| 5 | a good usb cable, straight into the pc | hubs and cheap cables cause most failed flashes |
| 6 | your stuff backed up | a clean install wipes the phone |
| 7 | 50%+ battery | |

## fastboot or recovery

| | fastboot | recovery |
|---|---|---|
| needs | a pc | a pc + orangefox on the phone |
| steps | one command | a few taps + one command |
| for | everyone | people already using orangefox |
| guide | [install with fastboot](install-fastboot.md) | [install with recovery](install-recovery.md) |

same rom either way.

## one rule

**never relock the bootloader while on a custom rom.** not with miflash "clean all and lock", not with `fastboot flashing lock`. that's how phones actually get bricked.

ready? grab the [downloads](downloads.md).
