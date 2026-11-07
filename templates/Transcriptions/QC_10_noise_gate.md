# Noise Gates: Setup & Placement
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Use two gates for high gain: one before the amp (kills guitar hum at source), one after the cab (kills amp hiss). Set threshold by ear — just above where the noise floor disappears, not higher. The Downward Expander is almost always preferable to the Hard Gate.

---

## Why Noise Gates Are Essential

Electric guitars — especially single-coil pickups and high-gain amp chains — generate noise at every stage:
- **60/50 Hz hum:** From single-coil pickups, ground loops, power supplies
- **High-frequency hiss:** From high-gain preamp stages
- **Cable and switching noise:** From long cable runs
- **Interference:** From lighting rigs, computer monitors, wireless systems

A noise gate doesn't eliminate the source of noise — it mutes the signal when it drops below a threshold. When you're playing, signal level is high enough to pass through. When you stop, the signal drops below threshold and the gate closes.

---

## Gate Types on the QC

### Hard Gate
A gate that cuts signal completely when the input drops below threshold. Binary: either fully open or fully closed.

**Use when:** You need total silence between notes (heavy metal chugging, staccato rhythms)
**Risk:** Can sound unnatural — notes cut off abruptly if threshold is set too high

### Downward Expander
Reduces gain gradually rather than cutting to silence. The closer to the threshold, the more gain reduction is applied.

**Use when:** Any situation where natural note decay matters — blues, rock, ambient
**Benefits:** Notes fade out naturally; sounds like silence rather than "someone muted the amp"
**Default choice:** Use Downward Expander unless you specifically need Hard Gate behavior

---

## Gate Parameters Explained

| Parameter | Function | Range |
|---|---|---|
| **Threshold** | Level below which the gate starts to close | -80 to 0 dB |
| **Attack** | How fast the gate opens when signal rises above threshold | 0.1–100 ms |
| **Hold** | How long the gate stays open after signal drops below threshold | 0–500 ms |
| **Release** | How fast the gate closes after hold time expires | 10–2000 ms |
| **Range** | How much gain reduction the gate applies (Downward Expander only) | -80 to 0 dB |

**Setting threshold:** Play your guitar normally, then stop suddenly. Adjust threshold upward from -80 dB until the noise floor disappears when you're not playing. Stop there. Going higher causes the gate to prematurely close during natural note decay.

---

## Two-Gate Placement for High Gain

This is the standard high-gain gate chain:

```
[Input] → [Gate 1] → [Drive Pedal] → [Amp] → [Cab] → [Gate 2] → [Delay] → [Reverb] → [Output]
```

### Gate 1: Pre-Amp Gate
**Purpose:** Kills guitar pickup hum and noise floor before it enters the amp and gets amplified
**Threshold:** -50 to -40 dB (hum is louder here because it's pre-gain)
**Attack:** 2–5 ms (fast — you want it to open quickly when you play)
**Hold:** 50–100 ms
**Release:** 50–100 ms
**Type:** Downward Expander preferred; Hard Gate for extreme metal

### Gate 2: Post-Amp Gate
**Purpose:** Kills residual amp hiss that persists even after Gate 1
**Placement:** After the cab block, before time-based effects
**Threshold:** -65 to -55 dB (amp hiss is lower level than guitar hum)
**Attack:** 5–10 ms (slightly slower — allows attack transients to pass cleanly)
**Hold:** 20–50 ms
**Release:** 100–300 ms (slower = more natural decay)
**Type:** Downward Expander

**Why Gate 2's threshold is lower:** After 60+ dB of amp gain, the signal level is high — but the amp's hiss floor is also high. The gate sees a relatively low signal when you stop playing, but that floor is still above what Gate 1 handles.

---

## Single Gate: When Is It Enough?

For clean and low-gain tones, one gate (pre-amp) is usually sufficient. The amp gain is not high enough to amplify hum dramatically.

**Single gate settings for clean/low-gain:**
- Threshold: -60 to -70 dB
- Attack: 5–10 ms
- Hold: 100 ms
- Release: 200 ms
- Type: Downward Expander

If you notice no appreciable noise with this single gate, turn it off entirely. Active gate = very slight coloration even when open. Unnecessary gating is a subtraction from your tone.

---

## Hum vs. Noise: Different Sources, Different Solutions

Understanding what you're hearing helps set the gate correctly.

| Noise Type | Sound | Source | Gate Setting |
|---|---|---|---|
| 60/50 Hz hum | Low drone/buzz | Single coils, ground loop | Gate 1, medium threshold |
| High-frequency hiss | "Shhh" sound | High-gain preamp | Gate 2, lower threshold |
| Switching noise | Click/pop | FX switching | Gate won't help — fix wiring |
| Interference buzz | Harmonic hum | Nearby electronics | Gate 1 + physical fix needed |

**Gate cannot fix:**
- Ground loop hum that changes pitch (this is a wiring/cable issue)
- Buzz that continues at the same level when you play loudly (gate will open, let it through)
- Wireless receiver noise floor (use a better receiver or wired)

---

## Gate and Note Decay: The Tradeoff

The gate threshold is always a tradeoff:
- **Too high:** Gate cuts off note decay (you hear "chop" at the end of notes)
- **Too low:** Gate doesn't close when it should (noise is audible)

**Finding the sweet spot:**
1. Set threshold at -80 dB (completely open)
2. Listen to the noise floor when not playing
3. Increase threshold slowly until noise disappears
4. Play a long note and let it decay — the gate should let it decay naturally
5. If the note chops, lower threshold by 5 dB and try again

**Note:** Different pickup positions have different noise levels. Single-coil bridge = noisier than neck humbucker. Set your gate for your noisiest configuration so it's adequate in all positions.

---

## Common Mistakes / Erreurs fréquentes

- Threshold set too high — kills note sustain and makes the guitar sound "choppy"
- Using Hard Gate for all situations — Downward Expander is almost always better
- One gate for a high-gain chain — the amp hiss passes Gate 1 (gate is pre-amp) and remains
- Gate placed after delay/reverb — the gate chops the reverb and delay tails
- Chasing a hum source with a gate when the hum needs a physical fix (bad cable, ground loop)
- Not re-checking gate threshold when switching guitars or pickups

---

## Quick Reference / Référence rapide

| Setting | Low Gain | High Gain (pre-amp) | High Gain (post-amp) |
|---|---|---|---|
| Threshold | -70 to -60 dB | -50 to -40 dB | -65 to -55 dB |
| Attack | 5–10 ms | 2–5 ms | 5–10 ms |
| Hold | 100 ms | 50–100 ms | 20–50 ms |
| Release | 200 ms | 50–100 ms | 100–300 ms |
| Type | Downward Expander | Either | Downward Expander |
| Placement | Before amp | Before amp | After cab, before FX |
