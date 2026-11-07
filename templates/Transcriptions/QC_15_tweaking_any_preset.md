# Tweaking Any Preset: Systematic Approach
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Always work in the same order: input gain → amp gain/EQ → cab IR → output level → effects. Never adjust effects before the amp is dialed in. Isolate one variable at a time. A/B compare by toggling a bypass, not by memory.

---

## Why Order Matters

Tweaking a preset is a chain reaction. Changing the amp's bass affects how the cab sounds. Changing the cab affects how much EQ you need. Changing the EQ affects the perceived output level. If you adjust things in random order, you'll chase your tail.

The right order mirrors the signal flow — start at the beginning, work toward the end.

---

## The Systematic Tweaking Order

### Step 1: Input Gain (Hardware)
Before touching any block, confirm the hardware input gain is set correctly.
- Play your hardest downstroke — the input LED should flash green, never red
- If your guitar clips the input before the amp, all subsequent fixes are addressing a corrupted signal

### Step 2: Amp Gain
Set the amp gain for the right amount of saturation at your playing intensity.
- For clean: gain 2–4 (no breakup on hard picking)
- For crunch: gain 5–6 (subtle breakup on hard strumming, clean when picking single notes gently)
- For lead/high gain: gain 7–9 (sustained, compressed, with controlled saturation)

**Don't touch effects yet.** Play clean through the amp into the cab — no reverb, no delay. The amp must sound right dry first.

### Step 3: Amp EQ (Bass/Mid/Treble/Presence)
With the amp gain set, adjust the amp's tone controls to get the broad tonal balance right.
- Reference position for all controls: 12 o'clock (5/10)
- Adjust by ear: too dark → raise treble; too bright → lower treble; muddy → lower bass; thin → raise bass; honky → lower mid
- Presence and Resonance: Presence = upper harmonic content; Resonance = low-end weight (porting effect)

Target: the amp should sound like a good amp in the room through reference monitors or headphones. It doesn't have to be perfect — that's what cab and EQ are for.

### Step 4: Cab IR Selection
The cab IR can completely transform the tone. Spend time here — it's the second most important variable after amp gain.

- Try 3–5 IRs before committing
- Use the same pick attack and volume for each IR test
- Narrow criteria: eliminate any that are too bright/harsh in the first 5 seconds
- Among the remaining: choose the one with the best note separation (each string of a chord sounds distinct)

**After choosing the IR:** Check the low end (too much sub-bass? add a high-pass filter at 80–100 Hz) and the high end (fizzy? gentle low-pass at 6–8 kHz).

### Step 5: Output Level
Before adding effects, set the output level to your standard reference (-18 dBFS average).
- Play a typical rhythm passage and watch the output meter
- Adjust the Output block level until the meter reads approximately -18 dBFS average
- Leave headroom — your loudest moments (solos) should not exceed -12 dBFS

This prevents effects from obscuring a hidden gain/volume mismatch.

### Step 6: Effects (in signal chain order)
Now add and tune effects, working in the order they appear in the chain:
1. Gate (threshold: just above noise floor)
2. Drive/compressor (if used)
3. Modulation (chorus, flanger — tune rate and depth)
4. Delay (time, feedback, mix — sync to tempo)
5. Reverb (size, decay, mix — last in chain)

Tune each effect with the others engaged so you hear them in context.

---

## Common Problems and Fixes

### "Too muddy / indistinct"
**Root cause:** Excess low-mid frequencies, often compounded by reverb
1. Lower amp Bass to 4–5
2. Add a high-pass filter at 100–120 Hz (before or after amp)
3. Reduce reverb Mix by 10%
4. If still muddy: EQ cut at 200–400 Hz

### "Too bright / harsh"
**Root cause:** Treble or presence too high, or cab IR has exaggerated upper midrange
1. Lower amp Treble to 5–6
2. Lower Presence to 4–5
3. Add a gentle low-pass filter after cab at 6–7 kHz
4. If still bright: check if the cab IR has an aggressive 2–4 kHz peak (try a different IR)

### "Sounds flat / no life"
**Root cause:** Compressed or lacking in midrange presence
1. Raise Presence 1–2 steps
2. Add subtle harmonic drive (Tube Screamer at 0% gain, 60% level) before amp
3. Raise amp Mid slightly (5–6)
4. Check the compressor is not over-compressed (reduce ratio or raise threshold)

### "Too compressed / no dynamics"
**Root cause:** Too much amp gain, compressor too aggressive, or capture at wrong operating point
1. Lower amp gain 1–2 steps
2. If using a compressor: reduce ratio (3:1 → 2:1) or raise threshold
3. If using a capture: try a different capture at a lower gain setting

### "Lost in the mix during band practice"
**Root cause:** Frequency conflict with bass guitar or other instruments
1. Boost at 1–2 kHz (presence zone — guitars' "cut-through" range)
2. Cut at 200–400 Hz (conflicts with bass guitar)
3. Add a gentle mid-boost EQ block (+2 dB shelf at 1 kHz)
4. Raise output level slightly (but match other presets afterward)

### "Solo doesn't sit above rhythm"
**Root cause:** Perceived loudness is determined more by frequency content than raw level
1. Add a drive block assigned to solo scenes: low gain, high level (functions as a boost)
2. Raise mid-presence for solo scenes (+2 dB at 1–2 kHz)
3. Turn delay Mix up slightly (delays add perceived density and length to notes)
4. If using a compressor: add it only on solo scenes to increase sustain

---

## A/B Comparison Technique

Memory is unreliable for tone comparison. A/B properly:

**Within a preset (comparing scenes):**
- Set Scene A as your reference (current sound)
- Set Scene B as your modified version
- Switch between A and B rapidly while playing — the difference should be immediately apparent

**Between two presets:**
- Set both presets in adjacent slots
- Footswitch between them while sustaining a note or chord
- Level-match both presets first — a louder sound always seems "better"

**Block bypass A/B:**
- Activate the block you want to test
- Play → bypass the block → play again
- If the difference is positive, keep it; if neutral or negative, delete the block

---

## Saving Progressively

Work with Save As at key milestones:
- `MySong_v1` — initial setup
- `MySong_v2` — after amp and cab are dialed
- `MySong_v3` — after effects
- `MySong_FINAL` — after band context testing

This creates a rollback path. It's easy to over-tweak — having v2 to compare against is invaluable.

---

## Common Mistakes / Erreurs fréquentes

- Adjusting reverb and delay before the amp is properly dialed in — effects mask amp problems
- Tweaking at bedroom volume and discovering the preset doesn't translate to stage volume
- Comparing tones from memory rather than by real-time A/B switching
- Making EQ adjustments to fix problems that originate from the wrong cab IR
- Not level-matching before A/B comparison — louder always wins perceptually
- Saving every 5 minutes without version names — can't roll back to a good state

---

## Quick Reference / Référence rapide

| Step | Focus | Don't Move On Until |
|---|---|---|
| 1. Input gain | Hardware knob | LED never clips red |
| 2. Amp gain | Saturation/breakup point | Right amount for the genre |
| 3. Amp EQ | Broad tonal balance | Sounds like a good amp dry |
| 4. Cab IR | Character, definition | 3-5 IRs tested, one chosen |
| 5. Output level | -18 dBFS average | Metered and confirmed |
| 6. Effects | Gate → Drive → Mod → Delay → Reverb | Each tuned in context |
