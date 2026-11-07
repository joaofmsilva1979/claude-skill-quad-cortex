# Output, FOH & IEM Setup
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Run your QC at -18 dBFS average output to the board. Use the cab IR to shape tone before FOH — always include one. Use Global EQ to compensate for the room, not individual presets. Use separate outputs for FOH vs. IEM so each can be tuned independently.

---

## Understanding QC Outputs

The Quad Cortex has four 1/4" outputs and two XLR outputs (balanced, direct):

| Output | Type | Use |
|---|---|---|
| Output 1/2 | 1/4" balanced | Main stereo outs → amp FX return, power amp, FRFR |
| Output 3/4 | 1/4" balanced | Aux send → monitor, second amp, IEM transmitter |
| XLR L/R | Balanced, low impedance | Direct to mixing console (FOH) |

**XLR vs. 1/4" for FOH:**
Both can go to FOH, but XLR is preferred for long cable runs (noise rejection). The XLR outputs are always active — they mirror Outputs 1/2 unless you route them separately.

---

## The Output Block

Every signal path ends at an **Output block** in the grid. This block controls:
- **Level:** Volume of this lane's signal (-60 to +6 dB, or as a percentage)
- **Pan:** Left/right position in the stereo field
- **Destination:** Which physical output this lane sends to (Output 1/2, 3/4, etc.)

**Standard output level:** Set the Output block so your average playing level reads **-18 dBFS** on the QC output meter. This leaves headroom for dynamics and matches pro audio standards.

**Why -18 dBFS?** It is the alignment standard between consumer/pro gear. FOH engineers expect signals in this range. Too hot (+0 dBFS) = digital distortion. Too quiet (-30 dBFS) = floor noise becomes audible at high PA gain.

---

## Cabinet IR Placement for DI

If you're going direct to FOH (no real speaker cabinet), you **must** include a Cabinet IR block before the output. Without it, the amp simulation sounds harsh, trebly, and unusable in a PA.

**Correct chain for direct out:**
```
[Amp Block] → [Cab/IR Block] → [Output]
```

**Choosing IRs for direct:**
- Use a neutral, well-balanced IR (not heavily EQ'd or processed)
- Avoid IRs that have already been mixed with room sound or reverb
- ML Sound Lab, York Audio, and Celestion Impulse Responses are well-regarded for DI use

**High-cut after cab:** Add a high-pass filter at **5–7 kHz** after the cab block if the top end sounds fizzy at the PA. This smooths the high-frequency artifacts of cabinet simulation.

---

## Global EQ

The Global EQ affects the final output signal before it leaves the QC — it applies to **all presets** without changing individual preset settings. It's your room correction tool.

**Access:** Settings → Global EQ (or swipe down from status bar → Global EQ icon)

**Use Global EQ for:**
- Cutting room-specific frequencies (a boomy room: cut 200–300 Hz; a harsh room: cut 2–5 kHz)
- Compensating for FRFR speaker coloration
- Adjusting for different venues without editing presets

**Do not use Global EQ for:**
- Fixing individual preset tone problems — fix those in the preset
- Making dramatic EQ moves (+/- more than 6 dB) — if you need that much, something is wrong upstream

**Common Global EQ starting points:**
- Venue with low ceilings: High-pass at 100 Hz to reduce room boom
- Bright venue/PA: -2 to -3 dB shelf at 5 kHz
- FRFR speaker: Every FRFR colors tone slightly — Global EQ is the right correction tool

---

## Separating FOH and Monitor/IEM Outputs

**Standard routing:**
- Output 1/2 (or XLR): FOH signal — includes cab IR, final EQ
- Output 3/4: Stage monitor or IEM signal — same signal by default, or different if routed separately

**To create a separate IEM mix:**
1. In the grid, route a parallel lane to Output 3/4
2. This lane can have different reverb, different EQ (more reverb is comfortable in IEMs; less low-end so you can hear the kick drum)
3. The FOH engineer doesn't hear this — it's your personal monitor mix

**IEM signal characteristics:**
- Less reverb than FOH (reverb in IEMs can mask stage cues)
- Slightly more mid presence (helps cut through drum bleed in IEMs)
- Low-cut at 100 Hz (removes HVAC/room rumble)
- Level: set to comfortable listening level in your IEMs — not matching FOH

---

## Running With a Real Power Amp or FRFR

If you're using a guitar power amp + real speaker cabinet, or an FRFR (Full Range, Flat Response) speaker:

**With FRFR (e.g., Headrush FRFR-108, Line 6 Powercab, Atomic CLR):**
- Keep the cab IR block in your chain — FRFR is flat, it needs the cab simulation
- The FRFR's EQ should be as flat as possible; use Global EQ to compensate
- Run at line level from Output 1/2

**With a traditional power amp + real guitar cabinet:**
- **Remove** the cab IR block from your chain (the real cabinet provides the cab sound)
- Use the Output block's level to match your power amp's input sensitivity
- Run from Output 1/2 to the power amp's input

**With an amp's FX return:**
- Same as power amp + real cabinet: remove the cab IR block
- Level sensitivity depends on the specific amp — start at 50% output level and increase

---

## DI Direct: Zero Amp on Stage

Many modern stages prefer the guitarist to run completely silent on stage (IEMs, no floor wedge, no amp):

**Complete DI setup:**
- QC → XLR direct → FOH console
- FOH gets your full processed signal (amp + cab + effects)
- Your IEM mix comes from the console's aux send back to your ears
- No amp on stage means zero bleed into drum mics and vocal mics

**Signal chain:**
```
[Input] → [Gate] → [Drive] → [Amp] → [Cab IR] → [EQ] → [Delay] → [Reverb] → [Output → XLR]
```

This setup requires you to trust your IEM mix — the most common complaint is "I can't feel the guitar." A sub-packer or guitar amp behind you (not mic'd) for air movement is a valid compromise.

---

## Common Mistakes / Erreurs fréquentes

- No cab IR block when going direct — sounds harsh and buzzy in the PA
- Output level too hot (above -12 dBFS) — FOH engineer's preamp clips
- Using Global EQ to fix individual preset problems — fix them in the preset
- Routing IEM and FOH to the same output with no independent control
- Forgetting to set IEM level separately — IEMs can cause hearing damage if too loud

---

## Quick Reference / Référence rapide

| Parameter | Value |
|---|---|
| Target output level (FOH) | -18 dBFS average |
| Cab IR requirement (DI) | Always include |
| High-cut after cab (fizz control) | 5–7 kHz |
| FOH output | Output 1/2 or XLR |
| IEM/monitor output | Output 3/4 (routed separately) |
| Global EQ typical cuts | 200–300 Hz (boom) or 2–5 kHz (harsh) |
| Power amp / FRFR: cab IR | Keep (FRFR) or remove (real cabinet) |
