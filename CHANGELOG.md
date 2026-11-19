# changelog

newest on top.

## pixelos 17

### 2026-11 | `17.0-20261118-2214`

first build on linux 6.6. clean install needed when coming from the october build. [notes](releases/17/2026-11.md)

- linux 6.6 kernel (was 5.10), qualcomm walt scheduler kept for battery
- new device trees (lineageos-style sm4450 6.6 bring-up), hyperos 3 common blobs, sky os2.0.210 blobs and firmware
- zram lz4 with zstd recompression, mglru, tuned dalvik heap and lmk, settings/systemui compiled ahead of time
- faster boot, tcp bbr, lazy rcu
- 90 hz, display cutout, rounded corners and status bar height set for sky
- 3-button nav, gestures and back gesture
- volte, vowifi and 5g carrier configs
- vibration fixed, audio and wifi fixes
- built-in ota updates (settings > system > updater)
- security patch 2026-11-01

### 2026-10 | `17.0-20260930-1940`

first public build. [notes](releases/17/2026-10.md)

- pixelos 17 (android 17)
- user build, signed, selinux enforcing
- kernel 5.10.260
- fastboot and recovery install
- fingerprint fixes
- selinux fixes for radio, wifi and thermal
