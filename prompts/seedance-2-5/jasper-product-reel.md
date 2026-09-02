# Jasper — "Product Reel" (10s, 16:9)

**Platform: Higgsfield → Seedance 2.5.**

Fast-cut 3D product hype reel. Warm orange rim light on near-black, a tumbling
phone, and huge two-tone spec callouts that punch down from overscan.

> ## ⚠️ Paste ONLY the fenced block in §1.
>
> Nothing else in this file goes in the prompt box. Higgsfield has a single
> prompt field and no negative-prompt field — anything you paste is read as a
> *request*.

**Subject assumption:** the reference is a hardware ad, so this is written as a
phone *running Jasper* — same style, feature callouts instead of hardware specs.
It keeps the physical object the style depends on. §5 covers swapping it.

---

## 1. The prompt

```
A high-energy cinematic 3D product advertisement. Deep warm near-black background, a dark brown-black #1A0E07 with a soft orange radial glow behind the subject and heavy vignetting at the frame edges. The subject is a sleek modern smartphone in burnt copper orange, lit by strong warm orange rim light raking along its edges against the darkness, with glossy specular highlights, shallow depth of field and a soft lens bloom. The phone rotates and tumbles slowly and continuously in the air throughout and is never still.

TEXT ACCURACY IS THE SINGLE MOST IMPORTANT REQUIREMENT OF THIS VIDEO. Every word of on-screen text must be spelled exactly as written below, in sharp, clean, perfectly legible uppercase letterforms, with no distortion, no warping, no extra letters, no missing letters and no invented words. The only words that appear anywhere in this video are: SMART ROSTER, AI POWERED, TEAM SYNC, JASPER.

All text is set in a heavy bold condensed uppercase sans-serif with very tight leading, stacked on two lines, the first line in pure white #FFFFFF and the second line in vivid orange #F98200.

Shot 1, zero to 2.6 seconds: the phone tumbles slowly, seen from behind at an angle, its camera module catching the orange rim light. The word "SMART" in white sits above the word "ROSTER" in orange. They begin enormously oversized, far larger than the frame so only parts of the letterforms are visible, then scale down rapidly and smoothly over half a second until they sit small and razor sharp in the upper left of frame, where they hold, drifting very slightly larger as the phone keeps turning.

Shot 2, 2.6 to 5.2 seconds: hard cut. The phone now lies at a low angle, edge on to camera, rim light raking across its metal frame. The word "AI" in white sits beside the word "POWERED" in orange. They enter enormously oversized, overflowing the frame, then scale down rapidly to sit centred and razor sharp in the middle of frame, holding as the phone rotates slowly beneath them.

Shot 3, 5.2 to 7.8 seconds: hard cut. Extreme close-up on the phone's side edge and buttons, the metal frame glowing with orange rim light, and the camera pulls back smoothly as the phone turns. The word "TEAM" in white sits above the word "SYNC" in orange. They enter enormously oversized and scale down rapidly to sit razor sharp in the lower left of frame.

Shot 4, 7.8 to 10 seconds: hard cut to near-black. The phone drifts slowly away into the darkness. The single word "JASPER" in heavy bold white uppercase scales down from enormously oversized and settles perfectly centred in frame, holding sharp and completely still, a soft orange glow blooming behind it.

Throughout, the cuts are hard and fast with no dissolves and no fades between shots, the camera moves constantly with slow drifting pushes and rotations, and every piece of text enters at enormous scale and snaps down quickly on a smooth ease-out into a small, crisp, perfectly legible resting position.
```

### Settings

**16:9 · 10s · 1080p · Bitrate High · Unlimited mode OFF**

Leave the reference/image slot empty.

---

## 2. Why this one can keep its text

Worth being explicit, because it reverses the advice on the other two prompts in
this repo. Text rendering is not uniformly hard — it fails on a specific
profile, and this reference sits at the opposite end of every axis:

| | The UI prompt that failed | This reel |
|---|---|---|
| Size | Tiny, interface scale | **Enormous, fills the frame** |
| Weight | Regular | **Heavy bold condensed** |
| Case | Mixed case | **All uppercase** |
| Length | 20–35 characters | **4–8 characters per word** |
| Contrast | Grey on white | **White and orange on near-black** |
| Duration | Typing, changing every frame | **Held static ~1s** |

Big, bold, short, high-contrast, uppercase and *stationary* is the reliability
envelope. Every callout here is inside it. You should expect this to work.

The instruction line you asked for is the second paragraph of the prompt, in
capitals, stating the requirement and then **listing the exact permitted
strings**. That enumeration matters more than the demand: it closes off the
model's freedom to invent words, which is the actual failure mode — garbled text
is almost always the model filling space it thinks needs filling.

---

## 3. Teardown of the reference

`563d061d-iphone_animation.mp4` — **15.74s · 30fps · 736×414 (16:9)**. An iPhone
17 spec-drop reel ending on a gold "SMG" logo.

**Palette** (sampled): ground is a warm dark brown-black, `#030100` at its
deepest through `#231409` in the glow; accent orange `#F98200` (samples
`#F97A00`–`#FB8A03`); text white `#FFFFFF`; product body burnt copper
`#AC4B33`–`#BF5E46`. Warm throughout — there is no neutral black in it.

**The text move**, frame-by-frame at 4.4–5.6s: the cut lands *while the text is
already mid-move*, letterforms so oversized only fragments are on screen
(`STEA` / `BLAC`). It scales down hard over ~0.5s, reaches legible size at 4.9s,
keeps shrinking to a small resting position by 5.1s, then holds in the corner
while the phone rotates in. At the end of the beat it scales back *up* and blows
out of frame as the next cut hits. So each beat is: **punch down → hold → punch
out.**

**Two-tone structure:** every callout is stacked on two lines with the first in
white and the second in orange — `SMART`/`ACTION BUTTON`, `CAMERA`/`CONTROL`,
`80W`/`CHARGING`, `PRO MOTION`/`DISPLAY`. Consistent enough to be a rule.

**Cut rhythm:** ~1.2–1.5s per beat, roughly 7 beats in 15.7s, hard cuts only, no
dissolves. This 10s version uses **4 beats at ~2.6s** — slower than the
reference on purpose, since holding each word longer is the cheapest way to buy
text reliability. Speed it up once you know the strings render.

**Colour breaks:** the reference punctuates the orange with a black beat
(4.4–5.6s), a red one (6.0s) and a magenta one (6.5s). Worth stealing later if
you extend this — it stops the orange becoming monotonous.

---

## 4. Judging a roll

1. Are all four strings spelled correctly — `SMART ROSTER`, `AI POWERED`,
   `TEAM SYNC`, `JASPER`? Check every frame they are on screen, not just the
   held frame; letters sometimes drift mid-move.
2. Do the callouts actually **punch down from overscan**, or do they just fade
   in? The scale-down is the signature — a fade is a different, cheaper ad.
3. Are the cuts hard, with no dissolves?
4. Is the ground warm brown-black rather than neutral grey, with the orange glow
   behind the phone?
5. Is the phone moving continuously in every shot?

### If a word garbles

In order:

**Re-roll two or three times first.** At this size and weight it is high
variance, not reliably broken.

**Then shorten the offender.** Every word here can lose characters:
`AI POWERED` → `AI POWER`, `SMART ROSTER` → `ROSTERS`, `TEAM SYNC` → `SYNC`.
Shorter is dramatically more reliable, and at this scale a single word reads as
confident rather than sparse.

**Then cut to three beats.** Drop shot 3 and give the remaining callouts ~3.3s
each. Longer holds mean more frames of stable text and fewer chances to drift.

**Last resort, drop to one string.** Keep only `JASPER` on the end card and
composite the three feature callouts in CapCut. They are static two-line lockups
in the corners — no tracking needed, just a scale keyframe on a quint-out curve
to reproduce the punch-down.

---

## 5. Swapping the subject

The style needs a physical object to rim-light and tumble; that is what carries
it. If you would rather not centre a phone:

- **A laptop** — same treatment, more "workforce software", less consumer.
- **A floating glass panel** showing a roster grid — abstract, keeps the light
  language, no hardware association. Replace "sleek modern smartphone in burnt
  copper orange" with "a thin floating rectangular glass panel with softly
  glowing orange edges".
- **Pure typography** — drop the object, keep the darkness, the glow and the
  punch-down text. Simplest and the most reliable of the three, but the reel
  loses the thing the camera is orbiting.

Swapping the accent from orange to Jasper's blue also works — change `#F98200`
to `#0A6BFF` and the ground from `#1A0E07` to a cool near-black `#07101A`. Keep
the rim light matched to the accent or the warmth fights the brand.
