# Fork modification notice

This repository is a **modified fork** of [sw33tLie/macshot](https://github.com/sw33tLie/macshot).

macshot is free software licensed under the **GNU General Public License v3.0**
(see [`LICENSE`](LICENSE)). The original copyright belongs to the upstream
authors and is retained in full. This fork remains licensed under GPLv3.

In accordance with GPLv3 §5(a), the modifications made in this fork are stated
below with their dates.

## Modifications

### 2026-06-30 — Auto-redact on capture
Added an **"Auto-redact sensitive data on capture"** preference
(Settings → Capture). When enabled, the existing PII redaction
(`AutoRedactor` / `performAutoRedact()`) runs automatically right after an
interactive capture selection is committed, so sensitive data (emails, credit
cards, SSNs, etc.) is censored without a manual step. The setting is off by
default and stored under the UserDefaults key `autoRedactOnCapture`.

Files changed:
- `macshot/UI/Windows/SettingsWindowController.swift` — preference checkbox
- `macshot/UI/Overlay/OverlayView+Popovers.swift` — `autoRedactOnCaptureIfEnabled()`
- `macshot/UI/Overlay/OverlayView.swift` — trigger on selection commit

Also added `.github/workflows/local-build.yml`, an unsigned CI build workflow
for producing a locally-runnable `.app` from this fork.
