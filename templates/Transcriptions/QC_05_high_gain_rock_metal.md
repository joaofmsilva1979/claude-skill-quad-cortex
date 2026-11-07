# High Gain: Rock & Metal Tones
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** High gain tones on the QC succeed or fail at the noise gate and cab IR stages — get those right before touching amp EQ. The amp gain knob is rarely where you should be pushing hardest; use drive staging instead.

---

## The Core High-Gain Amps on QC

| QC Block Name | Real Amp | Character |
|---|---|---|
| Brit 2203 JCM800 | Marshall JCM800 2203 | Mid-forward, punchy, classic rock/80s metal |
| Friedman BE-100 | Friedman BE-100 | Tight modern high gain, great low-end |
| EVH 5150 III | EVH 5150 III | Aggressive, articulate, brown sound |
| Recto Orange/Red | Mesa Boogie Dual Rectifier | Saturated, wide, heavy |
| SLO-100 | Soldano SLO-100 | Harmonically rich, violin-like sustain |
| Engl Fireball | ENGL Fireball | Tight, clinical, good for DJent |
| Peavey 6534 | Peavey 6534+ | Similar to 5150 but tighter |

---

## Gain Staging: Don't Just Max the Amp

The biggest mistake in high-gain tones is using only the amp's gain knob. Proper gain staging uses a drive pedal to push the amp in a controlled way:

**Recommended approach:**
1. Set amp gain to **60–70% of maximum** (not 100%)
2. Put a drive pedal (tubescreamer-style or hard clipper) **before** the amp
3. Set the drive pedal's gain low (0–20%) but level high (70–90%)
4. The pedal compresses and tightens the input before it hits the amp

This two-stage approach gives you:
- Better articulation (notes don't blur together)
- Tighter low end (the pedal compresses flub)
- More sustain without more noise

**QC blocks for drive staging:**
- "Green 808" (TS-style): adds mid hump, tightens low end
- "Minotaur" (Klon-style): transparent, adds harmonic presence
- "Phat Fuzz" or "Red Distortion": for more aggressive pre-gain

---

## Noise Gate Placement for High Gain

You need **two** noise gates in a high-gain chain:

```
[Input] → [Gate 1] → [Drive] → [Amp] → [Cab] → [Gate 2] → [Delay] → [Reverb] → [Output]
```

**Gate 1** (before amp): Kills guitar hum and pick noise between notes
**Gate 2** (after cab): Kills amp hiss and transformer noise that persists even after Gate 1

**Gate settings for high gain:**
| Parameter | Gate 1 (Pre-Amp) | Gate 2 (Post-Cab) |
|---|---|---|
| Threshold | -50 to -40 dB | -65 to -55 dB |
| Attack | 2–5 ms (fast) | 5–10 ms |
| Hold | 50–100 ms | 20–50 ms |
| Release | 50–100 ms | 100–200 ms |
| Type | Hard Gate or Downward Expander | Downward Expander |

Downward Expander is more musical — it reduces gain gradually rather than cutting to silence. Use Hard Gate only for extreme metal where total silence between notes is desirable.

---

## Cabinet IR Selection for Metal

The cab is as important as the amp for metal tone. Rule of thumb:

| Speaker | Character | Good For |
|---|---|---|
| Celestion Vintage 30 | Scooped, mid-spike at 2kHz, creamy | Classic rock, 80s metal |
| Celestion G12T-75 | Tight low end, forward upper mid | Thrash, modern metal |
| Greenbacks | Warm, broken-in, compressed | Classic rock, bluesier metal |
| Mesa V30 clone | Aggressive, modern | Djent, modern American metal |

**Mic position matters:**
- **On-axis (center cap):** Brighter, more aggressive
- **Off-axis (25% off cap):** Warmer, more rounded
- **Back mic blended:** Adds depth and low-mid body

For 4x12 cabinets: Mix two mic positions (e.g., SM57 on-axis + a ribbon off-axis) if the IR library supports it.

**Low-cut on cab IR:** Add a high-pass filter (low-cut) at **80–100 Hz** after the cab block to remove sub-bass rumble. This is not present in the cab IR itself — add it as a separate EQ block.

---

## Tight vs. Loose Feel

The "feel" of a high-gain amp is about transient response and low-end behavior.

**For tighter (djent/modern metal):**
- Drive pedal before amp (Green 808 at 0% gain, 80% level)
- Amp bass control lower (4–5)
- Amp presence higher (6–7)
- Gate 1 threshold higher (-45 to -40 dB)
- Cab: G12T-75 or Mesa V30 IR
- Add a subtle expander/compressor after the cab (ratio 1.5:1, fast attack)

**For looser (classic rock, doom):**
- Less or no drive pedal
- Amp bass higher (6–7)
- Amp presence lower (4–5)
- Gate 1 threshold lower (-60 dB) or off
- Cab: Greenback or Vintage 30 IR

---

## Scene Structure for Metal Presets

| Scene | Name | Config |
|---|---|---|
| A | Rhythm Clean | Amp channel 1 (clean), drive OFF, gate moderate |
| B | Crunch | Amp channel 2 (crunch), drive low gain, gate tight |
| C | Heavy Rhythm | Amp full gain, both gates ON, delay OFF |
| D | Lead | Heavy Rhythm + boost drive ON, mid EQ +2dB, delay ON |
| E | Solo Sustain | Same as D, reverb added, presence up |
| F | FX off (silent) | All FX bypassed, used for silent stage tuning |

---

## Specific Amp Settings

### JCM800 (Brit 2203)
- Gain: 6–8 (pre-amp stage already aggressive)
- Bass: 5, Mid: 6, Treble: 7
- Presence: 7 (key to the Marshall bark)
- Master: set for output level only
- Pair with Greenback or Vintage 30, 4x12

### Friedman BE-100
- Gain: 7–8
- Bass: 5 (it's already punchy)
- Mid: 6–7 (the BE channel has a natural mid-forward character)
- Treble: 6
- Presence: 5–6
- Drive: Green 808 before for tightening

### EVH 5150 III (Red channel)
- Gain: 6–7 (doesn't need to be maxed)
- Low: 5, Mid: 5, High: 7
- Presence: 6, Resonance: 5
- Green 808 before for the classic EVH technique
- Pair with 4x12 Mesa or Greenback

---

## Common Mistakes / Erreurs fréquentes

- Maxing out amp gain — creates mush, not aggression
- Skipping the second noise gate — amp hiss bleeds into every note
- Using a large reverb room on metal rhythm — kills clarity
- Choosing a Vintage 30 cab for tight modern metal — wrong character
- Placing the gate after all effects — gate chops delay tails
- Using drive pedal gain too high — doubles down on saturation instead of tightening

---

## Quick Reference / Référence rapide

| Parameter | Value Range |
|---|---|
| Amp gain (staged) | 60–70% max |
| Drive pedal gain | 0–20% (level booster role) |
| Gate 1 threshold (pre-amp) | -50 to -40 dB |
| Gate 2 threshold (post-cab) | -65 to -55 dB |
| Cab low-cut | 80–100 Hz |
| Presence for attack | 6–7 |
| Bass for tight feel | 4–5 |
