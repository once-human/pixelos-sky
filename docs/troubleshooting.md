# troubleshooting

still stuck after this? [report it](bug-reports.md) with the exact error.

| problem | fix |
|---|---|
| [`fastboot devices` shows nothing](#fastboot-devices-shows-nothing) | cable, port, driver |
| `requirement board=sky not met` | wrong phone, this rom is only for sky |
| ["rebooting into fastboot" then it hangs](#rebooting-into-fastboot-then-it-hangs) | update platform-tools |
| [keeps booting into recovery](#keeps-booting-into-recovery) | `fastboot erase misc` |
| [stuck on boot logo 15+ minutes](#stuck-on-boot-logo) | firmware or old data |
| [flash failed halfway](#flash-failed-halfway) | run the same command again |
| `fastboot` not recognized (windows) | use `.\fastboot` inside the platform-tools folder |
| `adb sideload` says no devices | start adb sideload on the phone first |

## fastboot devices shows nothing

1. phone actually on the fastboot screen?
2. plug straight into the pc, no hub. try another port
3. try another cable, some only charge
4. **windows:** install the [google usb driver](https://developer.android.com/studio/run/win-usb). in device manager, update the unknown "android" device with it
5. **linux:** try `sudo fastboot devices`
6. reboot the pc. sounds dumb, works surprisingly often

## "rebooting into fastboot" then it hangs

your platform-tools are too old.

1. update platform-tools to 35 or newer
2. get back to fastboot mode: hold **power + volume down**
3. `fastboot erase misc`
4. run the [install command](install-fastboot.md#4-flash) again

## keeps booting into recovery

in fastboot mode:

```bash
fastboot erase misc
fastboot reboot
```

## stuck on boot logo

first boot takes 5 to 10 minutes, give it 15.

| | |
|---|---|
| came from another rom without `-w` | do a clean install with `-w` |
| clean install and still stuck | [firmware](firmware.md#stuck-on-the-boot-logo) |

## flash failed halfway

don't reboot.

1. fix the connection (cable, port, pc going to sleep)
2. run the exact same command again, it's safe to repeat
