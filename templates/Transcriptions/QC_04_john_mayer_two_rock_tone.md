# John Mayer / Two Rock Clean Tones
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Two Rock tones live in the edge-of-breakup zone — a Strat's volume knob should take you from glassy clean to soft natural overdrive without a pedal. Prioritize capture selection and input impedance before touching EQ.

---

## The Core Sound: What You're Going For

John Mayer's reference tone is a Two Rock Custom Reverb Signature (or Studio Pro) through a Two Rock 1x12 or 2x12 cabinet with Tone Tubby Hemp Cone speakers. The defining characteristics:

- **Clear but not sterile** — there's compression and warmth even on clean
- **Touch-sensitive** — dig in harder and it softens/compresses naturally
- **Rolling the guitar volume to ~7** = complete clean; at 10 = on the edge of natural breakup
- **Single-coil character** — Stratocaster middle+neck positions dominate
- **Broad, scooped midrange** but not empty — the low-mids are present, not boosted

---

## Finding the Right Block / Capture

**On the QC, search for:**
- "Two Rock" in the Neural Captures cloud (Cortex Cloud)
- Neural DSP's own Two Rock amp blocks if available in your firmware
- Community captures: search "Two Rock Sig", "TRCS", "Two Rock Studio"

**What to listen for in a capture:**
- Pick the neck pickup at full volume and play softly — the attack should feel bouncy and clear
- Now dig in — it should compress naturally, not distort harshly
- Roll volume to 7 — should clean up completely with no muddiness

If the capture sounds stiff or harsh, skip it. Many Two Rock captures are mic'd too close or processed — find one with air.

**Alternative QC factory amps that approximate the character:**
- "US Deluxe Clean" (Fender Deluxe Reverb — not identical but similar clean platform)
- "US Double Nrm" (Fender Twin Reverb — cleaner, brighter)

---

## Signal Chain for Two Rock Tones

```
[Input] → [Optical Compressor] → [Amp (Two Rock)] → [Cab IR] → [EQ] → [Chorus] → [Delay] → [Reverb] → [Output]
```

### Compressor: Opto Comp
Mayer's reference is an Optical compressor (LA-2A style).

**Settings:**
- **Type:** Opto Comp (or "Optical" in QC)
- **Threshold:** -20 to -15 dB (light compression)
- **Ratio:** 2:1 to 3:1
- **Attack:** Medium-slow (30–50ms) — lets transients breathe
- **Release:** Auto (Opto behavior)
- **Mix:** 70–90% (some parallel dry signal preserved)

The compressor goes **before** the amp, not after. This shapes how the amp responds to your pick attack.

### Amp Parameters (Two Rock style)
- **Input Volume (Gain):** 4–6 out of 10 — this is not a high-gain amp. Keep it in the touch-sensitive zone.
- **Bass:** 5–6 (moderate — Two Rocks have a natural low-end warmth)
- **Mid:** 4–5 (slightly scooped but not absent)
- **Treble:** 6–7 (this amp is brighter than it appears — the treble is musical, not harsh)
- **Presence:** 5–6 (adds upper-mid clarity without brittleness)
- **Master Volume:** irrelevant for preset sound, set for output level

### Cabinet IR Selection
Target IRs:
- Two Rock 1x12 or 2x12 with Tone Tubby, Cannabis Rex, or Celestion G12H
- Mic placement: slightly off-axis, pulled back 2–4 inches (not on the dust cap)
- If using third-party IRs: Celestion, ML Sound Lab, or York Audio Two Rock IRs are well-regarded

**On QC built-in cabs:** Try "USA 112 Hemp" or similar small American cabinet — the warmth of a single 12" is key.

---

## Strat Pickup Positions and Volume Knob Response

The Two Rock tone is inseparable from guitar setup:

| Pickup Position | Character | Use For |
|---|---|---|
| Neck (1) | Warm, full, almost vocal | Slow blues, chords |
| Middle (3) | Bell-like, glassy | Arpeggios, chicken pickin' |
| Neck+Middle (2) | Quack, out-of-phase | Mayer signature "pop" tone |
| Bridge+Middle (4) | Bright, cutting | Funky rhythm, single notes |
| Bridge (5) | Bright, thin | Country twang, avoid on Two Rock |

**Volume knob technique:** With this amp sound, your guitar's volume knob is an active tone shaper:
- 10: Edge of breakup, full sustain
- 7–8: Clean with presence
- 5–6: Clean with warmth, good for comping
- 3–4: Very clean, almost glassy — good for ambient swells

---

## Scene Layout for a Mayer-Style Preset

| Scene | Name | Config |
|---|---|---|
| A | Clean Neck | Comp ON, neck pickup, reverb medium |
| B | Clean Bright | Comp ON, bridge+mid blend, slight EQ cut on bass |
| C | Edge OD | Comp ON, amp gain +1 step, Klon-style drive at unity |
| D | Crunch Solo | Light TS-style drive ON, amp gain up slightly |
| E | Ambient | Shimmer reverb ON, volume swell enabled, delay long |
| F | Full Band | Slight low-cut, mid push, cuts through mix |

---

## Key Pedals for the Sound (as QC blocks)

| Pedal | QC Block | Purpose |
|---|---|---|
| Klon Centaur | "Gold Drive" or "Klone" capture | Transparent boost/light OD |
| Tube Screamer | "Green 808" | Mid-push into amp breakup |
| Uni-Vibe | "Vibe" or "Rotary" | "Gravity" era pulsing chorus |
| Strymon Timeline (Tape delay) | "EP-III Tape" | Warm tape echo |
| Hall reverb | "Chamber Hall" or "Spring" | Spacious but not washy |

---

## Common Mistakes / Erreurs fréquentes

- Setting amp gain too high — this tone lives at 4–6, not 7–8
- Skipping the compressor — the touch dynamics fall apart without it
- Using a 4x12 cabinet IR — wrong speaker character for this amp
- Boosting mids heavily — the Two Rock has a natural, balanced midrange; don't sculpt aggressively
- Ignoring the guitar volume knob — most players just leave it at 10 and miss half the technique

---

## Quick Reference / Référence rapide

| Parameter | Target Value |
|---|---|
| Amp Gain | 4–6 / 10 |
| Bass | 5–6 |
| Mid | 4–5 |
| Treble | 6–7 |
| Opto Comp Ratio | 2:1 – 3:1 |
| Opto Comp Attack | 30–50 ms |
| Cab | 1x12 or 2x12, hemp/alnico speaker |
| Pickup Position | 2 or 3 (Strat) for core tone |
