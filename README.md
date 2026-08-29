# GurushNOW — Android APK Distribution (Private)

This private repository hosts the signed **GurushNOW** Android app
(`com.gurushnow.app`) as GitHub Release assets so the public APK download
button can point at a reliable, resumable, globally-distributed download URL.

## Latest Release

See the [Releases](../../releases) page.

- **App:** GurushNOW Android
- **Package:** `com.gurushnow.app`
- **Latest version:** `v1.1.2` (build `+5`)

## Updating the APK

Upload the signed APK and tag a release:

```bash
# tag a new version
git tag v1.2.0 -a -m "GurushNOW v1.2.0"
git push origin v1.2.0
```

Then create the release and attach the APK:

```bash
gh release create v1.2.0 ~/Downloads/GurushNOW-v1.2.0.apk \
  --repo DarnOsint/gurushnow-apk-dist \
  --title "GurushNOW v1.2.0" \
  --notes "Android download for GurushNOW v1.2.0"
```

Grab the resulting `browser_download_url` of the `.apk` asset and update
`web/src/lib/download-url.ts` in the main app.

> Note: anyone with the direct asset URL can download it. Keep this repo
> **private** so the release page/build tree isn't publicly browsable.
