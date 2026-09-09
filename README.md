# Focus Buddy: website hosting package

Upload this entire folder to a static HTTPS website, preserving the assets subfolder. No build command, account system, database, or backend is required. Set index.html as the default document. Test the HTTPS URL directly before embedding it.

Do not paste index.html, timer.js, or the old embed-block.html into systeme.io. Use the short systeme-embed-template.html from the parent folder after replacing its placeholder with the real HTTPS URL of this uploaded timer.

Systeme.io integration
1. Choose the hosting URL for this folder.
2. Replace YOUR_TIMER_HTTPS_URL in the embed template with that actual URL.
3. Ask systeme.io support to review the exact short embed before saving, referencing the previous anti-phishing block. Their response did not identify the specific trigger, so this package cannot guarantee avoidance of another block.
4. Add only the reviewed short iframe to a Raw HTML element. Test on a live test page: systeme.io documents that Raw HTML is not shown in editor Preview.

This changes the integration: the builder receives a small URL-based iframe, not encoded audio or nested application source. The separately hosted app serves normal HTML, CSS, JavaScript, images, and audio files. No obfuscation, proxying, or attempts to bypass security checks are used.

Hosting must allow your systeme.io page to frame the timer. A host that adds X-Frame-Options: DENY/SAMEORIGIN or a restrictive CSP frame-ancestors may block embedding across origins. Have the host explicitly permit your actual page origin rather than disabling protections broadly. The timer URL must be accessible to your intended visitors; a private sign-in-only preview will not serve as a public embed.

The app loads its robot artwork, brand logo, and stylesheet normally. Rain/ocean recordings are requested from the same timer host only when selected for playback; generated noise works without audio downloads. There are no analytics or background requests to systeme.io. HTML buttons and menus, rather than any automatic navigation, open pop-out/fullscreen views.

XP and preferences are saved locally per browser/site origin. A new hosting origin will not inherit XP from the old local file or srcdoc embed. Browser policies can restrict persistence inside third-party iframes. If storage is unavailable, the app displays that status in My robot workshop. Opening the timer URL directly is the most reliable way to use its local storage and supported always-on-top mode. Keep the original timer tab open while using a pop-out.

Preserved features: robot themes, clockwise ring, tutorial, missions, one to five evenly spaced Yes/No checks per focus round in main and compact views, sound selection, pause/reset, immediate settings application, stickers, and XP.

Credits
- Robots: Bottts Neutral via DiceBear, based on Bottts by Pablo Stanley; free for personal and commercial use. https://www.dicebear.com/styles/bottts-neutral/ and https://bottts.com/
- Rain: Ove Melaa, CC0. https://opengameart.org/content/rain-ambient-not-loopable-2-versions-available
- Ocean waves: jasinski (submitted by qubodup), CC0. https://opengameart.org/content/beach-ocean-waves

The original source recordings are included; playback normalizes levels and crossfades loops. No third-party media calls are required.

## Branding and robot rewards

Get ADHD Care branding links back to https://www.getadhd.care/. The timer remains at https://focus.getadhd.care/.

Saved XP builds the selected robot: body at 20 XP, arms at 40 XP, and legs at 60 XP. Each completed focus round earns 10 XP. Existing XP applies immediately; resetting a timer keeps XP. The workshop shows unlocked parts and the next milestone.

Grown-up settings support 1–5 check-ins per focus round, or disabling check-ins. Checks appear in the main timer, floating panel, and pop-out. Saving settings resets the current round so the new duration and check-in schedule apply immediately. Delayed background tabs combine already-passed checkpoints into one prompt.

Additional artwork: Get ADHD Care logo supplied by the public brand website; robot body generated with OpenAI image generation for this project. The original DiceBear face credits above continue to apply.

## Validation

Run from the repository root:

```sh
node --check timer.js
node tests/test.cjs
node tests/compact-test.cjs
node tests/rewards-checkins.cjs
```

These automated tests use a simulated browser and timer clock to check timer behavior, compact views, settings, persistence, XP milestones, and multiple check-in schedules.
