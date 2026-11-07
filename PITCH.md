# claude-skill-quad-cortex — What it does and why it matters

## The problem

You build a preset. It sounds great. Three weeks later you don't remember what you did.

You watch the same YouTube tutorial twice because you forgot the gate settings.

You spend 45 minutes finding the right amp block for a tone you already built six months ago.

You bring your Quad Cortex to a gig and realise your scenes aren't labelled.

None of this is a gear problem. It's a workflow problem.

---

## What this skill does

`claude-skill-quad-cortex` turns Claude Code into a Quad Cortex co-pilot — six agents, each with a specific job:

| What you need | Agent |
|---|---|
| "Which block parameters control tightness on a JCM800?" | A1 reads your manual and answers |
| "How did The Tone Shepherd set up his reverb chain?" | A2 searches your video transcriptions |
| "Is there a factory preset close to what I want?" | A3 checks your preset library |
| "What presets does my band need for the setlist?" | A4 tracks your band's project |
| "Build it on the hardware, now" | A5 controls the device via USB |
| "Log what we just did" | A6 writes the session journal automatically |

You describe what you want in plain language. Claude does the research, builds the preset, documents the session. You play.

---

## The part that's unusual

A5 — the Builder — talks to your Quad Cortex over USB in real time.

Not a workaround. Not a workaround. The `qc-mcp` server ([github.com/lexasoft123/qc-mcp](https://github.com/lexasoft123/qc-mcp)) reverse-engineered the QC's USB-HID protocol. Claude can add blocks, set parameters, assign stomps to scenes, check CPU load, and save presets — without you touching the touchscreen.

If you don't have the MCP set up, the skill still works: agents A1–A4 and A6 run as normal, and A5 produces a written build plan you can follow manually.

---

## What comes in the box

- **SKILL.md** — the skill itself, copy to `~/.claude/skills/quad-cortex/`
- **15 community guides** in `templates/Transcriptions/` — ready to use as your A2 knowledge base:
  - Scenes & Hybrid Mode
  - Lane routing & parallel rigs
  - John Mayer / Two Rock clean tone
  - High gain (JCM800, Friedman, EVH)
  - Noise gate setup
  - EQ & tone shaping
  - CPU management
  - Captures
  - Live gigging workflow
  - FOH / IEM output setup
  - … and more
- **LOG.md template** — auto-filled by A6 after every session

You don't need to source your own documentation to get started. The guides are already there.

---

## Who this is for

- Quad Cortex owners who use Claude Code (CLI, desktop app, VS Code extension)
- Players who build their own presets and want to work faster
- Bands managing multiple tones across a setlist
- Anyone who has ever rebuilt a preset from scratch because they didn't write it down

---

## Who this is not for

- claude.ai web users — skills don't load there
- Players happy with the Neural DSP Cortex Control app and no need for documentation

---

## Install in 3 steps

```bash
# 1. Get the skill
git clone https://github.com/joaofmsilva1979/claude-skill-quad-cortex
mkdir -p ~/.claude/skills/quad-cortex
cp claude-skill-quad-cortex/SKILL.md ~/.claude/skills/quad-cortex/

# 2. Create your workspace and copy the starter guides
mkdir -p ~/Documents/QuadCortex/Transcriptions
cp claude-skill-quad-cortex/templates/Transcriptions/*.md ~/Documents/QuadCortex/Transcriptions/
cp claude-skill-quad-cortex/templates/LOG.md ~/Documents/QuadCortex/

# 3. Open Claude Code and run
# /quad-cortex
```

First run asks 5 questions. After that, straight to work.

---

## Free. MIT. No account needed beyond Claude Code.

[github.com/joaofmsilva1979/claude-skill-quad-cortex](https://github.com/joaofmsilva1979/claude-skill-quad-cortex)
