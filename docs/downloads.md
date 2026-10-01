# downloads

**latest build:** [releases page](https://github.com/once-human/pixelos-sky/releases/latest), direct links to every file.

**all builds:** [sourceforge.net/projects/pixelos-sky/files](https://sourceforge.net/projects/pixelos-sky/files/)

## which file

every build comes with three files:

| file | what it is |
|---|---|
| `PixelOS_sky-<version>-fastboot.zip` | for [fastboot](install-fastboot.md). **grab this one if unsure** |
| `PixelOS_sky-<version>.zip` | for [recovery](install-recovery.md) |
| `SHA256SUMS` | checksums, to make sure your download isn't broken |

you only need one of the two zips.

## how builds are organised

```
pixelos-sky/
└── 17/                  pixelos 17 (android 17)
    └── 2026-09/         one folder per monthly build
        ├── PixelOS_sky-17.0-20260930-1940-fastboot.zip
        ├── PixelOS_sky-17.0-20260930-1940.zip
        └── SHA256SUMS
```

same names everywhere: the sourceforge folder `17/2026-09` has its notes in [releases/17/2026-09.md](../releases/17/2026-09.md) and its own [release](https://github.com/once-human/pixelos-sky/releases) on github.

## check your download

put `SHA256SUMS` in the same folder as the zip, then:

| os | command | good result |
|---|---|---|
| linux | `sha256sum -c SHA256SUMS --ignore-missing` | `OK` |
| mac | `shasum -a 256 PixelOS_sky-<version>-fastboot.zip` | same hash as the line in `SHA256SUMS` |
| windows | `certutil -hashfile PixelOS_sky-<version>-fastboot.zip SHA256` | same hash as the line in `SHA256SUMS` |

not matching? download it again.
