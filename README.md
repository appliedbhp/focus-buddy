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

Music uses three official Suno embedded players: Loft Apartment View, Smooth Getaway, and Quiet Revision. The previous nature recordings and generated noise have been removed. Music requires internet access and uses the Suno player's own play, pause, and volume controls. Timer pause and mute affect the timer/chimes only, not the third-party music player.

XP and preferences are saved locally per browser/site origin. A new hosting origin will not inherit XP from the old local file or srcdoc embed. Browser policies can restrict persistence inside third-party iframes. If storage is unavailable, the app displays that status in My robot workshop. Opening the timer URL directly is the most reliable way to use its local storage and supported always-on-top mode. Keep the original timer tab open while using a pop-out.

Preserved features: robot themes, clockwise ring, tutorial, missions, one to five evenly spaced Yes/No checks per focus round in main and compact views, sound selection, pause/reset, immediate settings application, stickers, and XP.

Credits
- Robots: Bottts Neutral via DiceBear, based on Bottts by Pablo Stanley; free for personal and commercial use. https://www.dicebear.com/styles/bottts-neutral/ and https://bottts.com/


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

The pop-out and floating panel display an XP bar with earned/required XP and locked/unlocked indicators for all three robot parts. Parts continue unlocking automatically at 20, 40, and 60 XP; XP is not spent.

## Monster Builder update

Characters now use Kenney's Monster Builder Pack (CC0). The included license is in assets/monsters/License.txt. Choose Bubbles (blue), Sprout (green), or Sunny (yellow). Each starts with a complete body and face. The workshop offers optional ears at 20 XP, horns at 40 XP, and antennas at 60 XP. Choose one feature or the simple starter look. Features unlock with lifetime XP and do not spend it. Existing browser XP and settings are preserved; the chosen feature is saved too.

This replaces the previous robot artwork and robot body/arms/legs progression described above. Music and check-in behavior are unchanged.

Buddy selection now generates three distinct body shapes with randomized limbs, eyes, and mouths whenever the picker opens. Meet three more rerolls the choices. Choosing a buddy saves its exact design; rerolling or reloading does not alter the selected companion.

Adventure team: eight Kenney Roguelike recruits unlock at 0–140 lifetime XP in 20 XP steps. Recruiting and renaming do not spend XP. Names and the active recruit are saved in existing browser storage. Selecting a monster returns to the monster companion; reset buddy preserves the roster. CC0 license included in assets/team/License.txt.

Character reveals use the user-provided Free/Part 1/13.png sprite sheet. The brief, silent effect plays when choosing a monster, recruiting or equipping a teammate, or equipping a monster feature. Reduced-motion preferences disable it.
