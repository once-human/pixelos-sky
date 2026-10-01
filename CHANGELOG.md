# changelog

newest on top. full notes for each build are in [releases/](releases/).

## 17.0-20260930-1940

first public build.

**rom**
- pixelos 17 (android 17)
- user build, signed with private keys, selinux enforcing, encrypted
- linux 5.10.260 kernel, built from source
- install with fastboot (one command) or recovery sideload

**device**
- based on topexguy's android 17 sky trees
- fingerprint hal no longer crashes when it can't find a sensor module
- goodix and fpc fingerprint folders get created at boot
- selinux fixes for dms, thermal, radio and wifi services

[release notes](releases/17.0-20260930-1940.md)
