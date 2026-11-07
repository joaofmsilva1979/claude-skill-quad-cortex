# CPU Management
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Keep total CPU below 85%. Reverb and polyphonic pitch effects are the most expensive blocks. Delete unused blocks instead of bypassing them — bypassed blocks still consume CPU. Mono processing halves DSP cost.

---

## Why CPU Matters

The Quad Cortex's DSP (Digital Signal Processor) has a finite processing budget. When CPU exceeds 100%, audio glitches, dropouts, and artifacts occur. The goal is to build presets that fit within budget.

**The 85% rule:** Keep CPU below 85% to leave headroom for unexpected spikes during performance (expression pedal movement, scene changes, bypass toggles can briefly spike CPU).

**Where to check CPU:** Swipe down from the top bar → CPU meter is displayed in real time. Build your preset and watch the meter as you add blocks.

---

## Block CPU Cost: Approximate Hierarchy

Block CPU cost varies by exact algorithm, but this ranking holds generally:

| CPU Cost | Block Types |
|---|---|
| Very high | Shimmer/pitch reverb, polyphonic pitch shifter, Neural Capture (Neural type), convolution reverb (long IR) |
| High | Algorithmic reverb (Hall, Chamber with long decay), multi-voice harmonizer, complex modulation (rotary, ensemble) |
| Medium | Standard delay, chorus, flanger, phaser, standard reverb (plate, spring) |
| Low | Amp simulation block, cab IR, EQ, compressor, standard gate, basic drive/OD |
| Very low | Volume, panner, simple boosts, input block, output block |

**Practical implication:** A preset with 2 reverbs + 1 shimmer + 1 pitch harmonizer can easily hit 90% CPU with nothing else. A preset with 2 amps + 2 cabs + 1 delay + 1 reverb might sit at 65%.

---

## Delete vs. Bypass

**This is the most important CPU management rule:**

Bypassed blocks still use CPU. The QC keeps the bypass state ready to un-bypass at any moment, so it maintains the processing. The only way to free CPU is to delete the block.

**Workflow:** When building a preset, if you try a reverb block and decide you don't want it, delete it — don't just bypass it.

Exception: If you're assigning a block to a scene and that scene should have the effect ON while another scene has it OFF, then you need to bypass rather than delete (scenes store bypass state). In this case, the CPU cost is intentional.

---

## Mono vs. Stereo Processing

Every stereo block processes two channels simultaneously, roughly doubling its CPU cost compared to the mono version.

**When you need stereo:**
- Running two separate physical outputs in stereo
- Ping-pong delay
- Stereo chorus width
- True stereo parallel amps panned left/right

**When mono is fine:**
- Single-amp mono rigs
- Playing through a single FRFR or single guitar cab
- Recording directly with no stereo panning intent

**How to check and change:** Most blocks have a mono/stereo toggle in their settings. Set the entire preset to mono if you're running a mono rig — CPU savings can be significant (15–25% on a full preset).

**Lane mono setting:** You can set individual lanes to mono. If your dry signal lane is mono (single amp into single cab) but your effects return lane is stereo (ping-pong delay), that's a valid hybrid approach.

---

## Optimization Strategies

### Strategy 1: Pre-Amp EQ Instead of Post-Amp EQ Block
Using the amp block's built-in tone controls (Bass/Mid/Treble) instead of adding an EQ block saves one block's worth of CPU. The amp controls are "free" (part of the amp block already).

### Strategy 2: Combine Drive + Amp Into One Character
Instead of a drive pedal + amp block, choose an amp block with slightly more gain. Eliminates one block entirely.

### Strategy 3: One Reverb, Use Scenes for Mix
Instead of two reverb blocks (one per scene), use one reverb block and scene the Mix parameter (0% for dry scenes, 40% for wet scenes). Halves reverb CPU cost.

### Strategy 4: Use Neural Capture Standard (Not Neural)
Neural Captures (the more accurate type) cost more CPU than Standard Captures. For many amp types, Standard quality is indistinguishable in a full-band context.

### Strategy 5: Shared Pre/Post Effects Across Parallel Lanes
In a parallel dual-amp rig, run shared effects (delay, reverb) after the merge point in a single lane, rather than separate delay/reverb blocks in each parallel lane.

**Expensive:**
```
Lane 1: [Amp 1] → [Reverb] → [Output]
Lane 2: [Amp 2] → [Reverb] → [Output]
```

**Cheaper:**
```
Lane 1: [Amp 1] →
Lane 2: [Amp 2] → [Merge] → [Reverb] → [Output]
```

### Strategy 6: Convolution vs. Algorithmic Reverb
Convolution reverbs (using an impulse response of a real space) are CPU-heavy. Algorithmic reverbs (plate, hall, spring) are lighter. For most guitar applications, an algorithmic reverb sounds equally convincing.

---

## CPU Budget Planning

Before building a preset, sketch your budget:

| Budget Item | Estimated CPU |
|---|---|
| Input + Output blocks | ~1% |
| 2x Noise gates | ~3% |
| Drive pedal | ~3% |
| Amp simulation block | ~8–12% |
| Cab IR block | ~5% |
| EQ block | ~2% |
| Compressor | ~3% |
| Modulation (chorus) | ~5% |
| Delay (stereo) | ~8% |
| Reverb (algorithmic, stereo) | ~10–15% |
| **Total (simple rig)** | **~50–60%** |

This leaves 25–35% for additional blocks or more complex reverb. Add a parallel amp lane and you're at 70–75% — still under 85%.

---

## When You're Over Budget: Triage Order

1. Remove/replace the most expensive non-essential block first (shimmer reverb → standard reverb)
2. Convert stereo blocks to mono where the stereo width isn't critical
3. Delete unused parallel lanes entirely
4. Simplify parallel routing to serial if dual-amp is non-essential
5. Replace Neural Capture (Neural) with Neural Capture (Standard)
6. Remove the second noise gate if the amp chain is relatively quiet
7. Simplify modulation (remove one of two chorus/flanger/phaser blocks)

---

## Common Mistakes / Erreurs fréquentes

- Bypassing unused blocks instead of deleting — CPU doesn't decrease
- Building a preset with 4 reverbs (one per lane, parallel) — budget killer
- Using stereo processing on a mono rig — wasted processing
- Not checking CPU meter while building — only discovering the problem at 100%
- Running two Neural Captures (Neural type) simultaneously without checking CPU first

---

## Quick Reference / Référence rapide

| Rule | Value |
|---|---|
| Maximum target CPU | 85% |
| Stereo vs. Mono cost | ~2x for stereo |
| Bypassed block CPU cost | Same as active — delete to free CPU |
| Most expensive block type | Shimmer reverb / polyphonic pitch |
| Free ways to save CPU | Mono mode, shared post-merge FX, Standard capture |
| Check CPU | Swipe down from top bar |
