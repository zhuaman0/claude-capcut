# Jasper — "Introducing" (10s, 16:9)

A condensed remake of the together.ai reference in Jasper's brand, built as a
**hybrid**: Seedance renders the void, the floating 3D roster panel, the camera
moves and the motion blur — **all kinetic type is composited in CapCut**, where
the word-cascade can be controlled to the frame.

Read [`reference/together-ai-teardown.md`](../../reference/together-ai-teardown.md)
first — this document assumes its colour values and motion mechanics.

**Copy:** `Introducing` → `Jasper [SHIFTS]` → `Simple, instant scheduling` →
`for teams of any size` → `Every shift covered.`

---

## Part 1 — Seedance 2.5

### Settings

| Setting | Value |
|---|---|
| Model | Seedance 2.5 |
| Aspect ratio | 16:9 |
| Duration | 10s |
| Resolution | 1080p minimum, 2K preferred (you are compositing type over this) |
| Frame rate | 30 fps if offered, to match the reference cadence and simplify frame-aligning the type |
| Reference image | None. A style reference will fight the pure-white void. |
| Seed | Lock as soon as the panel move reads correctly. |

### PASTE-READY PROMPT

---

**GLOBAL STYLE (all shots):** Clean product-marketing animation on a **pure
white background (#FFFFFF), edge to edge, no gradient, no vignette, no texture.**
Bright, airy, high-key. The only colours in frame are white, a light grey ramp
(#F1F2F5 panel fills, #D2D2D7 mid grey, #333336 dark grey) and a single electric
accent blue (#0A6BFF). **No black anywhere. No second accent colour. No warm
tones.** Objects are flat 2.5D interface panels — crisp rounded rectangles with
24px corner radii — floating in empty white space, each carrying a large, very
soft, low-opacity drop shadow offset down and to the right, with no hard edges
and no contact shadow. Shallow depth of field with gentle falloff at the frame
edges. Subtle natural motion blur on every fast move.

**CRITICAL — NO READABLE TEXT ANYWHERE IN FRAME.** All interface copy is
rendered as tiny abstract grey marks and dashes, far too small to read, pure
visual texture only. No headlines, no words, no letterforms, no numbers, no
logos, no watermarks at any size.

**MOTION LANGUAGE:** Every move is one continuous slow camera drift with heavy
ease-out — fast at the start, decelerating over a long tail, settling to a stop.
**No bounce, no overshoot, no springiness, no camera shake, no handheld, no
whip pans, no linear robotic motion.** The feeling is a calm, expensive Apple
keynote, not energetic motion graphics.

**SHOT 1 (0.0–2.4s) — Empty plate.**
An empty pure-white void. A single enormous, extremely soft, very faint grey
shadow bleeds in from just beyond the lower-right edge of frame, as though a
large object is floating out of shot, breathing almost imperceptibly. The camera
pushes in extremely slowly. Nothing else in frame. Calm, patient, minimal.

**SHOT 2 (2.4–7.6s) — The roster panel.**
A large white interface panel with softly rounded corners rises smoothly into
frame from the lower left, travelling along its own tilted axis. It is rotated
roughly 8 degrees anticlockwise and angled slightly in perspective so its right
edge recedes away from camera. **The panel's top-left header bar is completely
empty — a clean blank white strip with nothing in it.** Down the left of the
panel runs a narrow light grey sidebar (#F1F2F5). The main body is a weekly
schedule grid: seven vertical columns crossed by horizontal rows, filled with
small rounded rectangular blocks in varying tints of the accent blue — some
solid #0A6BFF, some at half strength, some pale, interspersed with neutral grey
blocks. The blocks fade in one row at a time in a staggered cascade, top row
first, each row a fraction behind the last. The camera pulls back slowly and
continuously throughout, the panel shrinking and settling into the right two
thirds of frame. **The entire left third of frame stays completely empty white.**
In the final second the panel drifts gently up and to the left, beginning to
leave frame, with soft motion blur trailing it.

**SHOT 3 (7.6–10.0s) — End card.**
Cut to empty white. Centred in frame, a simple flat vector icon assembles: a
dark navy (#1E2737) calendar page with softly rounded corners, a small circular
accent-blue (#0A6BFF) badge overlapping its lower-right corner carrying a white
checkmark. Two concentric pale blue rings (#F0F6FE outer, #E4EDFD inner) expand
outward from behind the icon in a slow, smooth, staggered ripple and hold. The
lower third of frame stays completely empty white. The camera eases to a
complete stop and holds perfectly still on the final composition.

---

### NEGATIVE PROMPT

```
text, words, letters, letterforms, typography, headline, caption, subtitle,
readable text, large text, numbers, logo, wordmark, watermark, signature,
black, dark background, off-white background, cream, beige, gradient
background, vignette, second accent color, orange, green, red, purple,
saturated colors, neon, harsh shadows, hard shadow edges, contact shadow,
3D render, glossy, metallic, glass, reflections, camera shake, handheld,
jitter, bounce, overshoot, springy motion, whip pan, zoom burst, glitch,
lens flare, film grain, noise, low resolution, cluttered, busy composition,
people, hands, cursor, mouse
```

> **Why the type is banned outright.** The word-cascade is the whole aesthetic,
> and it requires per-word opacity control that Seedance has no way to express.
> Asking for the type and getting an approximation is worse than asking for
> nothing, because you cannot composite clean type over garbled model text — you
> would have to mask it out. A clean plate is worth far more than a lucky roll.

---

## Part 2 — CapCut compositing

### Type setup

| | |
|---|---|
| Typeface | Helvetica Now Display, Medium. Free substitutes, in order: **Inter Display Medium**, General Sans Medium, SF Pro Display Medium (macOS). |
| Tracking | −2% on headlines. The reference is noticeably tight. |
| Dark | `#333336` |
| Pre-reveal grey | `#D2D2D7` |
| Accent blue | `#0A6BFF` |
| Easing | Custom bezier on every keyframe: **`cubic-bezier(0.22, 1, 0.36, 1)`** (quint-out). If CapCut only offers presets, use "Ease Out" at maximum strength. Never leave anything on Linear. |

### The two-layer trick — how to get grey→dark in CapCut

CapCut cannot animate text colour over time. Reproduce it with **two stacked
copies of the same word**, identical in font, size and position:

1. **Lower layer** — the word in `#D2D2D7`. Fades 0→100% opacity over 0.10s.
2. **Upper layer** — the same word in `#333336`. Starts at 0%, fades to 100%
   over 0.20s, beginning 0.06s after the grey layer.

The grey reads first, the dark resolves over it, and the eye sees a colour
shift. Build one word as a group, then duplicate and re-time it for every word
in the piece. This single trick is most of the reference's magic.

**Hero-word variant:** same stack, but the lower layer is `#0A6BFF` at 300%
scale, and the upper `#333336` layer fades in only as the group finishes scaling
down. The colour appears to shift blue→dark through the scale move.

### Timeline

Times in seconds against the 10s Seedance plate.

| In | Out | Element | Move |
|---|---|---|---|
| 0.15 | 0.78 | `Introducing` | Typewriter, ~17 chars/sec, centred so it grows outward from the middle. Thin caret trailing the last glyph, blinking at 1.5Hz. |
| 0.78 | 1.35 | `Introducing` | Hold. Caret keeps blinking. |
| 1.35 | 1.60 | `Introducing` | Exit: per-glyph scattered dissolve with a touch of blur. Set each letter as its own layer and stagger the fades in **random** order, not left to right. |
| 1.62 | 1.97 | `Jasper` | Typewriter in, same speed and caret. |
| 2.00 | 2.15 | `[SHIFTS]` pill | Small rounded pill, fill `#E4EDFD`, label `#0A6BFF` at ~40% of the wordmark's size. Scales 85→100% on quint-out. |
| 2.15 | 2.55 | Wordmark lockup | Hold. |
| 2.55 | 3.30 | Wordmark lockup | **The dock.** Scale down to ~28% and travel up-left, landing exactly inside the empty header bar of the incoming Seedance panel. Match the panel's 8° tilt as it lands. Time this against the plate — scrub to find the frame the header bar reaches its resting position. |
| 3.30 | 6.60 | Wordmark lockup | Parented to the panel. Track it manually with position keyframes as the plate pulls back. |
| 4.30 | 4.85 | `Simple` | Hero-word: enters at 300% scale in `#0A6BFF`, centred in the empty left third. Holds at full size. |
| 4.85 | 5.40 | `Simple` | Scales to 100% on quint-out while the dark layer resolves over the blue. Travels to its final position in the line. |
| 5.42 | 5.62 | `, instant` | Cascade in (two-layer trick). |
| 5.55 | 5.75 | `scheduling` | Cascade in, +0.13s behind the previous word. |
| 6.10 | 6.30 | `for` | Second line begins cascading, +0.13s per word. |
| 6.23 | 6.43 | `teams` | |
| 6.36 | 6.56 | `of` | |
| 6.49 | 6.69 | `any` | |
| 6.62 | 6.82 | `size` | |
| 6.82 | 7.50 | Both lines | Hold. |
| 7.50 | 7.80 | Both lines | Scattered per-glyph dissolve out. |
| 8.70 | 8.90 | `Every` | End-card line, cascading beneath the icon. |
| 8.83 | 9.03 | `shift` | |
| 8.96 | 9.16 | `covered.` | Land this word in **`#0A6BFF`** and leave it blue — the reference inverts the hero move at the end and keeps its final phrase in accent. |
| 9.16 | 10.00 | All | Hold to black. |

### The reflow question

In the reference, the line physically **re-centres** as each word lands — the
earlier words slide left to make room. It is the most laborious part to
reproduce and the easiest to skip.

- **Simple version:** place every word at its final position from the start and
  animate opacity only. At 0.13s stagger the eye barely registers the missing
  reflow. Do this first.
- **Faithful version:** add X-position keyframes to each word group, each
  shifting left by half the width of the word that follows it, on the same
  quint-out curve. Roughly 40 extra keyframes for this piece. Worth it only if
  the spot is going somewhere that matters.

Do the simple version, watch it against the reference, and upgrade only if the
difference bothers you.

---

## Risk points and fallbacks

**1. The dock beat (2.55–3.30s) is the hard one.** It only works if Seedance
delivers a genuinely empty header bar and a predictable settle position. If the
plate comes back with the panel arriving at the wrong place or the header
occupied:

- *Fallback A:* drop the dock entirely. Let the wordmark dissolve out on the
  scatter exit, and have the panel simply rise into a clean frame. You lose the
  cleverest move in the reference but nothing looks broken.
- *Fallback B:* generate Shot 2 alone, several times, and pick the roll whose
  panel settles furthest right — that gives you the most room to land the
  wordmark and the widest empty left third.

**2. Seedance will probably sneak text into the panel anyway.** Small
grey marks are what you want; actual attempted letterforms are not. If it
produces legible garbage, re-roll rather than mask — the negative prompt is
already heavy, so add `interface text, UI labels, menu items` to it and try
again.

**3. The empty left third.** Models drift toward centred compositions. If the
panel lands too central and crowds the headline, either re-roll or accept it and
move the headline to sit *above* the panel instead of beside it. Check this
before you build any type.

**4. Shot 1 is 2.4s of near-empty white.** That is deliberate — it is a clean
plate for the opening type. If a roll wastes it or puts something ugly in it,
just freeze a clean white frame in CapCut and extend it; you lose nothing.

## Iteration order

Judge each roll in this order and stop at the first failure — everything below
is invalidated by anything above it:

1. Is the background pure white and the palette confined to white / grey / one blue?
2. Does the camera move read as one continuous ease-out pull-back, with no bounce?
3. Is the left third of frame empty during the settled beat?
4. Is the panel header bar empty?
5. Is all interface text illegible texture rather than attempted letterforms?

Fix one, lock the seed, re-roll. Do not start compositing type until 1–3 pass.
