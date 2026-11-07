# Covers Band Setup: Managing Many Tones
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** One preset per song is the cleanest system — it eliminates mid-song confusion. Use scenes within each preset for verse/chorus/solo variations, and standardize your output levels so the FOH engineer doesn't have to ride your fader all night.

---

## Philosophy: One Preset Per Song

For a covers band playing 30+ different songs across multiple genres, the QC's preset system is your best friend — if you organize it correctly.

**Recommended structure:**
- Each setlist = one full set (e.g., "Set 1 — Covers Night")
- Each preset = one song
- Each scene within the preset = one section of the song (clean verse, crunchy chorus, lead solo)
- Stomps in Hybrid mode = momentary toggles (boost, wah on/off)

This means: when you switch to a new song's preset, the amp, cab, and base EQ are already correct for that song's character. You're not scrambling to stomp multiple things at once.

---

## Organizing Presets by Song

**Naming convention that works:**
- Format: `[Genre Icon]-[Song Name]-[Artist]`
- Example: `R-Satisfaction-Stones` or `B-Little Wing-Hendrix`

**Bank organization:**
- Bank 1: Set 1 songs (songs 1–16)
- Bank 2: Set 2 songs
- Bank 3: Specials / encores / requests
- Bank 4: Work in progress / new songs

Since presets in a setlist are ordered independently from bank position, your bank organization is for backstage management, not live performance.

---

## Style-Switching: What to Change Per Song

| Song Style | Amp | Cab | Drive | EQ Change |
|---|---|---|---|---|
| Classic Rock (Stones, Zeppelin) | Brit 2203 (JCM800) | 4x12 Greenback | Light OD | Presence +1–2 |
| Blues (SRV, BB King) | US Deluxe Clean | 1x12 Jensen | Tube Screamer | Treble +1 |
| Funk (Chic, RHCP) | US Double (Twin) | 2x12 Clean | Comp only | Mid -1 |
| Modern Rock (Foo Fighters) | Friedman BE-100 | 4x12 V30 | Green 808 | Standard |
| Pop/Country | Vox AC30 | 2x12 Blue | None | Treble +2 |
| Metal (Metallica) | EVH 5150 / Recto | 4x12 Mesa | Tight gate | Low-cut up |

**The goal isn't perfect recreation** — it's convincing in the mix. A Twin Reverb approximation that sounds right in context is better than a "correct" amp that takes 20 minutes to dial in.

---

## Standardizing Output Levels Across Presets

This is the single biggest quality-of-life improvement for a covers band. FOH engineers will thank you.

**Procedure:**
1. Use a reference preset (your most common rhythm tone) as 0 dB baseline
2. Set up a simple output level measurement: play a consistent riff at standard intensity
3. For each song preset, adjust the **Output block** level until it matches the reference
4. Aim for -18 dBFS average on the QC output meter
5. Leave headroom: lead tones should be at most +3 dB above rhythm (apparent loudness boost via frequency shaping is usually more effective than raw volume boost)

**Lead tone volume boost without raising overall level:**
- Mid-range EQ boost (+2–3 dB at 1–2 kHz) cuts through the mix better than raw level
- This is the classic "presence boost" approach — the solo feels louder without clipping FOH

---

## Quick Style Switching: Hybrid Mode for Covers

With Hybrid mode (scenes on top row, stomps on bottom):

**Example: "Comfortably Numb" preset**

| Scene | Section | Config |
|---|---|---|
| A | Intro clean | Twin-style clean, light reverb |
| B | Verse | Same clean + slight warmth |
| C | First chorus | Crunch, mid-gain amp |
| D | Solo 1 (Gilmour) | High-gain lead, delay, smooth reverb |
| E | Outro solo | Same as D + more sustain, reverb up |

**Stomps (Hybrid bottom row):**
- Stomp 1: Wah (Clyde or Vox wah)
- Stomp 2: Delay toggle (eighth note)
- Stomp 3: Boost (+3 dB for hottest solo moments)
- Stomp 4: Tuner / mute

This setup handles the entire song without touching the touchscreen — only footswitches.

---

## Managing a Large Song Library

**When you have 60+ songs:**
- Use setlists aggressively: build a new setlist for each venue/format rather than reordering presets
- Build "template" presets for each genre and clone them as starting points for new songs
- Color-code (if the QC supports preset color tagging in your firmware) by genre

**Template presets to build once and clone:**
- `TEMPLATE-ClassicRock` — JCM800, Greenback, light OD
- `TEMPLATE-BluesClean` — Twin, Jensen, compressor
- `TEMPLATE-ModernRock` — Friedman, V30, Green 808
- `TEMPLATE-Metal` — 5150, Mesa, full gate chain

When adding a new song, clone the closest template → rename → fine-tune.

---

## Scenes Per Song: Practical Examples

### "Pride (In the Name of Love)" — U2 style
- Scene A: Edge-of-breakup clean, long dotted-eighth delay
- Scene B: Same + slight OD for the chorus drive
- Scene C: Fully clean, reverb up, for the outro arpeggios
- Stomp 1: Delay toggle (signature Edge delay on/off)

### "Back in Black" — AC/DC style
- Scene A: Crunch rhythm — Brit 2203, 7/10 gain, no drive pedal
- Scene B: Same + slight mid boost for fills
- Scene C: Lead — same amp, solo boost drive ON, presence +1
- Scene D: (unused — AC/DC doesn't need 4 tones)

### "Purple Rain" — Prince style
- Scene A: Clean neck pickup, light chorus
- Scene B: Clean + reverb up for the ballad sections
- Scene C: Lead — OD drive ON, reverb, volume up slightly
- Stomp: Wah for the solo

---

## Common Mistakes / Erreurs fréquentes

- Trying to do an entire set with 3–4 presets and too many stomps — chaotic live
- Different output levels per preset — FOH engineer constantly adjusting
- Not naming scenes descriptively — forgetting which scene is "solo" mid-song
- Building presets with zero scenes — forced to change entire preset for every song section
- Over-engineering presets with 8 scenes when 3 would cover the song

---

## Quick Reference / Référence rapide

| Task | Method |
|---|---|
| Clone a preset | Preset list → long-press → Duplicate |
| Rename a scene | Tap scene letter → Rename |
| Level-match presets | Output block → adjust to -18 dBFS avg |
| Create a setlist | Settings → Setlists → New |
| Add preset to setlist | Setlist edit → "+" → choose preset |
| Reorder setlist | Drag preset in setlist edit view |
