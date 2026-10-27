# Developer preview notes

## 0.3.0

A native browser experience upgrade with a structured sidebar, a fully interactive compact tab rail, more page padding, glass surfaces, the corrected metallic orbit artwork, context and tab transitions, Google by default, local address suggestions, space swipes, grouped settings and a local Dia import preview.

Reliability repairs include settings-window geometry, tab pinning, profile/space identity and selection, deletion cleanup, split-state persistence, command-palette search and keyboard focus, and query punctuation encoding.

### Verification

The local ARM64 build passed 92 tests. Native UI checks covered settings, profile controls, palette filtering/Return, compact mode, and the space-management menu. Hardware trackpad gestures and signed iCloud authentication still need end-to-end confirmation.

### Known release limits

- Ad-hoc signed, not Apple notarized.
- Browser passkey access needs Apple-approved signing and an appropriate provisioning profile. Automatic iCloud password filling is not verified.
- Dia migration supports readable bookmarks/history only; encrypted sessions, credentials, cookies and extensions are excluded.
- This is a developer preview, not a completed stable release.
