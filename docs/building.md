# building

everything's public. the manifest follows the `seventeen` branches of the sky repos.

## what you need

| | |
|---|---|
| os | linux (ubuntu 22.04+ or similar), x86_64 |
| disk | ~450 gb free, ssd |
| ram | 32 gb+ |
| stock roms | xiaomi's official recovery zips: sky `OS2.0.210.0.VMWMIXM` and mist `OS3.0.306.0.WPUINXM` (the vendor blobs are extracted from them) |

## build (script)

```bash
mkdir -p ~/stock-roms   # put both stock zips here
curl -fLO https://raw.githubusercontent.com/once-human/local_manifests/seventeen/scripts/build_pixelos17_sky.sh
chmod +x build_pixelos17_sky.sh
./build_pixelos17_sky.sh
```

it syncs, extracts the blobs, checks the configuration and kernel early, builds a signed user build, verifies it and packages the release.

## build (by hand)

```bash
mkdir pixelos && cd pixelos
repo init -u https://github.com/PixelOS-AOSP/android_manifest.git -b seventeen --git-lfs
mkdir -p .repo/local_manifests
curl -fLo .repo/local_manifests/sky.xml https://raw.githubusercontent.com/once-human/local_manifests/seventeen/sky.xml
repo sync -c -j"$(nproc)" --force-sync --no-clone-bundle --no-tags

cd device/xiaomi/sky
./extract-files.py --only-common ~/stock-roms/<mist zip>
./extract-files.py --only-target ~/stock-roms/<sky zip>
cd -

source build/envsetup.sh
lunch custom_sky-cp2a-user
m pixelos
```

## sources

| path | repo |
|---|---|
| `device/xiaomi/sky` | [once-human/android_device_xiaomi_sky](https://github.com/once-human/android_device_xiaomi_sky/tree/seventeen) |
| `device/xiaomi/sm4450-common` | [once-human/android_device_xiaomi_sm4450-common](https://github.com/once-human/android_device_xiaomi_sm4450-common/tree/seventeen) |
| `kernel/xiaomi/sm4450` | [once-human/android_kernel_xiaomi_sm4450](https://github.com/once-human/android_kernel_xiaomi_sm4450/tree/seventeen) (linux 6.6, `-onkar`) |
| `kernel/xiaomi/sm4450-modules` | [once-human/android_kernel_xiaomi_sm4450-modules](https://github.com/once-human/android_kernel_xiaomi_sm4450-modules/tree/seventeen) |
| `kernel/xiaomi/sm4450-devicetrees` | [once-human/android_kernel_xiaomi_sm4450-devicetrees](https://github.com/once-human/android_kernel_xiaomi_sm4450-devicetrees/tree/seventeen) |
| `hardware/xiaomi` | [once-human/android_hardware_xiaomi](https://github.com/once-human/android_hardware_xiaomi/tree/seventeen-6.6) |
| `vendor/xiaomi/*` | extracted from the stock roms above |

the october (5.10) build's sources are on the [`seventeen-5.10`](https://github.com/once-human/local_manifests/tree/seventeen-5.10) manifest branch.

your own build is signed with your own keys, so it won't update over the releases here. that's expected.
