# Developer preview notes

## 0.6.8

- **Fullscreen Tab Switching & Background Layer Purge:** Fixed an issue where switching tabs while a video (e.g. YouTube) was in element fullscreen would leave the previous tab's content (such as Cloudflare) visible in the viewport or render a blank window. Inactive tabs' web views are now immediately removed from the container on tab change, element fullscreen is cleanly dismissed, and clicking a tab in the sidebar reliably attaches and displays the selected tab.
- **Universal 2 Binary (Apple Silicon & Intel Macs):** Built as a native Universal fat binary (`arm64` + `x86_64`), Developer ID signed, Apple notarized, and stapled into both `.dmg` and `.zip` distribution packages.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.6.7

- **Edge-Hugging Liquid Progress Beam:** Redesigned page loading with an edge-hugging luminous neon beam that flows along the rounded corners and contours of the webpage canvas with a glowing white-hot comet spark head and bloom completion effect.
- **Seamless Light & Dark Mode Dynamic Switching:** Toggling between System, Dark, and Light appearances in Settings now cascades instantly across all open windows, chrome surfaces, and WebKit rendering instances without app relaunches or page refreshes.
- **Adaptive Sidebar Tinting Enabled by Default:** "Tint Sidebar with Page Color" is now enabled by default for all users, dynamically sampling chromatic tints from active web pages and adapting vibrantly across both Light and Dark palettes.
- **Premium Frosted Glass Settings Redesign:** Transformed Settings with full-size translucent glass (`NSVisualEffectView`), floating macOS traffic lights, polished search pill, custom pill-selected navigation rows with brand indicator, and frosted acrylic card containers with subtle hair-thin borders.
- **Multi-Context Private Browsing & Keyboard Shortcut Navigation:**
  - Pressing `⌘⇧N` enters private browsing from normal mode, and closes the current private browsing context and returns to normal browsing when pressed inside private mode.
  - Full support for multiple completely isolated private browsing contexts ("Private 1", "Private 2", etc.), each with independent ephemeral data stores, created directly from the sidebar.
  - Fixed Profile Switcher layout and badge positioning to eliminate text overlap, truncation, and awkward ellipses.
- **Universal 2 Binary (Apple Silicon & Intel Macs):** Built as a native Universal fat binary (`arm64` + `x86_64`), Developer ID signed, Apple notarized, and stapled into both `.dmg` and `.zip` distribution packages.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.6.5

- **Universal 2 Binary (Apple Silicon & Intel Mac support):** compiled as a native Universal binary running with full hardware performance on both Apple Silicon (M1–M4, ARM64) and Intel (x86_64) Macs running macOS 14 Sonoma or macOS 15 Sequoia.
- **Packaged DMG Disk Image:** distributed in a custom-designed `.dmg` installer with drag-to-Applications layout, signed with Developer ID and notarized by Apple.
- **Open in native desktop apps:** clicking "Open in Teams", Zoom, Slack, Figma, Notion, or mailto links prompts cleanly with a glass confirmation sheet and "Always Allow" memory per host, launching the native macOS app while protecting against dangerous schemes.
- **Fullscreen video recovery:** eliminated black/blank screens when entering fullscreen or switching tabs and windows during video playback, preserving WebKit fullscreen hierarchy and hardware compositing layers.
- **Keyboard shortcuts:** suppressed unwanted macOS system alert beeps while preserving full shortcut handling on YouTube and web video players (arrow keys, J, K, L, M, F, and spacebar).
- **New Tab 3D Emblem:** enhanced the animated orb with physical surface texture micro-relief, directional 3D key/fill lighting, ambient occlusion, and specular highlights.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.6.4

- **Web page interaction:** restored full pointer interaction, clicking, and typing into text inputs, search boxes, and forms across all web pages.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.6.3

- **Session restoration:** the browser remembers the exact active space, active tab, and per-space active tabs across app quits and window closes, returning you right where you left off.
- **Media & fullscreen stability:** disabled automatic VisionKit text analysis overlay on web video elements, preventing geometry crashes when entering element fullscreen.
- **Adaptive sidebar colors:** navigation and dynamic page themes update reliably, stale samples cannot overwrite a newer page, and light/dark surfaces retain readable text.
- **Popup protection:** preserve approved navigation chains, restore popup rules alongside compiled filter caches, and correctly resolve disabled filter rules.
- **Privacy and permissions:** camera, microphone and notification decisions are separated by full origin; old hostname-only approvals require a fresh prompt. Private favicons use a memory-only cache that rejects late results after the session ends.
- **Extensions:** enforce content-script exclusions and resource containment. Native controllers remain available on existing tabs; disabling extensions unloads their contexts and cancels unfinished loads.
- **Browser fixes:** search shortcut encoding and completion casing, split-pane preservation, profile teardown, download progress and sidebar control consistency.
- **Screen sharing:** the custom bridge is restricted to the main frame; unsupported audio sharing is disabled and labelled unavailable. The app delegate is retained explicitly throughout the release event loop.

**Verification:** Automated tests passed across all suites. The final package is ARM64, Developer ID signed, notarized and stapled.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.6.2

- **Three sidebar modes.** Expanded, Compact (a slim rail) and Hidden (only the page; move the pointer to the left edge and the sidebar slides over it, then tucks away when you leave). Change it from View → Sidebar, Settings → Appearance, or press ⌃⌘S to cycle.
- **The close, minimise and zoom buttons live in the sidebar in every mode:** in the card's corner when expanded, centred across the rail when compact, and shown only while the sidebar slides out when hidden. No title-bar strip, and the page keeps the same even border everywhere.
- **Tabs.** Related link tabs (⌘-click, middle-click, Open Link in New Tab) can group with the page they came from (asked once; change it in Settings → Tabs). Groups collapse and close together. Split panes share one row. ⌘T always focuses the start-page search.
- **Dark mode fixes.** A window that switched to dark kept some light colours (white selected tab, grey address bar, light error page). Colours now follow Light and Dark changes everywhere. Selected tabs get a restrained ruby highlight.
- **Fixed:** the floating-player tests were unreliable on a busy Mac (test-only); the fixed localhost shortcuts were removed from Developer.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.6.1

- **Aether now appears in System Settings → Desktop & Dock → Default web browser.** It declared web links but not web pages, and macOS lists a browser only if it claims both. Drag Aether into Applications, open it from there, then choose it in System Settings (or Aether → Settings → Default Web Browser). It claims web pages at the lowest priority, so it does not take over opening `.html` files.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.6.0

- **Ad and tracker blocking.** Aether now blocks ads and trackers with the public EasyList and EasyPrivacy lists, converted to WebKit's native rules, on top of the existing tracker rules. Sign-in, payment and CAPTCHA pages are never blocked. About once a week (or with Settings → Update Now) it downloads fresh lists from easylist.to; nothing about your browsing is sent, and the weekly download can be turned off. The first launch after installing takes a few seconds longer while the lists are prepared, and the app uses more memory than before. It does not block everything: some first-party and video ads (YouTube) still get through, and there is no "blocks all ads" claim.
- **Site shields.** A shield button in the address bar (and in the collapsed rail) turns blocking off or on for one site, per profile, and reloads the page.
- **Floating video.** When a playing video leaves view because you switched tab or space, it can float in a small player so it keeps playing (Settings → turn off "Float playing video when I switch tabs or spaces"). The picture-in-picture button falls back to this player when WebKit does not enter picture in picture.
- **A real 3D logo** on the start page that you can drag to turn, a softer start-page glow, a tidier address bar (long addresses no longer run under the shield), and the window buttons live inside the sidebar again.
- **Fixes:** YouTube and other videos go fullscreen without a blank page; a warning appears if Aether is run from a disk image or a temporary download folder, where it can crash when the disk image goes away; light-mode glow and halo polish; swiping anywhere over the sidebar switches space.

Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.5.3

- **A real 3D logo.** The start-page logo is now a glowing ball that turns in 3D: the ribbon slides around the curve of the sphere, the surface flows like liquid, and a rim of light and a drifting highlight play across the glass. It is drawn on the GPU by a tiny shader and costs almost nothing. The pointer tilt and the orbit rings are gone; the colour blobs stay.
- **The profile and space read as "Personal • Media"** under the greeting, with the dot in the space's colour.
- **Address suggestions are centred** and a single suggestion no longer clips or shows a scroller.

Motion respects Reduce Motion (the ball is then a still image). Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

## 0.5.2

- **A livelier new-tab page.** The logo is centred and animated: it pops in, turns, floats, glows and leans toward your pointer. The page has a slowly drifting background coloured by your current space (or its wallpaper), faint stars, and two orbits with small satellites around the logo.
- **Rotating greetings**, including a time-of-day one ("Good morning, <your first name>."), a fresh one each time you open a tab and a new one every few seconds.
- **Quick-action chips** (Private, Split view, History, Downloads, Settings) and a **Jump back in** row of your most recent pages.
- **Shortcut tiles** lift and glow when you hover them.
- **Tabs animate open:** a new tab grows into the sidebar with a soft spring, and a new tile pops into the collapsed rail.

Motion respects Reduce Motion. Signed with a Developer ID and notarized by Apple. If you are on 0.5.0 or later, Aether can update itself: Aether → Check for Updates…

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
