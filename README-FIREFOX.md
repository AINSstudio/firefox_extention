# AINS Studio Glasswing for Firefox

Firefox build of AINS Studio **v5.0.1**, codename **Glasswing**. The package uses Firefox’s Manifest V3 event-page background scripts and the standard `browser.*` API namespace through a compatibility adapter for the shared extension code.

## Install temporarily for development

1. Extract `ains-studio-glasswing-firefox-v5.0.1.zip`.
2. Open `about:debugging#/runtime/this-firefox`.
3. Choose **Load Temporary Add-on…** and select the package’s `manifest.json`.
4. Open AINS at `https://ains.moe.gov.my/web/` and refresh the page. Use the extension toolbar icon or the AINS navbar shortcut to open Studio settings.

Temporary add-ons are removed when Firefox closes. To distribute a permanent install, sign the package through Mozilla Add-ons (AMO) or another Firefox-supported signing workflow.

## Included

- AINS Studio settings center, feature switches, theme and language controls, and custom Studio 404 page.
- Reading dashboard, local activity view, announcement preference, translation, and Excel/CSV record assistant.
- Firefox-specific Manifest V3 background scripts and a `browser` namespace adapter.
- Host access scoped to `https://ains.moe.gov.my/web/*` and a `none` data collection declaration.

The package targets Firefox 128 or later because it relies on the APIs declared by this Manifest V3 build. Firefox for Android is not declared as a target in this release.


### v5.0.1 background timer update
The Excel assistant now uses a persisted absolute deadline for its approval prompt. It resumes at the correct remaining time after background-tab throttling. If the browser or device suspends execution, the page continues when scheduled again.


