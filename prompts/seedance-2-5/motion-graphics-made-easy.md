# Seedance 2.5 — "Motion Graphics Made Easy" (10s, multi-shot)

Light neumorphic aesthetic, pastel bloom, off-white void. A prompt bar expands,
gets typed into, gets clicked, launches into the abyss, and blooms into floating
UI cards that settle into a calm hero frame.

## Generation settings

| Setting | Value |
|---|---|
| Model | Seedance 2.5 |
| Aspect ratio | 16:9 |
| Duration | 10s |
| Resolution | 1080p (2K if available) |
| Frame rate | 24 fps |
| Reference image | Attach the neumorphic button reference as a **style reference**, strength ~0.5–0.6. Do **not** use it as a locked first frame — it would pin the camera to that exact composition. |
| Seed | Lock the seed once you get a good take, then iterate one shot at a time. |

---

## PASTE-READY PROMPT

> Copy everything between the rules into the prompt field as one block.

---

**GLOBAL STYLE (applies to all shots):** Premium 3D motion-design render, soft
neumorphism. Clean off-white studio background (#F1F1EF) with a faint pale
dot-grid texture on the right third of frame. All objects are matte porcelain
white (#FCFCFC) with generously rounded corners, lit by a single large soft key
light from the upper left, casting long, low-opacity, heavily blurred shadows.
A gentle pastel chromatic bloom hugs every object edge — lilac (#DED0EE), blush
pink (#F6D7E4), powder blue (#CFE0F5) — like light refracting through frosted
glass. All icons, cursors and text are muted mauve (#B7A6C4). Shallow depth of
field, 50mm lens, delicate film grain, airy and bright, no pure black anywhere,
no harsh contrast. **Motion language:** the easing of a professional motion
designer — smooth ease-in-out, slight overshoot and settle on every move,
staggered timing between elements, no linear robotic movement, no camera shake,
no jitter.

**SHOT 1 (0.0–2.5s) — The bar expands.**
Macro close-up, dead center: a small porcelain-white pill-shaped button floats a
few millimetres above an off-white surface, soft blurred shadow pooled beneath
it. It smoothly stretches outward along the horizontal axis into a wide rounded
prompt bar, overshooting slightly then settling, its edges catching a lilac and
powder-blue bloom as it grows. The camera dollies slowly backward and tilts
slightly up to reveal the full bar. A slim mauve text cursor fades in at the
left inner edge of the bar and blinks once.

**SHOT 2 (2.5–5.2s) — The typing.**
Cut to a tighter three-quarter macro angle across the interior of the prompt
bar. Text types itself in one character at a time in a clean geometric
sans-serif, large and crisp and correctly spelled, muted mauve on white, on a
single line: "motion graphics made easy... how?". The blinking cursor advances
with each character at a natural human typing rhythm. The camera drifts slowly
to the right, tracking the text as it fills the bar, shallow focus falling off
at both ends, the soft shadow shifting gently beneath.

**SHOT 3 (5.2–7.0s) — The click.**
Cut to extreme macro on the right end of the prompt bar: a circular porcelain
send button with a mauve arrow icon pointing up and to the right, ringed in
pastel bloom. In the soft-focus foreground, a single realistic human hand rests
on a matte-white ergonomic mouse. The index finger presses down once, slowly and
deliberately. In perfect sync, the send button depresses into its recess, the
pastel bloom flares brighter, and a soft ring of light ripples outward across
the surface.

**SHOT 4 (7.0–10.0s) — Launch and bloom.**
Cut to a wide shot. The entire prompt bar rockets away from camera into an
infinite white void, shrinking to a vanishing point trailing motion-blurred
streaks of lilac and blue light. Instantly, floating neumorphic UI cards bloom
outward from that vanishing point toward camera in staggered waves: a video
timeline panel with pastel clip blocks, a large rounded play button, a curved
slider control, a circular progress dial. All porcelain white with soft shadows
and pastel edge bloom, all surfaces blank with no readable text. They fan
outward, decelerate with elegant easing, and settle into a calm, balanced,
gently breathing composition floating in the light. The camera eases to a full
stop and holds on the final still hero frame.

---

## NEGATIVE PROMPT

```
garbled text, misspelled words, gibberish letters, text on UI cards, extra
fingers, deformed hands, mutated fingers, dark background, black, high contrast,
saturated colors, neon, harsh shadows, glitch, camera shake, handheld, jitter,
linear robotic motion, whip pans, lens flare, watermark, logo, low resolution,
noise, distorted UI, cluttered composition, stock footage look
```

---

## Known risk points and fallbacks

Three things in this shot list are where Seedance 2.5 most often breaks. Fixes,
in the order I'd try them:

**1. The typed string (Shot 2) — highest risk.**
`motion graphics made easy... how?` is 33 characters including an ellipsis and a
question mark. Seedance renders short, large, high-contrast strings well and
degrades fast past ~25 characters, and punctuation clusters like `...` often come
out as a smear.

- *Fallback A:* shorten to `motion graphics made easy` and let the question live
  in the edit (a title card, or VO).
- *Fallback B:* split it — Shot 2 types `motion graphics made easy`, then a beat,
  then `how?` appears alone on a second line. Two short strings beat one long one.
- *Fallback C (most reliable):* generate Shot 2 with the bar **empty** and only
  the cursor blinking, then composite the typing on in CapCut with a typewriter
  text animation. This also gives you exact control over the timing and font.

**2. The hand on the mouse (Shot 3) — second highest risk.**
Hands are the weakest subject in every current video model. If the take comes
back with finger artifacts, swap the Shot 3 hand sentence for:

> In the soft-focus foreground, a single human index fingertip enters frame from
> the lower right and taps the button once. Only the fingertip and first knuckle
> are visible; the rest of the hand is out of frame.

Less visible anatomy means less to get wrong. If that still fails, drop to a
cursor-only version: *"A mauve arrow cursor glides in with smooth easing and
presses the button, which depresses under it."*

**3. Four cuts in ten seconds.**
Each shot averages 2.5s, which is tight for Seedance's shot coherence. If the
result feels rushed or the model bleeds one shot into the next, merge Shots 1
and 2 into one continuous 5.2s move — the bar expands and the camera keeps
pushing in as the text types, no cut. That buys the launch beat more room, which
is the shot that actually sells the piece.

## Iteration order

Do not re-roll the whole 10s when one beat is wrong. Generate, then judge in this
order — each item invalidates the ones below it:

1. Does the overall look match the reference? (If not, raise style-reference strength before touching the prompt.)
2. Does Shot 4 land — do the cards bloom outward and *settle*, or do they keep drifting?
3. Is the text legible and correctly spelled?
4. Is the hand clean?

Fix one, lock the seed, re-roll.
