# troubleshooting

find your problem below. still stuck? [report it](bug-reports.md) with the exact error.

## quick table

| problem | fix |
|---|---|
| [`fastboot devices` shows nothing](#fastboot-devices-shows-nothing) | cable, port, driver |
| `requirement board=sky not met` / wrong product | this rom is only for sky, check your phone |
| ["rebooting into fastboot" and then it hangs](#rebooting-into-fastboot-and-then-it-hangs) | update platform-tools, erase misc, try again |
| [keeps booting into recovery](#keeps-booting-into-recovery) | `fastboot erase misc` then `fastboot reboot` |
| [stuck on boot logo for 15+ minutes](#stuck-on-boot-logo) | firmware |
| [flash failed halfway](#flash-failed-halfway) | don't reboot, fix the connection, run the same command again |
| `fastboot: command not found` / not recognized | you're not in the platform-tools folder, or use `.\fastboot` on windows |
| `adb sideload` says no devices | start adb sideload on the phone first, then run the command |

## fastboot devices shows nothing

1. phone actually in fastboot mode? you should see the fastboot screen
2. plug straight into the pc, not a hub. try another port, usb 2.0 ports are often more reliable
3. try another cable. charging-only cables exist and they're the worst
4. **windows:** install the [google usb driver](https://developer.android.com/studio/run/win-usb). in device manager, if you see an unknown "android" device, update its driver and point it to the google driver
5. **linux:** try `sudo fastboot devices`. if that works, just use sudo
6. still nothing? reboot the pc, sounds dumb, fixes it surprisingly often

## "rebooting into fastboot" and then it hangs

your fastboot is too old to flash the zip in one go, so it tries another way and gets stuck.

1. update platform-tools to 35 or newer (`fastboot --version` to check)
2. get back to fastboot mode: hold **power + volume down**
3. run `fastboot erase misc`
4. run the [install command](install-fastboot.md#4-flash) again

**windows:** if it says `< waiting for any device >` after "rebooting into fastboot", the pc needs a driver for that mode too. open device manager while it's waiting and install the google usb driver for the new device that shows up.

## keeps booting into recovery

a leftover boot request from an earlier failed attempt. in fastboot mode:

```bash
fastboot erase misc
fastboot reboot
```

## stuck on boot logo

first boot takes 5 to 10 minutes, so give it 15 before worrying. after that it's almost always the firmware. see [firmware](firmware.md#stuck-on-the-boot-logo).

coming from another rom and you used `fastboot update` without `-w`? your old data is in the way. do a clean install with `-w`.

## flash failed halfway

don't panic and don't reboot. fastboot mode is untouched, so:

1. fix whatever went wrong (cable, port, sleep mode on the pc)
2. run the exact same command again. it's safe to repeat

## still broken

[report it](bug-reports.md). include the full terminal output, not just the last line.
