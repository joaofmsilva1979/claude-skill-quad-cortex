# Getting Started with the Quad Cortex
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Plug in, set your input to match your guitar (Instrument level, high impedance), load a preset, and understand that the grid reads left to right — signal enters lane 1 from the left and exits at the output block on the right.

---

## Hardware Setup First

**Input connections:**
- Input 1 (top left, 1/4"): Your guitar. Set the input switch to **Instrument** (not Line).
- Input 2: Second instrument or effects return.
- Outputs 1/2: To your amp's FX return, power amp, or FRFR speaker.
- Outputs 3/4: Can be used as a separate monitor or second amp send.
- XLR outputs: Direct to FOH. These are always active.

**Input gain (hardware knob):** This is NOT a parameter you set per preset — it's a global hardware trim. Set it so your guitar's loudest pick attack doesn't clip the input meter. The input LED on the front panel should flash green, never red. For passive humbuckers: typically around 12 o'clock. For active pickups: often 8–9 o'clock.

**Impedance:** The QC automatically sets impedance based on what's connected. For vintage single-coil guitars (Strat, Tele), some players prefer to run a buffer pedal first. The QC's input impedance at Instrument level is 1MΩ.

---

## Navigating the Grid

The grid is 8 lanes × 8 columns. Think of it as a virtual pedalboard and amp rack combined.

**Navigation gestures:**
- Tap a block to select it
- Double-tap to open parameters
- Long-press an empty slot to add a block
- Swipe left/right on the grid to scroll (the grid is wider than the screen)
- Pinch to zoom out and see the full signal path

**Signal flow:** Left to right, top to bottom within a split. Lane 1 is at the top. All lanes merge at the output block unless you route them separately.

**Block types:**
- **Input** (auto-placed, top-left): Source selection (Instrument, Return, USB)
- **Stomps/Drives:** Overdrives, fuzzes, boosts
- **Amp blocks:** Amplifier head simulations (e.g., "Brit 2203 JCM800", "US Deluxe Clean")
- **Cab blocks:** Cabinet + microphone simulations (always after the amp)
- **FX blocks:** Modulation, delay, reverb — typically after the cab
- **Output block:** Sets level, panning, and destination for each lane

---

## Your First Preset: Signal Chain Order

A correct basic signal chain:

```
[Input] → [Noise Gate] → [Drive/OD] → [Amp] → [Cab] → [EQ] → [Chorus/Mod] → [Delay] → [Reverb] → [Output]
```

**Rules that matter:**
1. Noise gate goes **before** the amp (or use a dual-stage gate: one before amp, one in the FX loop position)
2. Cab block **always** after the amp block — never before
3. Modulation (chorus, flanger) sounds more natural **after** the cab
4. Time-based effects (delay, reverb) go **last**, after the cab
5. Compressor: before the amp for sustain shaping; after for studio-style peak control

**Adding your first amp block:**
1. Long-press an empty slot
2. Tap "Amp + Cab" to add both in one shot (saves time)
3. The QC adds a matched cab automatically — you can swap it
4. Double-tap the amp block to open its parameters

---

## Essential First Parameters to Adjust

When loading any preset, check these before playing:

| Parameter | What to Check |
|---|---|
| Input level (hardware) | No red clipping |
| Amp Gain | Match to your playing style |
| Amp Master Volume | Doesn't matter for preset, but sets feel |
| Cab IR selection | Try 2–3 IRs before settling |
| Output level | Should be around -18 dBFS average at the output |
| Noise Gate Threshold | High gain: -50 to -40 dB; Clean: off or -70 dB |

---

## Preset Management

**Presets are organized in a grid: 8 banks × 4 presets = 32 preset slots per setlist.**

- Footswitch A/B/C/D select presets within a bank
- Up/Down arrows (footswitches) navigate banks
- Hold a footswitch to enter rename mode

**Saving:** Always use **Save As** when modifying someone else's preset. This prevents overwriting the original. Navigate: Preset menu → Save As → name it.

**Setlists:** Group presets for a gig or genre. You can have multiple setlists. Setlist mode (long-press the setlist icon) lets you reorder presets without changing their bank positions.

---

## Common Mistakes / Erreurs fréquentes

- Running the hardware input gain too hot — causes ugly distortion before the signal hits any block
- Skipping the cab block (sounds harsh and unusable direct)
- Placing reverb before the amp (sounds like a washed-out mess)
- Forgetting to save after editing
- Using 8 lanes with heavy reverb on each — CPU will hit 100%

---

## Quick Reference / Référence rapide

| Task | Action |
|---|---|
| Add a block | Long-press empty slot |
| Move a block | Long-press → drag |
| Delete a block | Select → trash icon |
| Save preset | Preset icon → Save |
| Check CPU | Settings → CPU meter (top bar) |
| Tune your guitar | Hold down footswitch A (default tuner) |
| Factory reset a block | Double-tap → Reset to defaults |
