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

## v1 feedback (2026-09-29), saved as v1.html
> "Way better... we don't need two buttons... remove the button on top of the video... and the words below that
> button... where it says call booked step two, remove that too... remove that logo on the very top, just keep the
> logo on the very bottom... make the headline better... add a little things of like steps... one you booked a call
> check... step two submit the assessment... step three the call's confirmed... make it more premium, but you are
> heading in the right direction."

## v2 (2026-09-29)
- One CTA only, below the video. Top logo and step chip gone; logo lives in the footer.
- H1 "Your call is booked. / *Now let's make it count.*" Sub: "Watch this 36-second video, then fill out your
  onboarding assessment. Three minutes now saves thirty on the call." (last line is the old page's own copy).
- 3-step tracker (01 Call Booked, done, green check / 02 Submit Your Assessment, now, pulsing blue / 03 Call
  Confirmed) inside a dark glass panel with the CTA, same 960px width as the video frame (edges verified equal).
  Mobile: steps go vertical with a rail. Risk line carries the old heads-up ("not done in time, rescheduled").
- First panel pass used the light glass fill and read washed-out blue over the fog; dark fill (#070b17 at .86) fixed it.
- Mobile H1 emphasis orphaned "count."; script line set to .9em at phone width.
