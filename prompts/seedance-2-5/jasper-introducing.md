# Jasper — "Introducing" (10s, 16:9)

**Platform: Higgsfield → Seedance 2.5.**

> ## ⚠️ Paste ONLY the fenced block in §1.
>
> Nothing else in this file goes in the prompt box. Not the headings, not the
> explanations, not the section below it. Higgsfield has a single prompt field
> and no negative-prompt field — anything you paste is read as a *request*.

---

## 1. The prompt

Copy everything between the fences. Nothing above it, nothing below it.

```
A calm, high-end product animation on a pure white background, edge to edge, bright and airy, with no gradient and no vignette.

Shot 1, zero to 2.4 seconds: an empty white void. One enormous, extremely soft, very faint grey shadow bleeds in from just beyond the lower right edge of frame, as though a large object were floating just out of shot. The camera pushes in extremely slowly. The frame is otherwise completely empty.

Shot 2, 2.4 to 7.6 seconds: a large white interface panel with softly rounded corners rises smoothly into frame from the lower left, travelling along its own tilted axis, rotated about 8 degrees anticlockwise and angled in perspective so its right edge recedes from camera. Its top strip is a clean empty white bar. A narrow pale grey sidebar, colour #F1F2F5, runs down its left side, divided into plain unmarked rounded shapes. The main body is a weekly schedule grid, seven columns by six rows, filled with small blank rounded rectangles in tints of electric blue #0A6BFF, some solid, some half strength, some very pale, mixed with neutral grey ones. Every surface is smooth and unmarked. The blocks fade in one row at a time, top row first, each row slightly behind the last. The camera pulls back slowly and continuously; the panel shrinks and settles into the right two thirds of frame while the left third of frame stays empty white. The panel carries one large, very soft, low opacity shadow offset down and to the right.

Shot 3, 7.6 to 10 seconds: cut to empty white. Centred in frame, a simple flat vector icon: a dark navy #1E2737 rounded calendar page with a small electric blue circle overlapping its lower right corner, holding a white checkmark. Two concentric pale blue rings, #F0F6FE outer and #E4EDFD inner, expand outward from behind the icon in a slow staggered ripple and hold. The lower third of frame stays empty white. The camera eases to a complete stop and holds perfectly still.

Throughout, every move is a single continuous slow camera drift with heavy ease-out, decelerating over a long tail into a settle, with soft natural motion blur. No bounce, no overshoot, no camera shake. The palette is limited to white, a light grey ramp and one electric blue. Every panel surface is smooth, blank and unmarked.
```

### Settings

Your settings in the screenshot were already correct — keep them:

**10s · 16:9 · 1080p · Bitrate High · Unlimited mode OFF**

Leave the reference/image slot empty. A style reference will fight the pure
white void.

---

## 2. Why the first attempt failed

Worth understanding, because it governs every prompt you write on this platform.

**The whole markdown file went into the prompt box.** The model was handed the
words `together.ai`, `What's on your mind?`, `CHAT`, and a full description of
together.ai's sidebar — so it rebuilt together.ai's interface. It was following
instructions precisely; the instructions were just wrong.

**The negative prompt became a positive one.** Higgsfield exposes no negative
field. The list started `text, words, letters, letterforms, typography,
headline, caption` — which, read as a request, is an order for exactly the
garbled type that came back.

### The rule this gives you

**Never name a thing you do not want.** Video models have no reliable "not"
operator; naming an object tends to summon it whatever word sits in front of it.

So the prompt above never uses the words *text*, *letters*, *words*, *label* or
*logo* even once. Emptiness is described **affirmatively** instead:

| Instead of | Write |
|---|---|
| "no text on the panel" | "every surface is smooth and unmarked" |
| "empty header with no logo" | "its top strip is a clean empty white bar" |
| "grid blocks with no labels" | "small blank rounded rectangles" |
| "no sidebar menu text" | "plain unmarked rounded shapes" |

Motion negations (`no bounce`, `no overshoot`, `no camera shake`) are safe —
those are behaviours, not objects, and won't be rendered as things.

---

## 3. CapCut compositing

The plate comes back with no type on it by design. Every word goes on here,
where the cascade can be controlled to the frame.

**Copy:** `Introducing` → `Jasper [SHIFTS]` → `Simple, instant scheduling` →
`for teams of any size` → `Every shift covered.`

### Type setup

| | |
|---|---|
| Typeface | Helvetica Now Display, Medium. Free substitutes, in order: **Inter Display Medium**, General Sans Medium, SF Pro Display Medium (macOS). |
| Tracking | −2% on headlines. The reference is noticeably tight. |
| Dark | `#333336` |
| Pre-reveal grey | `#D2D2D7` |
| Accent blue | `#0A6BFF` |
| Easing | Custom bezier on every keyframe: **`cubic-bezier(0.22, 1, 0.36, 1)`** (quint-out). If CapCut only offers presets, use "Ease Out" at maximum strength. Never leave anything on Linear. |

### The two-layer trick — grey→dark in CapCut

CapCut cannot animate text colour over time. Reproduce it with **two stacked
copies of the same word**, identical in font, size and position:

1. **Lower layer** — the word in `#D2D2D7`. Fades 0→100% opacity over 0.10s.
2. **Upper layer** — the same word in `#333336`. Starts at 0%, fades to 100%
   over 0.20s, beginning 0.06s after the grey layer.

The grey reads first, the dark resolves over it, and the eye sees a colour
shift. Build one word as a group, then duplicate and re-time for every word.
This single trick is most of the reference's magic.

**Hero-word variant:** same stack, but the lower layer is `#0A6BFF` at 300%
scale, and the upper `#333336` layer fades in only as the group finishes scaling
down — the colour appears to shift blue→dark through the scale move.

### Timeline

Times in seconds against the 10s plate.

| In | Out | Element | Move |
|---|---|---|---|
| 0.15 | 0.78 | `Introducing` | Typewriter, ~17 chars/sec, centred so it grows outward from the middle. Thin caret trailing the last glyph, blinking at 1.5Hz. |
| 0.78 | 1.35 | `Introducing` | Hold. Caret keeps blinking. |
| 1.35 | 1.60 | `Introducing` | Exit: per-glyph scattered dissolve with a touch of blur. Each letter its own layer, fades staggered in **random** order, not left to right. |
| 1.62 | 1.97 | `Jasper` | Typewriter in, same speed and caret. |
| 2.00 | 2.15 | `[SHIFTS]` pill | Rounded pill, fill `#E4EDFD`, label `#0A6BFF`, ~40% of the wordmark's size. Scales 85→100% on quint-out. |
| 2.15 | 2.55 | Wordmark lockup | Hold. |
| 2.55 | 3.30 | Wordmark lockup | **The dock.** Scale to ~28% and travel up-left, landing inside the empty top strip of the incoming panel. Match the panel's 8° tilt as it lands. Scrub the plate to find the frame the strip reaches rest. |
| 3.30 | 6.60 | Wordmark lockup | Parented to the panel — track it with position keyframes as the plate pulls back. |
| 4.30 | 4.85 | `Simple` | Hero-word: enters at 300% scale in `#0A6BFF`, centred in the empty left third. Holds at full size. |
| 4.85 | 5.40 | `Simple` | Scales to 100% on quint-out while the dark layer resolves over the blue. Travels to its place in the line. |
| 5.42 | 5.62 | `, instant` | Cascade in (two-layer trick). |
| 5.55 | 5.75 | `scheduling` | Cascade in, +0.13s behind. |
| 6.10 | 6.30 | `for` | Second line begins, +0.13s per word. |
| 6.23 | 6.43 | `teams` | |
| 6.36 | 6.56 | `of` | |
| 6.49 | 6.69 | `any` | |
| 6.62 | 6.82 | `size` | |
| 6.82 | 7.50 | Both lines | Hold. |
| 7.50 | 7.80 | Both lines | Scattered per-glyph dissolve out. |
| 8.70 | 8.90 | `Every` | End-card line, cascading beneath the icon. |
| 8.83 | 9.03 | `shift` | |
| 8.96 | 9.16 | `covered.` | Land this word in **`#0A6BFF`** and leave it blue — the reference inverts the hero move at the end, keeping its final phrase in accent. |
| 9.16 | 10.00 | All | Hold to end. |

### The reflow question

In the reference the line physically **re-centres** as each word lands — earlier
words slide left to make room. Most laborious part to reproduce, easiest to skip.

- **Simple version:** place every word at its final position and animate opacity
  only. At 0.13s stagger the eye barely registers the missing reflow. Do this first.
- **Faithful version:** add X-position keyframes to each word group, each
  shifting left by half the width of the word that follows, on the same
  quint-out curve. ~40 extra keyframes. Worth it only if the spot matters.

---

## 4. Judging a roll

Check in this order and stop at the first failure — everything below is
invalidated by anything above:

1. Is the background pure white, and the palette only white / grey / one blue?
2. Are all panel surfaces blank — no attempted letterforms anywhere?
3. Does the camera read as one continuous ease-out pull-back, no bounce?
4. Is the left third of frame empty during the settled beat?
5. Is the panel's top strip empty?

Lock the seed as soon as 1–3 pass. Do not start compositing type until 4 passes —
if the panel crowds the left third there is nowhere for the headline to go.

### If it still puts marks on the panel

Swap the grid sentence for a plainer one — fewer nouns give it less to
elaborate on:

```
The main body is a plain grid of small blank rounded rectangles in tints of electric blue #0A6BFF and neutral grey, seven columns by six rows, all surfaces smooth and empty.
```

### If the dock beat has nowhere to land

Drop it. Let the wordmark dissolve on the scatter exit at 1.60s and have the
panel simply rise into a clean frame. You lose the cleverest move in the
reference, but nothing looks broken.
