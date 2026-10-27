# Developer preview notes

## 0.4.2

- **Developer tools redesigned in Chrome's style.** Elements is now editable (edit as HTML, attributes and text, duplicate, delete) with a Styles pane (editable, toggleable declarations and colour swatches), Computed and a box-model Layout view. Network has record, clear, preserve log, type filters, a waterfall, and Headers / Preview / Response / Timing for each request. Application has a storage tree with a filter, value preview and editing.
- **Right-click menu** for pages in Aether's own design, including Inspect Element.
- **Websites now see Aether as Safari**, so Google and other sites serve their full modern pages (including AI Mode) instead of a stripped-down layout.
- Safari's Web Inspector can no longer attach to your tabs unless you turn it on in Settings, since that lets other programs read open pages.
- Fixes: a crash when a page opened a pop-up (sign-in windows), and the Downloads popover and Cancel button text.

Signed with a Developer ID and notarized by Apple. Passkeys are still unavailable until Apple approves the browser passkey capability (requested).

## 0.4.1

Same features as 0.4.0, now **signed with a Developer ID and notarized by Apple**, so it opens without the right-click workaround. Passkeys and iCloud password filling are still unavailable until Apple approves the browser passkey capability (requested).

## 0.4.0

A large update. New: a space dock with custom icons, colours and backgrounds for spaces and profiles; split view with resizable panes, a picker and drag and drop; private browsing; inline URL completion; page zoom, print, save and media pause; a Settings search box, Spaces editor and live shortcuts list; import from Safari, Chrome, Arc and Dia; built-in developer tools (Elements with a pick tool, Network, Application); link peek (⇧-click); search inside pages you have read; on-device page translation and picture in picture.

Changes: sideways swipes switch spaces only in the collapsed rail; the expanded dock scrolls when there are many spaces.

Fixes include a crash when a page opened a pop-up (sign-in windows), invisible Cancel button text in prompts, and the Downloads popover opening away from its button.

### Known limits

- Ad-hoc signed and not notarized: right-click Aether and choose Open the first time.
- Browser passkeys and iCloud password filling are not available yet (they need an Apple-approved entitlement and a signed build).
- Apple Silicon and macOS 14 or later. Page translation needs macOS 15 or later; glass surfaces use macOS 26 or later.
- Tested with automated tests and hands-on checks, not on a wide range of Macs; link peek, translation, picture in picture and trackpad swipes have had little real-world use.

## 0.3.0

A native browser experience upgrade with a structured sidebar, a fully interactive compact tab rail, more page padding, glass surfaces, the corrected metallic orbit artwork, context and tab transitions, Google by default, local address suggestions, space swipes, grouped settings and a local Dia import preview.

Reliability repairs include settings-window geometry, tab pinning, profile/space identity and selection, deletion cleanup, split-state persistence, command-palette search and keyboard focus, and query punctuation encoding.

### Verification

The local ARM64 build passed 94 tests. Native UI checks covered settings, profile controls, palette filtering/Return, compact mode, and the space-management menu. Hardware trackpad gestures and signed iCloud authentication still need end-to-end confirmation.

### Known release limits

- Ad-hoc signed, not Apple notarized.
- Browser passkey access needs Apple-approved signing and an appropriate provisioning profile. Automatic iCloud password filling is not verified.
- Dia migration supports readable bookmarks/history only; encrypted sessions, credentials, cookies and extensions are excluded.
- This is a developer preview, not a completed stable release.
