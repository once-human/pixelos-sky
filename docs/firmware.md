# firmware

## the short version

the rom doesn't come with firmware. it uses whatever firmware your phone already has, and that needs to be **stock hyperos 2** (android 15 based).

| your phone is on | what to do |
|---|---|
| stock hyperos 2 | nothing, go [install](install-fastboot.md) |
| stock hyperos 1 or miui 14 | update to hyperos 2 first (system update, or flash it, see below), boot it once, then install |
| another custom rom and you don't know the firmware | flash stock hyperos 2 first to be safe |

tested on **OS2.0.210** (global). other hyperos 2 versions should work too. if one doesn't, [tell me](bug-reports.md) which.

## why no firmware in the zip

firmware is the risky part of any flash. by not shipping it, the rom can't mess up your modem, bootloader or anything low level. it's also why one zip works for every region: global, india, china, eea, whatever.

## how to flash stock hyperos 2

1. download the official **fastboot rom** (`.tgz`) for your phone. tested: **OS2.0.210.0.VMWMIXM** (global). [xiaomifirmwareupdater.com](https://xiaomifirmwareupdater.com) lists them with links to xiaomi's own servers
2. extract it
3. phone in fastboot mode, plugged in
4. flash it with **miflash** (windows) using **"clean all"**, or run the `flash_all` script inside the extracted folder (`flash_all.bat` on windows, `flash_all.sh` on linux and mac)
5. boot it once, finish setup quickly, then come back and do the [clean install](install-fastboot.md)

**never pick "clean all and lock"** in miflash. locking the bootloader on anything but a fully stock phone is how you brick it.

xiaomi's own flash scripts check anti rollback for you and refuse versions that would trip it. don't edit them to skip that check.

## stuck on the boot logo?

if the rom doesn't boot after 15 minutes, it's almost always firmware:

1. hold **power + volume down** to get back to fastboot (always works, the rom never touches the bootloader)
2. flash stock hyperos 2 as above
3. boot it once, then install the rom again
