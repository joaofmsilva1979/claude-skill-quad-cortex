# Neural Captures: What They Are & How to Use Them
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Captures are neural network snapshots of real amps or pedals — they model the input/output behavior of the hardware at a specific gain setting. They're not the same as amp simulations; they're closer to a highly accurate "photograph" of one operating point.

---

## What Is a Neural Capture?

A Neural Capture uses Neural DSP's machine learning process to characterize how a real piece of hardware (amp, pedal, preamp) responds to an audio signal. The QC plays a sweep of test signals through the hardware, records the output, and trains a small neural network to replicate that input/output relationship.

**Key characteristics:**
- Captures a **specific gain setting** at a specific moment — not a range
- Extremely accurate at the captured operating point
- Rolling guitar volume up and down works (dynamic response is captured), but changing the amp's physical knobs after capture doesn't translate
- The capture doesn't know what a "bass knob" is — it only knows the amp's behavior as configured during capture

**What captures CAN do:**
- Accurately replicate the sonic character of a real amp
- Capture touch dynamics and compression characteristics
- Reproduce pedal clipping behavior

**What captures CANNOT do:**
- Let you change amp parameters (gain, EQ) post-capture
- Capture speaker behavior (you still need a cab IR after a capture of an amp head)
- Replace understanding of the amp (a bad capture of a great amp is still bad)

---

## Neural Captures vs. Standard Amp Simulations

| Aspect | Neural Capture | Amp Simulation Block |
|---|---|---|
| Accuracy | Extremely high at one point | High across a range |
| Adjustability | Fixed (the amp was set before capture) | Fully adjustable parameters |
| Variability | Each capture = one static setting | One block = many settings |
| CPU cost | Low-medium | Medium |
| Use case | "I want THAT amp at THAT setting" | "I want to explore amp character" |

**In practice:** Use captures for specific "holy grail" tones you've heard or owned. Use amp simulation blocks for exploration and when you need to dial in parameters on the fly.

---

## Capturing Your Own Amp

Capturing your own amp is one of the most powerful QC features. You can archive a beloved amp's character forever, or capture a friend's vintage amp.

### Equipment Needed
- Your amp (head or combo) with an effects loop, OR a load box
- Microphone (or direct out if the amp has one)
- Audio interface connected to your Mac/PC
- QC connected via USB
- Neural DSP's capture software (or capture directly on device in later CorOS versions)

### Mic Placement for Captures
Mic placement during capture defines the captured sound permanently — there's no going back. Choose wisely:

| Position | Character | Recommendation |
|---|---|---|
| On-axis, dust cap | Bright, aggressive | High-gain tones, presence-focused |
| On-axis, 1" off cap | Neutral, balanced | General purpose — good starting point |
| Off-axis, 25–50% | Warmer, less harsh | Blues, clean, vintage |
| Off-axis + ribbon blend | Most realistic | Best all-around, requires 2 mics |

**Rule:** More off-axis = warmer and more "in the room." More on-axis = more attack and upper-mid detail.

### Gain Staging Before Capture
The capture hears the signal coming out of your interface/mic. Set levels so:
- Signal peaks at -12 to -6 dBFS (not clipping, not too quiet)
- The amp is at the gain setting you use most often for that tone
- Room noise is minimal (turn off HVAC, fans, etc.)

### Capture Types
- **Standard Capture:** Fast, slightly lower accuracy, good for most amps
- **Neural Capture:** Slower process, higher accuracy, better for complex amp behavior and saturated pedals

Use Neural Capture for amps with complex harmonic content (high gain, cranked vintage amps) and Standard Capture for relatively linear preamps or pedals.

---

## Loading Captures on the QC

1. Download captures from Cortex Cloud (community or Neural DSP official)
2. Connect QC via USB or use the QC Neural Cloud via WiFi
3. In the QC grid, long-press an empty slot → "Neural Capture" → browse
4. The capture appears as a block in your chain

**Capture placement in signal chain:**
- If the capture is an **amp head** (no speaker): place a cab IR block after it, just like an amp simulation block
- If the capture includes a **mic'd amp** (speaker already in the sound): no additional cab IR needed — the speaker character is part of the capture
- If the capture is a **pedal**: place it where you'd put that pedal in the chain

**How to tell if a capture includes a cab:** Listen for the cab's frequency rolloff and "room" character. If it sounds like it was recorded through a speaker, it already has the cab. Check the capture's description on Cortex Cloud.

---

## Mixing Capture + Factory Amp in Parallel

This is an advanced technique that combines the accuracy of a capture with the flexibility of a simulation block.

**Routing:**
```
[Y-Split]
├── Lane 1: [Neural Capture (your amp)] → [Cab IR or no cab if already captured with mic]
└── Lane 2: [Factory Amp Block (similar amp)] → [Cab IR]
[Merge] → [Delay] → [Reverb] → [Output]
```

**Why this works:**
- The capture provides the "soul" of the real amp (exact harmonic character)
- The factory amp provides adjustable parameters (EQ, gain)
- Blending the two at 60/40 or 70/30 gives you a tone that's accurate but flexible
- You can scene-shift the blend ratio to adjust character without changing the entire preset

**Lane level for blending:** Start at both lanes at -6 dB (equal blend). Adjust by ear — the capture lane often benefits from being slightly louder (60–70%) since it carries more authentic character.

---

## Cortex Cloud: Finding Good Captures

**Search strategies:**
- Search the specific amp model: "Plexi 1959", "Dr Z Route 66", "Mesa Boogie Mark V"
- Look at download count + user ratings — popular captures are usually better-vetted
- Filter by "Neural Capture" type for higher-quality results
- Check the description: does it list gain setting, mic used, speaker type?

**Red flags in a capture:**
- Description is vague or missing (you don't know what was captured or how)
- Very low ratings or few downloads on a "featured" capture
- The tone sounds processed or EQ'd before capture (should be flat-ish)

---

## Common Mistakes / Erreurs fréquentes

- Placing a cab IR after a capture that already includes a mic'd speaker — sounds doubly processed
- Expecting to adjust amp gain/EQ after capturing — the knobs are "baked in"
- Capturing in a noisy room — the room acoustics become part of the capture forever
- Using too close an on-axis mic position — capture sounds harsh and un-amp-like
- Confusing a "preamp" capture (needs cab IR) with a "full amp" capture (doesn't need one)

---

## Quick Reference / Référence rapide

| Task | Method |
|---|---|
| Load capture | Long-press slot → Neural Capture → browse |
| Capture type for clean amp | Standard |
| Capture type for high gain/complex | Neural |
| Mic position for capture | Off-axis, 1–2" from cap (balanced starting point) |
| Cab IR needed? | Yes if amp head only; No if mic'd capture |
| Capture gain range | Fixed at the knob position during capture |
| Find captures online | Cortex Cloud (built into QC or via app) |
