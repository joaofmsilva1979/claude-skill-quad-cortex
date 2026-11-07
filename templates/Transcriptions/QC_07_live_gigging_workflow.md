# Live Gigging Workflow
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Build your setlist in Setlist mode, standardize output levels across all presets before the gig, enable spillover in settings, and always have a silent/tuner scene on each preset. Test everything through the actual PA system if possible.

---

## Pre-Gig Preparation

### Build Your Setlist
Setlist mode reorganizes your presets into the song order you'll play them — without moving or renaming the presets in their original banks.

**How to create a setlist:**
1. Settings → Setlists → Create New Setlist
2. Name it (e.g., "Venue 2024-11" or "Cover Band Set 1")
3. Add presets in song order — drag to reorder
4. Each preset slot in a setlist points to the original preset; editing the preset updates the setlist reference automatically

**Setlist navigation live:**
- Next preset: Footswitch Up
- Previous preset: Footswitch Down (or as assigned)
- In setlist mode, you scroll sequentially through the song order

### Level-Match All Presets
Nothing is more unprofessional at a gig than volume jumps between songs. Before the gig:

1. Set a reference level: pick your loudest preset and treat it as 0 dB reference
2. Play each other preset at the same pick intensity and match the output level by ear or by meter
3. Use the **Output block level** (not amp gain) to adjust — this doesn't change tone
4. Target: approximately **-18 dBFS average** output level on the QC meter

**Practical check:** Use the QC's output meter (swipe down from the top bar). Your clean rhythm preset and your lead tone should read roughly the same average loudness.

---

## Spillover: Delay and Reverb Trails Between Presets

Spillover allows delay and reverb tails from one preset to ring out as the next preset loads. Without spillover, switching presets cuts all FX tails instantly.

**To enable:**
Settings → General → Spillover: ON

**Important limitations:**
- Spillover works best between presets with similar FX block structure
- It is not guaranteed across all block types
- CPU overhead increases slightly with spillover enabled

**Alternative (more reliable):** Use scenes within one preset instead of switching presets for songs that need continuous reverb/delay tails. Scene switching is gap-free and always preserves trails.

---

## Tempo Sync

If you use tempo-synced delays or modulation effects (highly recommended), sync the tempo before each song.

**Methods:**
1. **Manual tap:** Hold the Tap Tempo footswitch and tap in the song's beat (4 taps)
2. **MIDI clock:** If using a DAW or drum machine sending MIDI, the QC can receive BPM via MIDI
3. **Fixed BPM per preset:** Set tempo in the preset metadata — the tempo is recalled with the preset

**To set a fixed tempo per preset:**
Preset icon → Tempo → Enter BPM

This is the most reliable live approach: set the song's BPM in the preset when you build it, and it's ready when you switch to that preset.

---

## Tuner

**Activate tuner:** Hold footswitch A (default) or assign to any footswitch.

The tuner **mutes the signal** while active — good for silent stage tuning between songs.

**Tuner settings:**
- Tuning reference: Default is A=440 Hz; adjust if the band tunes differently
- Display: Strobe mode vs. standard — strobe is more accurate for fine-tuning
- Mute output: Confirm this is ON (it is by default)

**Tip:** Assign the tuner to a scene ("Scene G: Tuner") so it's one tap from any scene within your preset. Add "TUNER" as the scene name so it's visible on the display.

---

## Snapshot vs. Full Preset Switch

| Situation | Use |
|---|---|
| Same song, different section (verse/chorus/solo) | Scene switch |
| Different song, different amp character | Preset switch |
| Adding a solo boost mid-song | Stomp toggle (Hybrid mode) |
| Tempo change between songs | Preset switch (new tempo stored) |
| Extended outro with reverb fade | Remain in scene, adjust reverb mix via expression |

Scene switches are always safer live: no risk of audio gaps, no preset loading time.

---

## Expression Pedal Assignment for Live Use

An expression pedal connected to the QC's expression input (or EXP jack) can control multiple parameters simultaneously.

**Common live assignments:**
- Volume swell (overall output or input volume)
- Wah (frequency sweep of a wah block)
- Reverb mix (swell from 0% to 60% for ambient sections)
- Amp gain (smooth transition from clean to crunch)

**To assign:** Double-tap a parameter knob → "Assign to EXP1" → Set min/max values.

---

## In-Ear Monitor (IEM) Setup at the Gig

If you're running IEMs:
- Use Outputs 3/4 for your IEM send (before the main FOH output)
- Set Outputs 3/4 to a mix that suits your on-stage needs (more reverb for comfort, etc.)
- The FOH engineer takes Outputs 1/2 or XLR direct — these can have a different EQ/level

**Output routing:**
- Outputs 1/2 → FOH (via XLR direct or 1/4" to DI box)
- Outputs 3/4 → Stage monitor or IEM transmitter
- Global EQ on Output 1/2: Tune for the room; Output 3/4: Tune for comfort

---

## Day-of-Gig Checklist

- [ ] All presets saved and named
- [ ] Setlist built in correct song order
- [ ] All presets level-matched
- [ ] Tempo set per preset (or Tap Tempo practiced)
- [ ] Tuner accessible from every preset
- [ ] Spillover enabled (if needed)
- [ ] Expression pedal connected and calibrated (hold EXP and move through full sweep to calibrate)
- [ ] Battery charged on QC (if battery-powered rig)
- [ ] USB cable + laptop available for backup if factory reset is needed
- [ ] Spare 1/4" cable

---

## Common Mistakes / Erreurs fréquentes

- Switching presets during a song when a scene switch would be cleaner
- Not testing levels through the actual PA — room acoustics change everything
- Forgetting to tap tempo before the song starts (delay is now on wrong BPM)
- Tuner not muting output — audience hears string noise between songs
- Setting all presets to max output — no headroom for expression pedal volume swells

---

## Quick Reference / Référence rapide

| Task | Action |
|---|---|
| Create setlist | Settings → Setlists → New |
| Enable spillover | Settings → General → Spillover ON |
| Set preset tempo | Preset icon → Tempo |
| Activate tuner | Hold footswitch A (default) |
| Level match | Output block → adjust level to -18 dBFS avg |
| Calibrate expression | Hold EXP jack toe down → heel down |
