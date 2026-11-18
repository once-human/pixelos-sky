# what works

status for the latest build, `17.0-20261118-2214` (linux 6.6). no sim in my test phone, so calls and data are untested.

| | |
|---|---|
| yes | works |
| partly | works with a catch, see notes |
| no | broken |
| ? | not tested yet, reports welcome |

## device

| feature | status | notes |
|---|---|---|
| display, touch, brightness | yes | 90 hz |
| navigation (3-button, gestures, back gesture) | yes | |
| wifi | yes | |
| hotspot | ? | |
| bluetooth | yes | |
| calls, sms | ? | |
| mobile data, 5g | ? | |
| volte, vowifi | ? | |
| dual sim | ? | |
| camera | yes | |
| fingerprint | ? | |
| speaker, mic | yes | |
| earpiece, headphones | ? | |
| vibration | yes | fixed in the november build |
| gps | yes | |
| sensors (rotation, proximity, light) | yes | |
| ir blaster | ? | |
| usb (file transfer, charging) | yes | |
| encryption | yes | |
| selinux | yes | enforcing |

benchmarks: [performance](performance.md).

## known issues

- coming from the october (5.10) build needs a clean install
- the vibration can be missed once or twice in the first minute after boot

found something else? [report it](bug-reports.md).
