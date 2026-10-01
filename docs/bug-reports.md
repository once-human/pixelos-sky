# reporting bugs

a report with logs gets fixed. "camera not working pls fix" doesn't.

## before reporting

| | |
|---|---|
| not in [known issues](status.md#known-issues) | |
| not already [reported](https://github.com/once-human/pixelos-sky/issues) | if it is, add your info there |
| clean install | dirty flashes from other roms cause fake bugs |
| no magisk modules or mods | try without them first |

## grab logs

you need adb on your pc ([platform-tools](install-fastboot.md#1-get-platform-tools-35-or-newer)).

1. settings > about phone > tap **build number** 7 times
2. settings > system > developer options > turn on **usb debugging**
3. plug in, allow it on the phone
4. make the bug happen, then right away:

```bash
adb logcat -b all -d > logcat.txt
```

crashes, random reboots or anything weird? a full bug report is better (takes a minute or two):

```bash
adb bugreport bugreport.zip
```

## what to include

| | example |
|---|---|
| build | settings > about phone > android version > build number |
| phone | poco m6 pro 5g |
| firmware before install | OS2.0.210 global |
| install method | fastboot, clean install |
| what happens | camera closes when switching to video |
| steps | open camera, tap video, crash |
| logs | `logcat.txt` or `bugreport.zip` |

## where

[open an issue](https://github.com/once-human/pixelos-sky/issues/new/choose). the form asks for all of the above.

a full bugreport can include personal stuff (wifi names, account names). check it before posting publicly.
