# firmware

the rom runs on top of the firmware your phone already has, and that needs to be **stock hyperos 2**.

| your phone is on | do this |
|---|---|
| stock hyperos 2 | nothing, go [install](install-fastboot.md) |
| stock hyperos 1 or miui 14 | update to hyperos 2 first (system update, or flash it below), boot it once, then install |
| another custom rom and you're not sure | flash stock hyperos 2 first |

tested on **OS2.0.210** (global). other hyperos 2 versions should work too. if one doesn't, [report it](bug-reports.md).

any region works: global, india, china, eea.

## flash stock hyperos 2

1. download the official **fastboot rom** (`.tgz`) for your phone. tested: **OS2.0.210.0.VMWMIXM** (global). [xiaomifirmwareupdater.com](https://xiaomifirmwareupdater.com) lists them with links to xiaomi's servers
2. extract it
3. phone in fastboot mode, plugged in
4. flash with **miflash** using **"clean all"**, or run the script inside the extracted folder (`flash_all.bat` on windows, `flash_all.sh` on linux and mac)
5. boot it once, then do the [clean install](install-fastboot.md)

**never pick "clean all and lock".**

## stuck on the boot logo

rom not booting after 15 minutes? almost always firmware.

1. hold **power + volume down** to get back to fastboot
2. flash stock hyperos 2 as above
3. boot it once, then install the rom again
