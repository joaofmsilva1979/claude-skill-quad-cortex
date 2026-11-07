# Stereo & Parallel Rigs
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** A true stereo parallel rig runs two separate amps panned left and right, summed into two outputs. Pan at 0.3–0.5 (not 1.0) for a usable stage mix. Drop each parallel lane to -6 dB before the merge to prevent clipping.

---

## What "True Stereo" Means on the QC

True stereo means two independent signal paths — each with its own amp, cab, and potentially different character — routed to separate left and right outputs. When the two signals combine in the stereo field, the difference between them creates width.

**Pseudo-stereo** (not covered here) uses a mono source fed into stereo effects (chorus, ping-pong delay) to create perceived width from a single amp. It's simpler and cheaper on CPU, but doesn't have the depth of a true two-amp rig.

---

## Basic Stereo Parallel Routing

```
[Input] → [Gate] → [Drive] → [Y-Split]
                              ├── Lane 1: [Amp 1] → [Cab 1 IR] → (pan L 0.3)
                              └── Lane 2: [Amp 2] → [Cab 2 IR] → (pan R 0.3)
                              → [Merge] → [Delay Stereo] → [Reverb Stereo] → [Output 1/2]
```

**Key configuration points:**
- Y-split sends full signal to both branches simultaneously
- Each amp receives the same input signal
- Panning is set at the lane output (tap the lane connector)
- The merge combines both channels into a stereo bus
- Stereo delay/reverb after the merge operates on both channels

---

## Amp Pairing for Stereo Rigs

The two amps should complement each other, not compete. Classic pairings:

| Amp L | Amp R | Character |
|---|---|---|
| Brit 2203 (JCM800) | US Double Nrm (Twin) | British grit left, American clean right |
| Friedman BE-100 | Vox AC30 | Modern tight left, chime right |
| Recto (Orange) | Fender Deluxe | Saturated American left, clean warm right |
| Two Rock Clean | Two Rock Crunch | Same amp, two voicings — subtle width |
| Capture of your amp | Factory sim of same amp | Real vs. sim blend |

**Matching gain levels:** The two amps should be at similar perceived loudness before panning. If one amp is 6 dB louder, the stereo image will pull heavily to one side. Use each amp's Master Volume or the lane output level to match.

---

## Pan Settings: Finding the Sweet Spot

**Hard L/R (1.0):** Sounds dramatic in isolation through studio monitors. Live through a PA with any room reflection, it sounds disconnected and instruments "fall out" of the center. Avoid on stage.

**Moderate (0.3–0.5):** Most material and practical for live use. Clear stereo width while maintaining apparent center presence. The "focused but wide" zone.

**Subtle (0.1–0.2):** Only slightly wider than mono. Useful when you need mono compatibility (many PA systems sum to mono at some point in the chain).

**Practical recommendation:**
- Recording/studio: Pan to 0.5–0.7 for dramatic width
- Live on stage: Pan to 0.3–0.4 for width without disconnect
- FOH stereo PA: Pan to 0.4–0.5 — the PA itself adds room diffusion

**Accessing pan:** Tap the lane output connector (small icon on the right of the lane row) → Pan parameter.

---

## Volume Compensation for Parallel Merge

When two signals merge at equal volume, the combined level is approximately +6 dB louder than either source alone (coherent summing can be up to +6 dB; incoherent summing from different amps is typically +3 dB). Without compensation, your parallel rig is significantly louder than a single-amp rig.

**Two compensation methods:**

**Method A: Drop lane output levels**
- Set each lane to -3 to -6 dB output level
- The merge point then sums to roughly the original single-amp level
- Fine-tune by ear to match reference level

**Method B: Reduce amp input levels**
- Lower the Master Volume or Gain on each amp
- More complex to manage since it affects amp feel, not just output level

Method A is preferred — it doesn't change amp character, only level.

---

## Cab Selection for Stereo

For stereo width, the two cabs should have different characters. Identical IRs on both sides = same tonality on both sides = no stereo difference beyond panning.

**Examples of complementary cab choices:**
- L: 4x12 Greenback (warm, smooth) | R: 4x12 V30 (scooped, brighter)
- L: 1x12 Alnico (bloom, warmth) | R: 2x12 G12H (tighter, more attack)
- L: Close-mic (dry, forward) | R: Room mic (ambient, further back)

**Mono compatibility check:** Sum your stereo output to mono (some audio interfaces and PA systems have a mono check). The two cab IRs should not create severe comb filtering when summed. If the mono tone sounds thin or hollow, try different IRs or adjust the phase of one channel.

---

## Stereo Delay: Ping-Pong

Ping-pong delay alternates repeats between left and right channels. It's the defining stereo delay effect.

**Ping-pong settings:**
- **Time:** Tempo-synced, typically dotted eighth note or quarter note
- **Feedback:** 30–50% (too much = washing the stereo field)
- **Spread:** 100% (maximum left-right difference between repeats)
- **Mix:** 20–40% in series; up to 60% in parallel lane

**Placement:** After the merge point. Ping-pong delay placed before the merge will collapse to mono in the merge.

---

## Wet/Dry/Wet (WDW) with Two Physical Outputs

The ultimate stereo rig for recording or high-spec live use:

```
Lane 1 (Center/Dry): [Amp] → [Cab] → Output 1/2 (L/R, panned center)
Lane 2 (Left Wet): [Reverb/Delay] → Output 1 (pan full L)
Lane 3 (Right Wet): [Chorus/Reverb] → Output 2 (pan full R)
```

Each lane goes to a physically separate destination. This requires 3 speakers/channels: center speaker for dry, two speakers for the wet stereo spread. Common in professional studio live setups.

---

## Stereo Parallel Rig with Scenes

| Scene | Config |
|---|---|
| A (Clean) | Both amps at low gain, pan 0.3/0.3, reverb medium |
| B (Crunch) | Amp 1 gain up slightly, Amp 2 stays clean, slight pan shift |
| C (Lead) | Both amps gain up, drive ON, delay ON, reverb up |
| D (Wide Ambient) | Reverb maxed on both, delay long, pan to 0.5/0.5 |

Scene the **blend ratio** between amps to shift character: more of Amp 1 for one scene, more of Amp 2 for another, without changing either amp's gain structure.

---

## Common Mistakes / Erreurs fréquentes

- Panning hard L/R (1.0) for live use — sounds disconnected in the room
- Not compensating for merge volume increase — rig is 6 dB louder than expected
- Using identical cab IRs on both lanes — no sonic difference, just doubled CPU cost
- Placing ping-pong delay before the merge — it collapses when summed
- Not checking mono compatibility — the stereo rig disappears on a mono PA

---

## Quick Reference / Référence rapide

| Parameter | Value |
|---|---|
| Pan for live use | L 0.3 / R 0.3 |
| Pan for studio | L 0.5–0.7 / R 0.5–0.7 |
| Lane level before merge | -3 to -6 dB each |
| Ping-pong delay time | Dotted eighth, tempo-synced |
| Ping-pong feedback | 30–50% |
| Stereo block position | After merge, not in parallel lanes |
| Mono check | Required before live performance |
