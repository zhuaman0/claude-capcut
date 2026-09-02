# Frame-by-frame teardown — reference animation

Source: `c58ea101-apple_animated_video.mp4`
**19.78s · 30fps · 736×414 (16:9) · h264 · HE-AACv2 audio**

Despite the filename, this is not an Apple video — it is a **together.ai Chat
product demo**. The design language is Apple-keynote-derived (white void,
grotesque type, word-cascade reveals, continuous slow dollies), which is
presumably why it reads as "Apple".

---

## 1. Beat sheet

| Time | Beat | What happens |
|---|---|---|
| 0.00s | Title frame | Single frame: "Product Demo" small above `together.ai` wordmark + blue `CHAT` pill. Clears immediately. |
| 0.12–1.35s | "Introducing" | Types in character-by-character with a thin caret. Scales up as the string lengthens. Holds ~0.5s. |
| 1.35–1.60s | Dissolve out | Per-glyph scattered fade with blur — glyphs leave in random order, not left-to-right. |
| 1.60–2.60s | Wordmark builds | `together.ai` types in the same way; the `.` lands in accent blue; the `CHAT` pill pops in last. Holds. |
| 2.70–4.20s | **Match-dock** | The wordmark stays anchored while a 3D-tilted app window slides up from below and docks its top-left corner to it — the wordmark *becomes* the app header. Sidebar list items cascade in. Camera pulls back continuously. |
| 4.30–6.20s | Composer | Cut to the "What's on your mind?" composer panel, slow push, then pull back to reveal the full window. |
| 6.30–8.35s | **"Private, secure access"** | Hero-word move (see §3). |
| 8.40–11.9s | Model list | Tilted card slides up from lower-left; rows cascade in; headline "to top / open-source / models" builds word-by-word on the left as the card settles right. Camera pulls back. |
| 12.0–13.0s | Reset | Pull back to the composer, then cut to macro. |
| 13.0–15.2s | Typing | `Explaine quantum physics like I'm 10 years old` types in at macro scale; camera tracks right as the line overflows frame. *(The typo "Explaine" is in the original.)* |
| 15.3–16.4s | Send button | Macro on the paperclip + blue circular send button. Slow scale pulse from camera dolly. **No cursor, no hand, no click.** |
| 16.5–19.8s | End card | Cut to a server-stack + shield icon over `together.ai`; two pale-blue halo rings expand outward; "Models served from / data centers hosted in / the U.S. & Canada" cascades in, final phrase landing in blue. Holds to end. |

---

## 2. Colour space

Sampled from decoded frames (h264 lifts blacks slightly; intent values in brackets).

| Role | Value | Notes |
|---|---|---|
| Background | `#FFFFFF` | Pure white, edge to edge. Never off-white, never a gradient. |
| Body / headline text | `#333336` → intent `#1D1D1F` | Near-black warm grey, never pure black. |
| **Pre-reveal grey** | `~#D2D2D7` | The state every word starts in before it darkens. This is the single most important colour in the piece. |
| Accent blue | `#0A6BFF` | Sampled `#0869FF`–`#106EFF`. Electric, bluer than Apple's `#0071E3`. |
| Panel fill (sidebar, composer) | `#F1F2F5` | |
| Panel fill (light/raised) | `#F6F7FA` | |
| Halo ring outer | `#F0F6FE` | End card only. |
| Halo ring inner | `#E4EDFD` | End card only. |
| Illustration navy | `#1E2737` | Server icon only. |

There is **no black anywhere**, no saturated colour other than the single blue,
and no second accent. The entire palette is white + one grey ramp + one blue.

Type is a geometric-humanist grotesque (Helvetica Now / SF Pro family), medium
weight for headlines, tight tracking, regular weight for UI copy.

---

## 3. Text motion mechanics — the signature

Three distinct moves, used consistently. This is what makes the piece read as
"expensive", and it is the part worth reproducing exactly.

### 3a. Typewriter build
Character-by-character at roughly **16–20 chars/sec**, thin vertical caret
trailing the last glyph. The line is **horizontally centred**, so it grows
outward from the centre in both directions rather than left-to-right. Apparent
scale eases *up* as the string lengthens. Used for "Introducing", the wordmark,
and the long prompt at 13s.

### 3b. Word cascade (used everywhere — headlines AND UI copy)
The core mechanic:

1. A word fades in at **`#D2D2D7` light grey**.
2. Over ~**0.2s** it darkens to `#333336`.
3. The next word begins ~**0.12–0.15s** later, overlapping.
4. The whole line **reflows and re-centres** as each word lands.

Watch 7.42s: `Private, secure` — "secure" is still light grey.
Watch 7.55s: `Private, secure access` — "secure" has darkened, "access" is now
the grey one. The grey state is always exactly one word ahead.

Critically, the *same* cascade is applied to UI text inside the 3D cards
(8.6–9.3s: "Full R1, / uses / advanced / reasoning" arriving in stages). That
consistency between headline type and interface copy is what unifies the piece.

### 3c. Hero-word move
Reserved for one word per section:

1. Word flies in **oversized** (≈3× final size) in **accent blue**.
2. Holds at full size ~0.4s.
3. Scales down on a long ease-out **while colour-shifting blue → near-black**,
   travelling to its final position in the sentence.
4. The rest of the sentence then cascades in around it (§3b).

Seen on "Private" (6.3→7.3s). The end card inverts it: the *final* phrase
("the U.S. & Canada") lands and **stays** blue.

### 3d. Exit
Per-glyph scattered dissolve with directional blur, ~0.25s. Glyphs leave in
pseudo-random order, not in reading order.

---

## 4. Camera and easing

- **One continuous move per beat.** Cuts happen *between* beats, never during.
  Every beat is a single slow dolly — almost always a **pull-back**.
- **Easing is heavy ease-out**: fast start, very long deceleration, settle.
  Nothing linear. Notably there is **no overshoot and no bounce** — this is
  Apple-style smooth deceleration, not springy motion-graphics bounce.
- **Real motion blur** on every fast move (clearly visible at 0.62s and 8.43s).
- 3D cards sit at roughly **−8° to −10° roll** with a slight Y-axis rotation so
  the far edge recedes. They slide in from the lower-left along their own tilted
  axis, not straight up.
- Shadows are large, very soft, low-opacity, and offset down-right. No hard
  edges, no ambient occlusion contact shadow.

---

## 5. Implications for a Seedance 2.5 remake

The uncomfortable part: **this reference is ~40 discrete words of pixel-perfect
kinetic type across 19.8 seconds.** That is precisely the workload current video
models are worst at. Specifically:

- Seedance 2.5 caps out around 10–12s, so a like-for-like needs **2–3 stitched
  generations**.
- The word-cascade grey→black mechanic requires *per-word opacity control*. A
  video model has no such control — it will approximate it as a general fade.
- The typewriter beat requires stable, correctly-spelled glyphs across ~60
  frames. Seedance drifts glyphs between frames on strings past ~20 characters.
- The hero-word blue→black colour shift while scaling is a compound transform;
  models tend to pick one and drop the other.

What Seedance *is* genuinely good at here: the white void, the soft-shadowed
3D-tilted panels sliding through space, the continuous pull-back dolly, motion
blur, and the overall light/airy colour space. Those are the parts to ask it for.

The realistic production route is therefore a **hybrid**: generate the camera
moves, the void, and the floating 3D UI panels in Seedance; composite the
kinetic type in CapCut where the cascade timing can be controlled to the frame.
