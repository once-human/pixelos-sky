# back to stock

leaving is easy and nothing to be scared of. the rom never touched your bootloader or firmware.

1. back up anything you want to keep, this wipes the phone
2. download the official hyperos **fastboot rom** for your phone (see [firmware](firmware.md#how-to-flash-stock-hyperos-2))
3. phone into fastboot mode (**power + volume down**), plugged in
4. flash with miflash using **"clean all"**, or run `flash_all.bat` / `flash_all.sh` from the extracted rom
5. first boot takes a few minutes

## about relocking

| | |
|---|---|
| want to stay unlocked | nothing else to do |
| want to relock | only after stock is installed **and boots fine**. then you can relock. miflash's "clean all and lock" does flash + lock in one go, use it only with an official stock rom, never while a custom rom is on the phone |

if you're not sure, just stay unlocked. an unlocked bootloader on stock is perfectly fine.
