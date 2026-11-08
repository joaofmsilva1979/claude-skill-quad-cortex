# Common Mistakes to Avoid
*Neural DSP Quad Cortex — Community Guide*

> **TL;DR:** Most tone problems on the QC come from the same five mistakes: too many effects, mismatched amp+cab, broken gain staging, missing high/low cuts, and dialing in at bedroom volume. Fix these in order and your tone changes more than any preset swap.

*Source: "5 Quad Cortex MISTAKES to avoid" + "Quad Cortex Tips I Wish I Knew Sooner" — Devin Bishop*
*https://www.youtube.com/watch?v=A07q_lnY20Q | https://www.youtube.com/watch?v=pRKTWIA678g*

---

## Mistake 1 — Too Many Effects

**Rule of thumb:** if your tone needs 6–10 pedals to sound good, your amp and cab aren't dialed in yet.

**How to diagnose:**
1. Turn off every effect block.
2. Listen to amp+cab alone. Is the top end piercing? Is the low end muddy?
3. Fix those problems at the amp/cab level first.
4. Add effects back one at a time. Ask: *"Is this adding to my tone or subtracting from it?"*

Effects that don't survive this test get removed, not just bypassed.

---

## Mistake 2 — Ignoring the Cab

**The cab changes your tone more than you think.** Two identical amp blocks with different cabs will sound radically different — not just "slightly different."

- Same amp, switch cabs: listen for low-end weight, top-end fizz, mid presence.
- A cab that adds too much low end makes the mix muddy regardless of EQ.
- Pair amp and cab as a unit. If the amp sounds right but the cab sounds wrong, the cab is the problem.

---

## Mistake 3 — Broken Gain Staging

Gain staging is not just the amp gain knob. Check every point in the chain:

| Point | What to check |
|---|---|
| Input | Is the signal registering properly? (Some guitars need +10–17 dB boost at input) |
| Compression | Is it pushing the amp harder than you want? |
| Overdrive/Distortion | Is it stacking with amp gain unintentionally? |
| Amp gain | Gain = breakup. Volume = output level. These are not the same. |
| Amp volume | Use this to compensate after setting gain. |
| Cab | No gain here, but placement matters for IR response. |
| EQ blocks | No clipping. |
| Output | Check the output meter. If it clips, reduce somewhere upstream. |

**Key distinction:** pushing amp *gain* makes it break up more. Pushing amp *volume* makes it louder without adding distortion. Use both levers intentionally.

**Output check:** monitor your output level while playing. If it's clipping (hitting -8 or -9 dB consistently), reduce input gain or amp volume — don't just pull the output fader.

---

## Mistake 4 — No High/Low Cuts

Real amps don't reproduce sub-bass rumble or extreme high-end fizz — they're physically not built for it. The QC models the amp, but the full frequency range still passes through.

**Where to put them:**
- **Cab block** (simplest): add a high-cut and a low-cut directly in the cab parameters.
- **EQ block** (more control): use a low-pass filter (~6–8 kHz) and a high-pass filter (~80–120 Hz). Place it after the cab.

**Typical ranges:**
- Low cut (high-pass): 20–80 Hz (removes sub-bass rumble)
- High cut (low-pass): 6,000–8,000 Hz (removes digital fizz)

It's subtle. It's also the difference between "good tone" and "this sounds like a real amp."

**Mud fix (bonus):** if the QC sounds muddy in the 200–500 Hz range, roll off gradually: more cut at 60 Hz, less at 125, less at 250, less at 500. This is more surgical than a simple high-pass and fixes the specific "blanket over the amp" problem common on modelers.

---

## Mistake 5 — Dialing In at Bedroom Volume

Tone at low volume ≠ tone at gig volume. At higher volumes:
- Low end gets louder relative to mids (Fletcher-Munson effect)
- Gain stages that sounded balanced start to feel excessive
- Fizz that was hidden becomes obvious

**How to test without destroying your hearing:**
- Play in a garage or outdoors at moderate volume.
- Record yourself and listen on: headphones, car speakers, phone speaker, studio monitors.
- If the tone sounds different across playback sources, adjust — don't just optimize for one.

---

## The Order That Works

Strip everything back → dial amp+cab → add high/low cuts → fix gain staging at every point → add effects one by one → test at different volumes.

Don't swap presets until you've done this. The QC can sound like a great amp — most tone problems come from skipping these fundamentals.
