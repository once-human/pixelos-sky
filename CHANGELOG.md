# changelog

newest on top.

## pixelos 17

### upcoming | november build

not released yet. built from [local_manifests](https://github.com/once-human/local_manifests) `seventeen`.

- linux 6.6 "nimbus" kernel (was 5.10), qualcomm walt scheduler kept for battery
- new device trees (lineageos-style sm4450 6.6 bring-up), hyperos 3 common blobs, sky os2.0.210 blobs and firmware
- zram lz4 with zstd recompression, mglru, tuned dalvik heap and lmk, settings/systemui compiled ahead of time
- faster boot, tcp bbr, lazy rcu
- built-in ota updates (settings > system > updater)
- clean install needed when coming from the october build

### 2026-10 | `17.0-20260930-1940`

first public build. [notes](releases/17/2026-10.md)

- pixelos 17 (android 17)
- user build, signed, selinux enforcing
- kernel 5.10.260
- fastboot and recovery install
- fingerprint fixes
- selinux fixes for radio, wifi and thermal
