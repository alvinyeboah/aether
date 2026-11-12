# Developer preview notes

## 0.7.9 — 12 November 2026

Five improvements for a safer, smoother Aether.

- **One session owner:** Aether acquires a process lock before opening browsing data. Additional launches hand off to the existing browser; a crashed process cannot leave a stale lock. Update & Restart waits for the old process to exit.
- **Adaptive sharing:** Automatic sharing quality adjusts frame rate and resolution when delivery slows or thermal pressure rises. High and Efficient modes are available in Settings → Performance. Existing stream, aspect ratio, sharing badges and capture boundaries are preserved.
- **Undo deletions:** Use the Undo toast, Edit → Undo Space or Group Deletion, or the command palette after deleting a space or closing a group. Undo is available for 15 seconds within the original profile and preserves custom appearance and newer work.
- **Space Overview:** Open Spaces → Space Overview or search for it with Command-K. Search spaces and tab titles, preview tab lists, open a space, and drag cards to reorder. Suspended pages are not loaded for previews.
- **Permission Activity:** Open View → Permission Activity or Settings → Privacy. See requests, decisions and observed capture changes. History is local to this Mac, profile isolated, limited to 500 events and 30 days, and private browsing is never recorded. Stored origins omit paths, queries and credentials.

Signed, notarized Universal app for Apple Silicon and Intel, macOS 14 or later. No new services, accounts or telemetry. Apple credential approval is unchanged.


## 0.7.8 — 11 November 2026

Aether 0.7.8 brings clearer spaces, sharing and meeting controls.

- Choose an icon, emoji and colour when creating a space or profile, from the sidebar or Settings.
- Spaces compact to icons during reordering, with a smaller drag preview and clear insertion marker.
- Refined tab groups with quieter headers, readable counts and visible expand/close controls.
- Share-tab choices stay inside the requesting space. Shared source tabs are marked in expanded, compact and split layouts. Moving either endpoint outside the authorized space stops capture.
- Optional haptic feedback for tab and space actions, sidebar modes, appearance selection and completed actions. Disable it under Settings → Appearance.
- Improved meeting PiP selection for camera-off participants, with name/initial cards; keeps participants visible while you present and remote presentations alongside participants when someone else presents.
- Required crash-recovery prompts survive chrome refreshes, and quitting before choosing recovery preserves the saved session.
- Removed unnecessary Swift executor checks from constant AppKit orientation getters.
- About Aether now shows the installed bundle version and build, with the actual running architecture, rather than the old milestone label.

Universal macOS build for Apple Silicon and Intel. Signed and notarized. Apple credential entitlement approval is still separate from this release; this update does not claim to enable passkeys.


## 0.7.7 — 11 November 2026

- Scroll over the expanded sidebar's spaces dock to browse all your spaces. Both sideways trackpad movement and vertical mouse-wheel scrolling work, without selecting spaces one by one.
- Routine tab/title/count updates preserve the dock position you chose. Choosing a different space still brings it into view.
- The compact rail keeps its existing space-switch gesture; sidebar gestures outside the expanded dock retain their behavior.
- Command-Shift-C now copies the active page's full URL immediately, including its query string and fragment. It does not open a confirmation or remove parameters. A separate Copy Clean Link… option remains in Edit.
- Removed the misleading Command-Shift-C hint from the clean-link context-menu action. The new Copy Page URL command is available in shortcut settings.

Universal app for Apple Silicon and Intel Macs, macOS 14 or later. Apple Passwords allowlisting and the browser credential entitlement are separate approval processes; this release does not enable or claim approved inline AutoFill/passkey access.


## 0.7.6 — 4 November 2026

Fixes the overlapping buttons, misplaced search text and clipped loading bar in 0.7.5.

- Buttons, pop-up menus, filter pills and search fields no longer overlap or sit taller than their row. This affected Bookmarks, History, Downloads, Settings, the tab manager and the other panels.
- Search fields place their icon, placeholder and typed text on one line, with a clear button.
- The page loading bar now draws on top of the page's rounded corner, so its glow and full stroke are no longer cut off.

This release supports Apple Silicon and Intel Macs running macOS 14 or later. Browser passkeys and inline Apple Passwords remain subject to Apple's pending approval; this update does not change their availability.

## 0.7.5 — 4 November 2026

Buttons and search fields now line up across Aether's pages and dialogs.

- Buttons, pop-up menus and search fields in a row share one height and one spacing, so toolbars and footers no longer sit flush against each other.
- Search fields are now drawn in Aether's own style, matching the buttons beside them, with an accent outline while you type. This covers Bookmarks, History, Downloads, Settings, the tab manager, Find in Page and the developer tools.
- The tab manager, reading queue, keyboard shortcuts, resource monitor, import and workspace recovery dialogs use Aether's buttons instead of the system ones.
- Optional n0tch companion (off by default). Turn it on under Settings → Tabs & spaces to share a bounded busy/idle signal, meeting state and download progress with the n0tch app on your Mac. Private tabs are never shared, and nothing leaves your Mac.

This release supports Apple Silicon and Intel Macs running macOS 14 or later. Browser passkeys and inline Apple Passwords remain subject to Apple's pending approval; this update does not change their availability.

## 0.7.4 — 3 November 2026

Bookmarks, history, downloads and settings now share a more deliberate Aether interface.

- Bookmarks: spacious saved-page rows with site initials, addresses and folders, a clearer search/filter toolbar, and selection-aware actions.
- History: a chronological timeline with day headings, visit times and clearer empty/search states. Pagination and profile isolation remain intact.
- Downloads: Aether filter pills, larger file rows, custom progress with VoiceOver information, and the existing cancellation and recovery actions.
- Settings: consistent page headings, red-accented navigation, Aether checkboxes and appearance/layout selectors, and wrapping option descriptions.
- Fixed saving the current page refreshing before the bookmark had been written. Saving now respects the selected folder, and changing filters clears stale selections.
- Import/export confirmations now use Aether's prompt design.
- Stronger pop-under protection: Aniwaves gets stricter cross-site popup handling, and script-created windows cannot escape through blank-page redirects to unknown advertising sites. Ordinary links, explicit modifier clicks, site exceptions and recognized sign-in/payment providers retain their supported paths.
- Corrected the vertical centering of saved-site initials and download action padding.

This release supports Apple Silicon and Intel Macs running macOS 14 or later. Browser passkeys and inline Apple Passwords remain subject to Apple's pending approval; this update does not change their availability.


## 0.7.3 — 3 November 2026

- **Meeting stage for the floating call player.** When a call floats while you work in another tab, the compact player now shows the people who matter: up to two remote participants (the active speaker, or a shared screen plus a speaker), never your own camera or your own presentation. A small readout says who is speaking, who has a hand raised or that a screen is shared, and falls back to a neutral "In meeting" when the page gives no clear information. It reads page metadata only: it does not touch the call's audio or video tracks, and it leaves the provider's buttons and page styles alone.
- **It is tuned for Google Meet.** Participant tiles are recognised from the information a page exposes. Other providers (Zoom, Teams, Webex, Whereby, Discord, Chime) may show only the "In meeting" readout without video until they are checked and tuned.

**Verification:** 542 automated tests passed (serial run), including 15 for stage selection on simulated meeting pages. Universal app for Apple Silicon and Intel, macOS 14+. Developer ID signing and Apple notarization.

**Preview limits:** the stage has not been tried in a live Google Meet, Teams or Zoom call yet, and the earlier open items (repeated live YouTube fullscreen, Granola handoff, real network resume) still need live acceptance.

## 0.7.2 — 3 November 2026

- **First-run setup.** A seven-step welcome flow lets a new user choose sidebar layout, tab grouping, search, an optional import from Dia, Chrome, Arc or Safari (with bookmark/history selection) and everyday preferences before browsing. It is animated, previews each choice, and can be replayed from Settings. Existing users are not interrupted.
- **Everyday browsing.** Closed-space recovery, keyboard tab search, per-site zoom, searchable downloads, a reading queue with sanitized Reader copies, focused website windows, standard website shortcuts and clearer health controls.
- **Quieter and more responsive.** Page loading progress no longer redraws the whole browser, hidden start-page history work only runs when the start page is showing, History and Bookmarks no longer wake up needlessly, and extension tab bookkeeping is cheaper. These remove work; they are not measured speed-ups.
- **Granola companion (optional, off by default).** Opening Granola for a recognised meeting now shows it, reports a failed launch and lets you retry, and re-checks when you turn the setting on during a call. Opening Granola does not start transcription; open the meeting note or press New Note in Granola.
- **Prompts and sharing.** The startup recovery prompt keeps stable button layouts (this fixes a layout crash), and screen-share frames are prepared off the main thread with back-pressure so the browser stays responsive while sharing.
- **Extensions and passwords groundwork.** Native extensions now see the right tabs and windows per profile, and the system's own credential menus are preserved on login fields. This is groundwork only: iCloud Passwords/passkey filling and extension store installation are not working yet and are not claimed.

**Verification:** 527 automated tests passed (run serially). Universal app for Apple Silicon and Intel, macOS 14+. Developer ID signing and Apple notarization.

**Preview limits:** repeated live YouTube fullscreen, provider-specific meeting controls, real network resume, native notifications and the Granola handoff still need live acceptance on this build. The meeting "stage" view is not part of this release.

## 0.7.1 — 2 November 2026

- **Readable DevTools:** larger interface and code text, clearer contrast and selection, more room for details, document-bound edits, full storage-value editing and bounded network response previews. Capture stops when the inspector is hidden.
- **Buttons and settings:** Restore Backup and other prompt actions keep complete labels; crowded actions stack, and settings controls adapt to narrow windows. Added customizable menu shortcuts, a redacted diagnostics preview/export, appearance storage cleanup and per-site page-text exclusions.
- **Session and tab safety:** preserve pending saves during imports, retire deleted profiles from recovery, restore the correct profile/space, preserve selected split panes and suspend tabs only after their web view is released.
- **Downloads and updates:** preserve file reservations through cancellation, keep progress controls stable, identify missing files, warn before quitting active downloads and honor failed-save/canceled-quit decisions. Normal downloads retain a minimal local interrupted-transfer notice across restarts; restart from the original website. Private downloads are excluded.
- **Browsing boundaries:** scope history, zoom, HTTP fallback, Reader, Find, previews and delayed actions to the owning profile and document. Reader content is inert; preview failures are visible. Improved translation cancellation, notification replacement/closing, URL parsing, icon limits and tracking-link cleanup.
- **Extensions and appearance:** restore normal-profile registrations and display real load failures, tear down retired profiles, keep private assets transient, and bound image imports. Unsupported extension action popups explain their limitation.
- **Import undo:** review an import operation and remove only its unchanged imported rows; preserve later edits and profile/space containers.
- **Optional Granola companion:** Settings → Tabs can open the installed Granola app when a recognized Meet, Teams or Zoom page uses the microphone. Off by default, excluded from private browsing, and sends no meeting details. Start a note in Granola to transcribe; Aether does not start recording.

**Verification:** 488 automated tests passed across 130 suites. Universal app for Apple Silicon and Intel, macOS 14+. Developer ID signing and Apple notarization are verified as part of release publication.

**Preview limits:** repeated live YouTube fullscreen, provider-specific meeting controls, real network resume, native notifications and Granola handoff still need live acceptance checks. Resume support depends on WebKit/server support; recovery after restarting Aether is an interrupted notice rather than automatic authenticated resume. Cross-origin iframe tint may fall back to the outer page. Extension action popups, iCloud passkeys and Apple Passwords AutoFill remain unavailable or unverified. No new passkey approval is claimed.

## 0.7.0

- **Site controls:** review camera, microphone and notification permissions, host shields and site-data clearing from the address/rail shield button.
- **Downloads:** progress, individual dismissal and Retry/Resume when WebKit provides recovery data and the original tab context is still available.
- **Session safety:** local recovery snapshots and an explicit choice after an interrupted shutdown. File → Recover Session… restores recent normal-profile tabs; private contexts must be closed first.
- **Tab Manager:** profile-scoped search, exact-URL duplicate preview, multi-selection, pin/unpin, move and confirmed close (Command-Option-Shift-T).
- **Bookmark portability:** native HTML import/export with folder handling and per-profile duplicate checks.
- **Browser repairs:** session-save ordering, profile boundaries on startup and tab moves, split-pane selection, popup redirect protection, and presentation ownership during fullscreen refreshes.
- **Meeting PiP:** precise self-microphone/camera/hand controls, a reaction picker, unavailable-control feedback, hover highlights and press feedback.

Known preview limits: live YouTube fullscreen and meeting-provider acceptance still need verification; network resume depends on server/WebKit support. Cross-origin redirected iframe tint can fall back to the outer page. Very large bookmark folder names can cause excessive import memory use; recovery snapshots may retain deleted normal profiles until rotation. iCloud passkey and Apple Passwords AutoFill support is not verified.

Signed with a Developer ID and notarized by Apple. Existing installations can use Aether → Check for Updates….

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
