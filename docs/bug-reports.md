# reporting bugs

a bug report with logs gets fixed. "camera not working pls fix" doesn't. here's how to make a good one.

## before reporting

| check | |
|---|---|
| it's not already in [known issues](status.md#known-issues) | |
| it's not already [reported](https://github.com/once-human/pixelos-sky/issues) | if it is, add your info there instead |
| you did a clean install | dirty flashes from other roms cause weird bugs that aren't real bugs |
| no magisk modules or mods | if you use them, try without first |

## grab logs

you need adb on your pc ([platform-tools](install-fastboot.md#1-get-platform-tools-35-or-newer)).

1. on the phone: settings > about phone > tap **build number** 7 times
2. settings > system > developer options > turn on **usb debugging**
3. plug in, accept the prompt on the phone
4. make the bug happen, then right away run:

```bash
adb logcat -b all -d > logcat.txt
```

for crashes, random reboots or anything weird, a full bug report is better (takes a minute or two):

```bash
adb bugreport bugreport.zip
```

## what to include

| | example |
|---|---|
| build | `17.0-20260930-1940` |
| phone | redmi 12 5g / poco m6 pro 5g / redmi note 12r |
| firmware before install | hyperos OS2.0.210 global |
| install method | fastboot / recovery, clean / update |
| what happens | camera app closes when switching to video |
| steps to reproduce | open camera, tap video, crash |
| logs | `logcat.txt` or `bugreport.zip` attached |

## where

[open an issue](https://github.com/once-human/pixelos-sky/issues/new/choose). the bug template asks for all of the above, just fill it in.

**heads up:** a full bugreport can include personal stuff (wifi names, app list, account names). skim it before posting publicly, or say so in the issue and send it privately.
