# Scenes, Stomps & Hybrid Mode
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Scenes (A–H) are full-preset snapshots — switching scenes changes amp gain, EQ, and effect mixes with zero audio gap. Hybrid mode lets footswitches act as both scene selectors and toggleable stomps simultaneously.

---

## What Are Scenes?

Scenes are saved states of parameters and bypass states for every block in a preset. When you switch from Scene A to Scene B, the QC crossfades parameter values instantaneously — there is no audio gap, no relay click.

**What scenes can store:**
- Block bypass states (amp on/off, drive on/off, reverb on/off)
- Parameter values per block (amp gain, reverb mix, delay level, EQ settings)
- Expression pedal positions (if assigned)

**What scenes cannot do:**
- Change routing (you can't switch from serial to parallel per scene)
- Swap blocks entirely (you can't scene-switch from a Fender amp to a Marshall)
- Independently control output routing

There are **8 scenes per preset** (A through H).

---

## Stomp Mode

In Stomp mode, each footswitch is mapped to a specific block. Press it = toggle bypass. This is the traditional pedalboard experience: each button does one thing.

**Assigning a block to a stomp:**
1. Double-tap the block on the grid
2. Tap the footswitch assignment field
3. Press the footswitch you want to assign

Unassigned blocks can still be triggered from the touchscreen during performance, but footswitch assignment is the live-performance-ready approach.

**Limitation of pure Stomp mode:** You can only control as many blocks as you have footswitches (4 visible at a time, 8 total with bank switching).

---

## Hybrid Mode

Hybrid mode is the most powerful live setup. The top row of footswitches (A–D) selects scenes; the bottom row acts as individual stomps.

**To enable Hybrid mode:**
Settings → Footswitch Mode → Hybrid

**Default Hybrid layout:**
- Top row (A/B/C/D): Scene selectors
- Bottom row (1/2/3/4): Individual stomp toggles (you assign these)

This lets you jump between full tonal setups (clean, crunch, lead, etc.) while still being able to toggle a boost or delay mid-scene without changing the overall tone.

---

## Practical Scene Assignments

A recommended starting template for a rock/blues preset:

| Scene | Name | Config |
|---|---|---|
| A | Clean | Amp gain low (~3), drive OFF, reverb medium, delay OFF |
| B | Clean + Boost | Same as A, compressor ON, reverb up |
| C | Crunch | Amp gain mid (~5-6), light OD ON, reverb low |
| D | Lead | Amp gain high (~7-8), mid-boost drive ON, delay ON, reverb medium |
| E | Lead + Delay | Same as D, delay level up, reverb off |
| F | Ambient | Reverb maxed, gain low, volume swell shimmer |
| G | Tuner / Silent | All blocks bypassed, output muted |
| H | (Spare) | Duplicate of your most-used scene for quick access |

---

## Setting Up Scene Parameters

**To set a parameter per scene:**
1. Navigate to the scene you want to edit (tap A/B/C/D on screen)
2. Double-tap the block you want to adjust
3. Change the parameter
4. The value is now saved for THIS scene only

**To copy a scene:** Long-press a scene letter on the touchscreen → "Copy Scene" → paste to another letter. Use this to create a lead scene that starts as a copy of your crunch scene, then tweak from there.

**Scene naming:** Tap the scene letter on the touchscreen → "Rename." Keep names short — 8 characters max displays cleanly on screen.

---

## Scenes vs. Stomps: When to Use Which

| Situation | Use Scenes | Use Stomps |
|---|---|---|
| Switching entire amp character | Yes | No |
| Turning on a solo boost | Scenes OR Stomps | Yes (simpler) |
| Changing reverb room size per song section | Yes | No |
| Turning a delay on/off during a solo | Either | Yes (muscle memory) |
| Playing covers with 3+ very different tones | Yes (one scene each) | Impractical |

**Key insight:** Scenes are better than patch changes when you need spillover (delay/reverb trails continue while switching). Changing scenes = no audio gap. Changing presets = potential gap + loss of trails (unless spillover is enabled in settings).

---

## Delay/Reverb and Scenes: The Important Caveat

You **cannot** bypass a delay or reverb block per scene using the standard bypass toggle and expect spillover — bypassing cuts the signal. Instead:

- **Scene the mix parameter** to 0% rather than bypassing the block
- This lets trails ring out naturally as you switch scenes
- Keep the delay/reverb block always active, just turn the Mix down to 0% in scenes where you don't want it

---

## Common Mistakes / Erreurs fréquentes

- Trying to bypass a reverb between scenes and cutting reverb tails abruptly — use Mix parameter instead
- Assigning too many blocks to stomp mode and not enough to scenes — hybrid mode is the solution
- Not naming scenes, then forgetting which is which during a gig
- Editing parameters without being in the right scene — always check which scene is active before tweaking
- Using a preset change instead of a scene change for mid-song tone shifts (causes dropout)

---

## Quick Reference / Référence rapide

| Action | Method |
|---|---|
| Enable Hybrid mode | Settings → Footswitch Mode → Hybrid |
| Enter scene edit | Tap scene letter (A-H) on touchscreen |
| Copy a scene | Long-press scene letter → Copy |
| Assign block to stomp | Block parameters → Footswitch field |
| Spillover-safe FX off | Set Mix to 0% per scene, don't bypass block |
| Scene vs preset switch | Scene = same preset, no gap; Preset = new preset, potential gap |
