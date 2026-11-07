# Clean & Ambient Tones
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Great ambient tones on QC depend on parallel FX routing (dry amp signal untouched, wet reverb/delay in a separate lane) and careful modulation layering. Keep the dry signal pristine; let the wet signal bloom.

---

## The Foundation: A Clean Amp

For ambient work, the amp should be fully clean — no breakup at any playing dynamic. Good base amps on QC:

| QC Block | Real Amp | Character |
|---|---|---|
| US Deluxe Clean | Fender Deluxe Reverb (clean) | Warm, slightly compressed |
| US Double Nrm | Fender Twin Reverb (normal ch.) | Very clean, wide bandwidth |
| UK Hiwatt | Hiwatt DR103 | Very clean, articulate, hi-fi |
| Vox AC30 (clean) | Vox AC30 | Chime, top-boost character |

**Amp gain:** 2–4 out of 10 maximum. If the amp breathes at all, it's too high for pure ambient work (unless that edge-of-breakup texture is intentional).

**Key amp settings for clean ambient:**
- Bass: 4–5 (not too much low-end — it muddies reverb)
- Mid: 4–5 (scooped slightly for shimmer to sit around it)
- Treble: 6–7 (brightness helps single-note lines cut through reverb)
- Presence: 5–6

---

## Parallel Reverb Chain: The Core Routing

The best ambient rigs keep the dry signal completely clean and route reverb in a parallel lane. This preserves pick attack and note definition that series reverb destroys.

```
[Input] → [Comp] → [Y-Split]
                    ├── Lane 1: [Amp] → [Cab] → [Output (center, 0 dB)]
                    └── Lane 2: [Reverb (long)] → [Shimmer] → [Output (stereo, mix 60%)]
```

**Benefits:**
- Your note attacks are always clear (dry lane)
- Reverb blooms behind notes without washing out attack
- You can push reverb mix much higher without losing definition
- CPU is shared across lanes rather than stacking series effects

**Lane level for parallel reverb:** Set the wet lane to -3 to -6 dB below the dry lane. This keeps the ambient bed as texture rather than the dominant element.

---

## Shimmer Reverb

Shimmer = reverb with pitch-shifted feedback (usually an octave up). It creates the sustained, angelic pad sound common in ambient guitar.

**QC shimmer approach:**
- Some QC reverb blocks have a "Shimmer" or "Pitch" parameter built in (check the Hall or Plate reverb blocks)
- Alternatively: chain a **Pitch Shifter** (set to +12 semitones, 100% wet) → into a **Reverb** block, with the reverb feedback high enough to sustain

**Shimmer reverb parameters:**
- Reverb size: Large (8–12 seconds decay)
- Pre-delay: 20–60 ms (lets the note start before shimmer enters)
- Shimmer mix (pitch shift in reverb): 30–60% — too high and it sounds like a keyboard, not a guitar
- Damping: Medium-low (let high frequencies sustain)

---

## Infinite Sustain / Freeze

The QC's **Freeze** effect or a Reverb block set to infinite decay (feedback at 100%) holds the ambient note or chord indefinitely.

**Practical use:**
- Assign a Freeze block to a stomp footswitch
- Play a chord, hit Freeze, then play a melody over the sustained pad
- The frozen chord acts as a one-shot ambient drone

**Alternative (no dedicated Freeze block):**
- Reverb block with Decay at maximum, pre-delay 0
- Expression pedal assigned to Reverb Mix (swell in the reverb with foot)

---

## Volume Swells

Volume swells (picking while ramping the volume up) are essential for ambient guitar. Two approaches on QC:

**1. Expression pedal:** Assign expression pedal to your amp or input block's volume. Heel = silent, toe = full volume. This is the most natural feel — identical to using a volume pedal.

**2. Swell block:** Some QC versions have a dedicated swell envelope. Set the swell time to 300–1000 ms depending on tempo.

**Signal chain for swells:**
```
[Input] → [Swell/Volume] → [Amp] → [Cab] → [Modulation] → [Delay] → [Reverb] → [Output]
```

Volume/swell goes **before** the amp. If placed after, the swell doesn't interact with amp dynamics.

---

## Modulation Layering

Ambient tones often use multiple light modulations to add movement without obvious pitch wobble.

**Light chorus:** Very subtle detuning (rate 0.5 Hz, depth 10–15%) adds width and shimmer without sounding like a 1980s chorus.

**Tremolo:** Slow (1–2 Hz), soft wave (sine not square). Great for a breathing quality to sustained chords.

**Pitch vibrato / Leslie:** Very slow (0.5 Hz), small depth (5–10%). Adds the warmth of a not-quite-in-tune string.

**Stacking modulation in series:**
```
[Amp] → [Cab] → [Light Chorus] → [Tremolo] → [Delay] → [Reverb]
```

Keep each modulation effect subtle. If you notice each effect individually, it's too much. The combined effect should feel like "movement" not "effect."

---

## Delay for Ambient Textures

**Tape echo (EP-III Tape delay):** Warm, slightly degraded repeats. Good for bluesy ambient.

**Reverse delay:** Swells before the note (sounds backwards). Creates ethereal pads when mixed at 30–50%.

**Ping-pong delay:** Repeats alternate left and right. Good for stereo width.

**Key ambient delay settings:**
- Time: Tempo-synced (1/4 note, dotted 1/8, or 1/2 note)
- Feedback: 40–70% (multiple repeats that fade)
- Mix: 20–40% in series; up to 70% in a parallel lane
- Modulation on delay: ON, slight pitch/rate variation for tape feel

---

## Common Mistakes / Erreurs fréquentes

- Putting reverb in series before checking how it affects note definition
- Reverb pre-delay at 0 — the reverb obscures the attack completely
- Too much shimmer mix — sounds like a synthesizer
- Not using parallel routing — the dry signal disappears into the reverb
- Volume swell placed after the amp — swell doesn't feel organic
- Stacking modulations at high depth — sounds like seasickness

---

## Quick Reference / Référence rapide

| Parameter | Value |
|---|---|
| Amp gain for clean | 2–4 / 10 |
| Reverb decay (ambient) | 6–12 seconds |
| Reverb pre-delay | 20–60 ms |
| Shimmer pitch shift | +12 semitones |
| Shimmer mix | 30–60% |
| Chorus depth (subtle) | 10–15% |
| Delay feedback (ambient) | 40–70% |
| Parallel wet lane level | -3 to -6 dB |
