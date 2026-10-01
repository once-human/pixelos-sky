# building

everything's public. the manifest pins every device repo to the exact commit of the latest release.

## what you need

| | |
|---|---|
| os | linux (ubuntu 22.04+ or similar) |
| disk | ~400 gb free, ssd |
| ram | 32 gb+ |

usual aosp build dependencies.

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

your own build is signed with your own keys, so it won't update over the releases here. that's expected.

the [build script](https://github.com/once-human/local_manifests/blob/seventeen/scripts/build_pixelos17_sky.sh) used for releases also packages the fastboot and recovery zips.
