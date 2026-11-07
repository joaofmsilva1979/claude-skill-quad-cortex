# EQ & Tone Shaping
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** EQ on the QC works at three levels: amp tone controls (broadest), dedicated EQ blocks (surgical), and Global EQ (room correction). Most problems should be fixed at the amp first; reach for an EQ block only for specific frequency problems.

---

## The EQ Hierarchy

### Level 1: Amp Tone Controls
Every amp block has its own Bass/Mid/Treble (and often Presence and Resonance). These are broad passive-style filters that interact with each other — the starting point for all EQ.

Fix broad tonal balance here. If the amp sounds too dark, raise treble. If it sounds honky, cut mid. Don't reach for an EQ block before exhausting the amp's own controls.

### Level 2: EQ Blocks
Dedicated EQ blocks provide more precise control — parametric, graphic, or shelf-based. Use these for:
- Specific problem frequencies ("there's a nasty ring at 1.2 kHz")
- Matching tones between two different amp blocks in a parallel rig
- Fine-tuning cab IR response
- Pre-amp input shaping (low-cut to remove proximity hum)

### Level 3: Global EQ
Room correction only. Applies to all presets. See QC_09 for details.

---

## Frequency Map for Guitar

Knowing what each frequency range sounds like helps you EQ faster:

| Frequency Range | Character | Common Issue |
|---|---|---|
| Below 80 Hz | Sub-bass rumble | HVAC noise, cab resonance — usually cut |
| 80–200 Hz | Low-end body, warmth | Too much = muddy; too little = thin |
| 200–400 Hz | Mud zone | Excess here = "blanket over the amp" sound |
| 400–800 Hz | Boxy/honk zone | Excess here = cheap combo amp sound |
| 800 Hz–2 kHz | Presence/attack | Cut for warmth; boost to cut through mix |
| 2–5 kHz | Bite, definition | Attack of pick on strings lives here |
| 5–8 kHz | Upper presence, sheen | Excess = harsh; correct amount = air |
| 8–10 kHz | Fizz zone (high gain) | Often needs gentle cut after cab IR |
| Above 10 kHz | Air, shimmer | Natural treble extension on clean tones |

**Most common problems and their EQ fixes:**

| Problem | Solution |
|---|---|
| Too muddy / indistinct | Cut -3 dB at 200–300 Hz; check low-cut is at 80–100 Hz |
| Sounds honky or nasal | Cut -2 to -4 dB at 500–800 Hz |
| Lost in the mix | Boost +2–3 dB at 1–2 kHz (presence zone) |
| Too bright/harsh | Cut -2 to -4 dB at 3–5 kHz; check high-cut after cab |
| High-gain fizz | Low shelf cut or gentle notch at 6–8 kHz |
| Thin without body | Boost +2 dB at 120–150 Hz |

---

## Low-Cut on Input (High-Pass Filter)

A high-pass filter (low-cut) at the beginning of your signal chain removes sub-bass frequencies before they hit the amp. This is almost always beneficial:

- **Frequency:** 80–100 Hz (clean tones); 100–120 Hz (high gain)
- **Slope:** 12 dB/octave is gentle; 24 dB/octave is steeper (removes more)
- **Why:** Guitar speakers don't reproduce below 80 Hz — anything below that is wasted energy and potential amp intermodulation distortion

**Add this as an EQ block** (high-pass) at the very beginning of the chain, before any drive pedal.

---

## High-Cut on Cab IR (Low-Pass Filter)

Similarly, a low-pass filter (high-cut) after the cab block removes the fizz and digital artifacts that cab IRs sometimes emphasize at high frequencies:

- **Frequency:** 5–8 kHz (adjust by ear — start at 6.5 kHz)
- **Slope:** 12 dB/octave
- **Why:** Real guitar speakers have a natural rolloff above ~5–6 kHz. IRs sometimes capture this correctly, sometimes don't. The cut emulates the natural speaker behavior.

**When to use it:** If your tone sounds harsh or fizzy when going direct to FOH or FRFR speakers, this is usually the fix.

---

## Pre-Amp EQ vs. Post-Amp EQ

**Pre-amp EQ (before the amp block):**
- Shapes what goes into the amp
- Changes how the amp responds, not just the output tone
- Example: Cutting bass pre-amp tightens up the low end more effectively than cutting bass post-amp (the amp never tries to amplify the bass in the first place)
- Good for: Tightening low end for high gain, shaping pickup character

**Post-amp EQ (after the amp block, before or after cab):**
- Shapes the final sound without affecting amp dynamics
- Cleaner, more precise control
- Good for: Fixing cab IR response, mix EQ, cutting problem frequencies

**Rule of thumb:** Use pre-amp EQ for feel and dynamics; use post-amp EQ for tone shaping.

---

## EQ Block Types on the QC

### 10-Band Graphic EQ
Fixed frequency bands (like a hardware rack EQ). Less flexible but visually intuitive. Good for quick overall shaping when you know the frequency range affected.

### Parametric EQ
Choose the exact frequency, bandwidth (Q), and gain for each band. More surgical. Use this for identifying and fixing specific problem frequencies.

**Parametric EQ technique:** Use a narrow Q boost and sweep through the frequency range. When you find the offending frequency (it will suddenly sound worse), reduce the gain to cut that specific problem.

### Shelf EQ
Broad cuts/boosts above or below a frequency. Best for overall brightness control or low-end management.

---

## 10-Band EQ as a Tone Shaper for Specific Genres

**Classic rock (JCM800-style):**
Slight mid-scoop to remove boxy quality: -2 dB at 500 Hz, +1 dB at 3 kHz for bite

**Metal (tight and modern):**
-3 dB at 200–300 Hz (remove mud), -2 dB at 600 Hz (remove honk), +2 dB at 2–3 kHz (definition)

**Clean blues:**
+2 dB at 150 Hz (body), flat mid, -1 dB at 5 kHz (smooth highs)

**Funk/clean:**
-1 dB at 200 Hz, +2 dB at 1 kHz (cut through mix), flat or +1 dB at 8 kHz (sparkle)

---

## Common Mistakes / Erreurs fréquentes

- Boosting to fix problems instead of cutting — cuts remove problems, boosts add character
- Stacking EQ blocks (3+ EQ blocks in one chain) — usually a sign of upstream problems, not solutions
- Using Global EQ to fix a preset tone — changes affect all presets
- Not having a low-cut at the input — sub-bass mud builds up through the chain
- Making large EQ moves (+/- 6 dB) — the starting point was probably wrong; reconsider the amp settings
- EQing in isolation (through headphones in quiet room) — always EQ in context (at gig volume, with the band)

---

## Quick Reference / Référence rapide

| Frequency | Sound | Fix |
|---|---|---|
| Below 80 Hz | Rumble | Cut (high-pass filter at input) |
| 200–400 Hz | Mud | Cut -2 to -4 dB |
| 500–800 Hz | Honk/boxy | Cut -2 to -3 dB |
| 1–2 kHz | Presence | Boost +2 dB to cut through mix |
| 3–5 kHz | Bite/attack | Boost for aggression; cut for warmth |
| 6–8 kHz | Fizz | Gentle cut after cab IR |
| Input low-cut | 80–120 Hz | Always |
| Cab high-cut | 5–8 kHz | If fizzy going direct |
