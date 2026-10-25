# AINS Studio Glasswing for Firefox v5.0.0

**Codename: Glasswing**

Glasswing brings AINS Studio’s v5 tools to Firefox as a Manifest V3 browser add-on. This package adapts the background lifecycle and API namespace to Firefox while retaining the shared AINS Studio interface and feature set.

## Highlights

- Full AINS-hosted settings center with global enable/disable and per-feature switches.
- Reading overview with date-based counts, local record snapshots, activity, and CSV export.
- Theme, supported translation, and clipboard controls.
- AINS announcement “Don’t show again” preference, reversible from settings.
- Custom Studio 404 page and account-bar shortcut.
- Excel/CSV record assistant, gated by its local admin-only UI lock.
- Firefox-specific Manifest V3 event-page background declaration and `browser.*` compatibility adapter.
- AINS-only host scope: `https://ains.moe.gov.my/web/*`.

## Developer notes

Firefox does not use `background.service_worker` for this Manifest V3 target. The manifest declares a non-persistent `background.scripts` event page instead. Content scripts load `browser-compat.js` before the shared scripts so Safari/Firefox’s `browser` namespace is available under the API name expected by the shared Promise-based code.

The extension declares local storage and scripting permissions, plus a Gecko add-on ID and minimum version. It declares `data_collection_permissions.required` as `none`: the extension stores its preferences and reading snapshots locally and does not transmit that data to an AINS Studio backend.

The Excel assistant’s local password check does not authenticate an AINS administrator account or change server permissions. Mozilla’s signing and review requirements still apply before public distribution. This source ZIP has not been signed or approved by Mozilla.

## Install for development

1. Extract `ains-studio-glasswing-firefox-v5.0.0.zip`.
2. Open `about:debugging#/runtime/this-firefox` and choose **Load Temporary Add-on…**.
3. Select `manifest.json`, then open and refresh AINS.

Temporary installations are removed when Firefox closes. Submit the package through Mozilla Add-ons for a signed public release.
