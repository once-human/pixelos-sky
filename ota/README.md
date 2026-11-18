# ota

the built-in updater (settings > system > updater) reads `seventeen/sky.json` here and shows
`seventeen/changelogs/sky.md` as the changelog.

both files are made by the build script with each release (`ota/` in the release folder). publish
them only **after** the zip is uploaded to the url inside `sky.json`, or phones will fail the download.
