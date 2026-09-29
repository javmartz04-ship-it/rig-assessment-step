# RIG · Post-booking assessment step (v1, 2026-09-29)

**Brief (Javier, verbatim-ish):** redo realinsurancecrm.com/assessment-form ("garbage"). Headline + subheadline +
a button that pops up the form. "Take out that bullshit box he made on the video, put a play button, automatically
plays in the background, but when they press play it restarts the video." Page = after they book: "one more step".

**Built:** same skin as the approved specialist booking page v10 (night #04070f + blue fog + grain, Questrial /
Quintessential script emphasis / JetBrains Mono, one blue gradient). Centered stack: step chip (Call Booked | Step 2
of 2) → H1 "You're booked. One more step / *before we talk.*" → sub → "Complete My Assessment" → video → same CTA
repeated → heads-up note (kept from the live page's content) → original disclaimer footer.

- **Video:** GHL media mp4 (assets.cdn.filesafe.space/.../6abb102cf6972e3b5225ecb5.mp4), autoplay muted loop,
  no native controls. Glass play button; click = currentTime 0, unmuted, loop off. After that, clicking the picture
  pauses/resumes; thin blue progress line. When it ends, the form modal opens.
- **Form:** GHL survey `lq6V9oxbZIH8Hfw3TSkG`, iframe byte-for-byte from the live page, in a modal (opacity/
  visibility, never display:none, so form_embed.js can size it). Verified: loads, resizes to 842px, video pauses.
- The removed "box" = the old page's form card + native controls bar. The live page's old step card is gone.

**Craft bug caught:** the video has burned-in captions along the bottom; a bottom-anchored "Tap to watch" label
collided with them. Label now sits under the play button.

**Preview:** https://javmartz04-ship-it.github.io/rig-assessment-step/ (repo javmartz04-ship-it/rig-assessment-step)
**Open:** Javier's reaction; GHL paste version (scope under #rig like the booking page) once approved.
