# screenshots

one folder per android version, so old ones stay around when a new version lands.

```
screenshots/
└── 17/
    ├── 01-home.png
    ├── 02-lockscreen.png
    ├── 03-quick-settings.png
    ├── 04-settings.png
    ├── 05-about-phone.png
    ├── 06-wallpaper-styles.png
    ├── 07-camera.png
    └── 08-geekbench.png
```

## rules

| | |
|---|---|
| format | png, straight from the phone (power + volume down) |
| names | `NN-what-it-is.png`, lowercase, numbered in the order they show up |
| size | under 1 mb each if possible, the readme loads all of them |
| content | no personal stuff: notifications, names, numbers, wifi names |

## adding them

upload into `screenshots/17/` (on github: open the folder > add file > upload files). the main [readme](../README.md) already has a gallery for the names above inside a comment block, just remove the two comment lines (`<!--` and `-->`) and the "coming soon" line. different names? edit the `src` paths there to match.
