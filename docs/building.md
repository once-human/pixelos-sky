# building

everything needed to build this rom is public. the local manifest pins every device repo to the exact commit the release was built from.

## what you need

| | |
|---|---|
| os | linux (ubuntu 22.04+ or similar) |
| disk | ~400 gb free, ssd strongly recommended |
| ram | 32 gb+ (or 16 gb with a big swap, slow) |
| time | a few hours for the first build |

standard aosp build dependencies apply. if you've built any android rom before, you're set.

## build

```bash
mkdir pixelos && cd pixelos
repo init -u https://github.com/PixelOS-AOSP/android_manifest.git -b seventeen --git-lfs
mkdir -p .repo/local_manifests
curl -fLo .repo/local_manifests/sky.xml https://raw.githubusercontent.com/once-human/local_manifests/seventeen/sky.xml
repo sync -c -j"$(nproc)" --force-sync --no-clone-bundle --no-tags

source build/envsetup.sh
lunch custom_sky-cp2a-user
m pixelos
```

## sources

| path | repo |
|---|---|
| `device/xiaomi/sky` | [once-human/device_xiaomi_sky](https://github.com/once-human/device_xiaomi_sky/tree/seventeen) |
| `vendor/xiaomi/sky` | [topexguy/vendor_xiaomi_sky](https://github.com/topexguy/vendor_xiaomi_sky) |
| `kernel/xiaomi/sky` | [topexguy/kernel_xiaomi_sky](https://github.com/topexguy/kernel_xiaomi_sky) |
| `kernel/xiaomi/sm8450-modules` | [topexguy/kernel_xiaomi_sm8450-modules](https://github.com/topexguy/kernel_xiaomi_sm8450-modules) |
| `hardware/xiaomi` | [once-human/android_hardware_xiaomi](https://github.com/once-human/android_hardware_xiaomi/tree/seventeen) |
| `hardware/dolby` | [anonytry/hardware_dolby](https://github.com/anonytry/hardware_dolby) |
| `vendor/qcom/opensource/vibrator` | [anonytry/android_vendor_qcom_opensource_vibrator](https://github.com/anonytry/android_vendor_qcom_opensource_vibrator) |

## signing

release builds are signed with private keys that never leave the build machine. if you build it yourself, generate your own keys (or build with test keys). your build won't update over the official releases here and that's expected, different keys.

## the all in one script

[`build_pixelos17_sky.sh`](https://github.com/once-human/local_manifests/blob/seventeen/scripts/build_pixelos17_sky.sh) is the script the first release was built with. it syncs, builds, signs, verifies and packages the fastboot and recovery zips. the fastboot zip packaging needs [`fix_super_empty.py`](https://github.com/once-human/local_manifests/blob/seventeen/scripts/fix_super_empty.py), which makes `fastboot update` flash super in one step.

for a plain build, the manifest above is all you need.
