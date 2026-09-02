# Jasper — "Systems" (10s, 16:9)

**Platform: Higgsfield → Seedance 2.5.**

Black-and-white wireframe network ad. One continuous camera move, no cuts. A
fixed HUD frame around a canvas that never stops moving.

> ## ⚠️ Paste ONLY the fenced block in §1.
>
> Nothing else in this file goes in the prompt box. Higgsfield has a single
> prompt field and no negative-prompt field — anything you paste is read as a
> *request*.

---

## 1. The prompt

```
A high-contrast black and white motion graphics advertisement. Pure black background, #000000, filling the entire frame. Everything is drawn as crisp hairline white line art in pure white #FFFFFF, with a small number of filled bars in mid grey #626060 and #838282. No other colours anywhere.

A fixed heads-up frame stays locked to the edges of the screen for the entire animation, never moving and never changing size: thin white brackets in all four corners, a short row of small tick marks along the top edge, the word "JASPER" in small clean uppercase sans-serif in the top left corner, "01/03" in the top right corner, and "SYSTEMS" in the bottom left corner. These elements stay perfectly still, sharp and unchanged at all times.

Inside that frame everything moves. The camera performs one single continuous unbroken move across the whole ten seconds and never cuts: a slow floating drift that constantly reframes, pushing in on details and pulling back to reveal, changing scale smoothly and continuously, easing softly only at changes of direction and never coming to a full stop. Every element scales and shifts together with the camera, as though a camera is flying low over one large flat diagram.

The subject is a wireframe network diagram. Three large outlined panels with softly rounded corners float in black space, joined to one another by thin white lines with small bright dots pulsing along them. The first panel holds a stack of plain outlined speech bubbles alternating left and right. The second holds a grid of seven columns of plain outlined rectangles. The third holds three columns of plain outlined cards stacked vertically. Small satellite nodes, plain outlined circles and squares, are scattered around them and joined to the panels by more thin lines.

A white arrow cursor moves through the diagram with clear intent. It travels to the first panel and clicks; a new outlined speech bubble appears and a bright dot pulses away down a connecting line. The camera follows that pulse along the line, pushing in as it travels, arriving at the second panel where rectangles fill one after another in sequence. The cursor drags one rectangle across to a new column. The camera pulls back and drifts down and to the left to the third panel, where outlined cards stack into their columns as the cursor moves between them. In the final seconds the camera pulls far back to reveal the whole network at once, all three panels and every satellite node connected and pulsing gently in rhythm, still drifting slowly as it ends.

Every panel surface and shape is a plain empty outline, smooth and unmarked.
```

### Settings

**16:9 · 10s · 1080p · Bitrate High · Unlimited mode OFF**

Leave the reference/image slot empty.

---

## 2. What the piece says

The camera move *is* the argument. It walks the viewer through Jasper's three
functions in one unbroken breath, then pulls back to show they were one system
all along:

| Time | Beat | Message |
|---|---|---|
| 0.0–2.0s | Push on one node, pull back to find a line leading away | Something is connected |
| 2.0–4.0s | Cursor clicks the speech-bubble panel; a pulse fires down the line | **Communicate** |
| 4.0–6.0s | Camera rides the pulse to the seven-column grid; blocks fill in sequence | **Schedule** |
| 6.0–8.0s | Drift to the card columns; cards stack as the cursor works | **Manage** |
| 8.0–10.0s | Pull far back; the whole network pulses together | It was one system |

The cursor is Jasper. It is the only thing in frame with intent — everything
else reacts to it. That is the entire characterisation, and it is enough.

---

## 3. Motion character — deliberately different from the "Introducing" spot

These two Jasper pieces use opposite motion languages. Don't cross-contaminate
them:

| | "Introducing" | "Systems" (this one) |
|---|---|---|
| Camera | One move per beat, **cuts between beats** | **One unbroken move**, no cuts at all |
| Easing | Heavy ease-out into a **full stop** | Continuous drift, **never stops** |
| Feel | Calm, patient, Apple keynote | Restless, floating, always reframing |
| Ground | Pure white | Pure black |

The reference's signature is the tension between a **locked frame** and a
**moving canvas**. The HUD is nailed to the screen; everything behind it is in
constant motion. Lose that contrast and it reads as a screen recording rather
than an ad.

Sampled from the reference: background `#010000` (93% of frame — effectively
pure black), line work and type pure `#FFFFFF`, filled bars `#292828` /
`#626060` / `#838282`. Three values, nothing else.

---

## 4. The baked-in HUD text

You asked for the corner labels rendered by the model rather than composited.
That is the highest-risk element in the prompt, so it is built to the narrowest
envelope these models handle reliably:

- **Three strings only.** The reference has six pieces of HUD furniture; more
  strings means more chances to fail, and any one failure means a re-roll.
- **All uppercase.** Caps have fewer ambiguous letterforms than lowercase and
  survive small rendering far better.
- **All ≤9 characters.** `JASPER` (6), `01/03` (5), `SYSTEMS` (7). Reliability
  falls off a cliff past roughly 12 characters.
- **Quoted in the prompt.** Explicitly quoted short strings render measurably
  better than strings described in prose.

Everything else in frame is described as plain outlines so the model has nothing
else it might decide to letter.

### If the labels come back mangled

Two moves, in order.

**First, re-roll two or three times.** Short-string rendering is high variance
rather than uniformly bad — the same prompt that fails once often lands cleanly
on the next seed. This is worth doing before changing anything.

**If it keeps failing,** swap the HUD paragraph for this marks-only version and
composite the words in CapCut over the top. The HUD is fixed and never moves, so
overlaying it is trivial — a static text layer, no tracking, no keyframes:

```
A fixed heads-up frame stays locked to the edges of the screen for the entire animation, never moving and never changing size: thin white brackets in all four corners, a short row of small tick marks along the top edge, and a small solid white dot in the bottom right corner. These elements stay perfectly still, sharp and unchanged at all times.
```

Set the CapCut labels in a clean grotesque — **Inter**, Helvetica Now or SF Pro,
uppercase, tracked +6%, pure white, small. Position them in the corners inside
the brackets.

---

## 5. Judging a roll

Check in this order, stop at the first failure:

1. Is the background pure black and the palette only black, white and grey?
2. **Does the HUD stay locked and completely still** while the canvas moves
   behind it? This is the single thing that makes the piece work — if the
   corners drift with the camera, re-roll immediately.
3. Is it genuinely one continuous move with no cut?
4. Does the camera actually change scale — pushing in and pulling back — rather
   than just panning across at a fixed zoom?
5. Are the panel interiors plain outlined shapes rather than invented marks?
6. Are the three HUD words correct?

Lock the seed as soon as 1–4 pass. Items 5 and 6 are the ones to burn re-rolls
on; 1–4 are structural and won't fix themselves.

### If the camera pans but never zooms

This is the most likely structural miss — models default to lateral drift.
Strengthen the move by replacing the opening of the camera paragraph with:

```
Inside that frame everything moves. The camera performs one single continuous unbroken move across the whole ten seconds and never cuts. It repeatedly zooms deep into small details until they fill the frame, then pulls back out until the entire diagram is small in the centre, over and over, so the scale of everything on screen is changing constantly and dramatically throughout.
```
