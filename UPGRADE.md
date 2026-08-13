# Hugo 0.165 compatibility upgrade notes

## Summary

This theme was updated for compatibility with Hugo v0.165.0 and newer releases.

## Changes made

- Replaced deprecated pagination config:
  - `paginate` -> `pagination.pagerSize`
- Replaced deprecated default language config:
  - `languageCode` -> `defaultContentLanguage`
- Removed deprecated site author access patterns:
  - `.Site.Author` -> `.Site.Params.author`
- Removed deprecated server detection patterns:
  - `.Site.IsServer` -> `hugo.IsServer`
- Updated the example site config and documentation references to the supported configuration format.
- Added CI coverage for Hugo 0.165.0 in the GitHub Actions workflow.

## Files updated

- `exampleSite/config.toml`
- `README.md`
- `layouts/_default/baseof.html`
- `layouts/partials/comments.html`
- `layouts/partials/authorbox.html`
- `layouts/partials/post_meta/author.html`
- `.github/workflows/ci-test.yml`

## Verification

The theme was validated against the actual Hugo v0.165.0 binary using the example site:

```powershell
Set-Location 'c:/Users/andyl/code/Mainroad/exampleSite'; & 'C:/Users/andyl/AppData/Local/Temp/hugo_0_165_0/hugo.exe' --theme Mainroad --themesDir ../.. --logLevel info
```

Result: successful site build with `Pages | 43` and no fatal compatibility errors.

## Note

The only reported message was a Goldmark raw-HTML warning from the demo article content, which is informational and does not indicate a theme incompatibility with Hugo 0.165.
