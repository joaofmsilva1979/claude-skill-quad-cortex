# Lane Routing: Serial, Parallel & Splits
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** The QC has 8 lanes. By default they run serial (one after another). Use Y-splits to run amps in parallel — this is the core technique for dual-amp rigs, wet/dry setups, and separating cab from effects chains.

---

## The Lane System

The Quad Cortex grid has **8 lanes**, each capable of holding 8 blocks. In the default view you see lanes 1–4; swipe up to see lanes 5–8.

**Lane hierarchy:**
- Lane 1 is the primary signal path
- Other lanes are sub-paths that must be connected back to Lane 1 (or to a separate output) via a merge
- An unconnected lane is silent

**Lane output levels:** Each lane has an independent output volume control. Access it by tapping the lane connector on the right side of the grid. Default is 0 dB; for parallel amps you'll often drop both to around -3 to -6 dB to prevent the mix from summing too loud.

---

## Serial Routing (Default)

All blocks in Lane 1 process in sequence. This is identical to a standard pedalboard:

```
Guitar → Drive → Amp → Cab → Delay → Reverb → Output
```

Serial is correct for:
- Single amp setups
- Traditional pedalboard emulation
- Keeping CPU low
- When you want the amp to color all effects in front of it

---

## Splits: Y, A/B, and X/Y

Splits are the routing nodes that branch your signal into multiple lanes.

### Y-Split
Sends the full signal to **both** branches simultaneously. Volume ratio is 50/50 by default but adjustable.

Use Y-splits for:
- Running two amps in parallel
- Wet/dry rigs (dry amp in one lane, wet FX chain in another)
- Blending a clean DI signal with an amp signal

### A/B Split
Routes signal to **either** Lane A or Lane B — not both. The routing depends on an expression pedal or scene assignment. At full A, you hear only Lane A; at full B, only Lane B; in the middle, a blend.

Use A/B splits for:
- Switching between two completely different amp characters
- Morphing between two cab IRs

### X/Y Split
Similar to A/B but with more parameter control. Generally used in advanced routing scenarios.

---

## Setting Up a Parallel Dual-Amp Rig

This is the most common advanced routing on QC.

**Step-by-step:**
1. Place your pre-amp effects (drive, noise gate, compressor) in Lane 1
2. Add a Y-Split block at the end of your pre-amp chain
3. Lane 1 (top branch): Add Amp 1 + Cab 1
4. Lane 2 (bottom branch): Add Amp 2 + Cab 2
5. Add a Merge block to bring both lanes back together
6. After the merge: shared post-amp effects (delay, reverb)
7. Output block at the end

**Level compensation:** When two signals merge, the volume roughly doubles. Set each lane's output volume to around -6 dB, or lower the input volume on each amp to compensate. Check your output meter to avoid clipping.

**Example parallel rig:**
```
[Input] → [Gate] → [Drive] → [Y-Split]
                              ├── Lane 1: [Brit 2203 JCM800] → [Marshall 1960A IR]
                              └── Lane 2: [US Hot Rod Clean] → [2x12 Greenback IR]
                              → [Merge] → [Delay] → [Reverb] → [Output]
```

---

## Lane Panning for Stereo Rigs

Each lane has an independent pan setting. For a stereo dual-amp rig:

- Lane 1 (Amp 1): Pan left — set to approximately **L 0.3** (30% left)
- Lane 2 (Amp 2): Pan right — set to approximately **R 0.3** (30% right)

Don't pan hard left/right (1.0) unless playing through stereo monitors with a lot of physical space — it sounds disconnected. 0.3–0.5 gives width while maintaining mono compatibility.

**Access lane panning:** Tap the lane output connector (small icon on the right of each lane row) → Pan parameter.

---

## FX Loop Integration

If you're running hardware pedals through the QC's FX loop:

- FX Send = Outputs 3/4
- FX Return = Inputs 3/4

In the grid, place the **FX Loop block** where you want your hardware pedal in the chain. This block routes signal out to your pedal and back in.

You can place the FX loop block in a parallel lane if you want your hardware reverb/delay wet-only in a parallel chain, keeping the dry signal internal.

---

## Wet/Dry/Wet (WDW) Routing

For studio-level ambient rigs:

```
[Y-Split]
├── Lane 1 (Center/Dry): Amp → Cab → Output (center pan)
├── Lane 2 (Left Wet): Delay (long) → Reverb → Output (pan left ~0.7)
└── Lane 3 (Right Wet): Chorus → Reverb → Output (pan right ~0.7)
```

Each lane goes to its own output destination. Use Outputs 1/2 for the wet lanes and direct out for dry.

---

## Common Mistakes / Erreurs fréquentes

- Creating a split but forgetting the merge block — the lower lane is silent
- Not compensating level after a merge — output clips
- Panning both lanes to 0 (center) in a stereo rig — no stereo benefit
- Using too many parallel lanes with heavy reverb in each — CPU spikes
- Placing the split after the cab instead of before it — both amps share one cab sound (usually unintended)

---

## Quick Reference / Référence rapide

| Concept | Value/Method |
|---|---|
| Add a split | Long-press empty slot → Split (Y, A/B, X/Y) |
| Lane output level | Tap lane connector → Volume |
| Lane panning | Tap lane connector → Pan |
| Parallel amp level compensation | -3 to -6 dB per lane before merge |
| Stereo pan values (suggested) | L 0.3 / R 0.3 (not hard L/R) |
| FX loop block location | Between pre-amp effects and amp |
| Max usable lanes (CPU safe) | 4 lanes with heavy FX; 6-8 for simple chains |
