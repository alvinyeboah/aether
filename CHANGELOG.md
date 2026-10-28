# Developer preview notes

## 0.5.1

- **Sidebar padding now matches the page margin** (20 pt on each side and at the bottom), so the sidebar and the page share one outer padding.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0, Aether can update itself: Aether → Check for Updates…

## 0.5.0: security release

- **Updates:** Aether can now check GitHub once a day and update itself (Settings → General → Updates, or Aether → Check for Updates…). It installs only a build that is signed by the same developer as your copy, notarized by Apple, has the same bundle identifier and a higher version. You can turn the daily check off. This version has to be installed by hand once; later versions can update themselves.
- **HTTPS first:** web addresses typed as http:// are tried as https:// first, and Aether asks before using a site that has no secure version. Plain-HTTP pages show a warning in the address bar. Localhost and private-network addresses are left alone (Settings → Privacy & Security).
- **Real tracker blocking:** about 150 rules for analytics, session recording, ad networks and social pixels, applied only when another site loads them. Sign-in, payments and CAPTCHAs are not touched.
- **Private data on disk:** Aether's data folder and its files are now readable only by your account; downloads get a proper macOS quarantine tag; remembered page text is deleted after 7, 30 or 90 days (30 by default).
- **Extensions are off by default** (Settings → Extensions → Enable experimental extensions).
- **Security policy:** report vulnerabilities privately at https://github.com/alvinyeboah/aether/security/advisories/new. Details at https://aether.alvinyeboah.com/security.
- Fixes: "Frame load interrupted" is no longer shown as an error over a working page or a download.

Not changed: Aether's own app process is not App Sandboxed (web pages are, through WebKit), there is no built-in password manager, and there has been no independent audit. Passkeys are still waiting on Apple.

Signed with a Developer ID and notarized by Apple.

## 0.4.3

- **Fixes "Sign in with Google" and "Sign in with Apple"** on X, Pinterest and other sites. Aether's tracker rules were blocking every window a page opened, so the sign-in window never appeared. Pop-ups opened by a click now work, and they close themselves and hand control back to the page that opened them.
- Pop-ups that nobody asked for are still blocked by WebKit, which only lets a page open a window from a click or other user action.

Signed with a Developer ID and notarized by Apple. Passkeys are still unavailable until Apple approves the browser passkey capability (requested).

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
