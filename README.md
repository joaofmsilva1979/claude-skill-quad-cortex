# Claude Code Skill — Neural DSP Quad Cortex

> 🇫🇷 Skill bilingue FR/EN — Claude s'adapte à la langue que tu utilises.
> 🇬🇧 Bilingual FR/EN skill — Claude adapts to the language you use.

A [Claude Code](https://claude.ai/code) skill that turns Claude into a full Quad Cortex assistant: manual lookup, YouTube technique research, preset library, band project management, live device control (via MCP), and automatic session documentation.

---

## What it does / Ce que ça fait

| Agent | Role |
|---|---|
| **A1 Manual** | Hardware reference — block parameters, firmware, I/O |
| **A2 Transcriptions** | Practical tips from YouTube educational videos |
| **A3 Presets** | Factory and custom preset library |
| **A4 Band** | Band/project preset state and setlist coherence |
| **A5 Builder** | Live preset building on the device *(requires MCP)* |
| **A6 Doc** | Automatic session journal and preset documentation |

---

## Requirements / Prérequis

- [Claude Code](https://claude.ai/code) installed
- A Neural DSP Quad Cortex
- *(Optional but recommended)* The `quad-cortex` MCP server — see [MCP Setup](#mcp-setup) below

---

## Installation

### 1. Copy the skill

```bash
mkdir -p ~/.claude/skills/quad-cortex
cp SKILL.md ~/.claude/skills/quad-cortex/SKILL.md
```

### 2. Create your workspace

Pick a folder for your QC documentation. Example:

```bash
mkdir -p ~/Documents/QuadCortex/Manual
mkdir -p ~/Documents/QuadCortex/Transcriptions
mkdir -p ~/Documents/QuadCortex/Presets/factory
mkdir -p ~/Documents/QuadCortex/Presets/notes
mkdir -p ~/Documents/QuadCortex/Backups
mkdir -p ~/Documents/QuadCortex/Band/MyBand
```

### 3. Populate your workspace

| Folder | What to put there |
|---|---|
| `Manual/` | QC User Manual — download the HTML version from [Neural DSP](https://neuraldsp.com/quad-cortex) |
| `Transcriptions/` | YouTube videos converted to text — use [yt-dlp](https://github.com/yt-dlp/yt-dlp) + subtitles, or paste transcripts manually. Name them `YT_<topic>.txt` |
| `Presets/factory/` | Export your factory presets index from the QC or the Neural DSP Cloud |
| `Presets/notes/` | Your own `.md` notes about custom presets |
| `Band/<name>/` | Band-specific preset notes and session logs |

### 4. MCP Setup

> Skip this if you only want manual lookup and documentation (A1–A4, A6). The MCP is only required for A5 (live device building).

The `quad-cortex` MCP server communicates with your Quad Cortex over USB.

**Install:**
```bash
# Clone and install the qc-mcp server
git clone https://github.com/lexasoft123/qc-mcp
cd qc-mcp
uv sync          # or: pip install .
```

**Register with Claude Code:**
```bash
claude mcp add quad-cortex /path/to/qc-mcp/.venv/bin/qc-mcp
# Replace /path/to/qc-mcp with your actual clone path
```

**Verify:**
```bash
claude mcp list
```

You should see `quad-cortex` in the list.

---

## Usage / Utilisation

In any Claude Code session, invoke the skill:

```
/quad-cortex
```

Or describe what you want:

```
/quad-cortex I want a John Mayer clean tone with a parallel reverb chain
```

```
/quad-cortex je veux un son high-gain pour du rock, basé sur un JCM800
```

On first run, Claude will ask you 5 setup questions (workspace path, MCP status, context, style, band name). After that it goes straight to work.

---

## Workflow example / Exemple de workflow

```
You: /quad-cortex build me a Foo Fighters tone, scenes for verse/chorus/solo

Claude:
  → A1: looks up relevant blocks in the manual
  → A2: finds the Foo Fighters YT transcription tips
  → A3: checks if a matching factory preset exists
  → A5: builds on device (empty slot, checks CPU < 85%)
  → A6: logs the session in LOG.md
```

---

## Tips for Transcriptions / Conseils pour les transcriptions

The more educational YouTube videos you convert to text, the better A2 gets.

Good channels to transcribe:
- The Tone Shepherd
- Neural DSP official tutorials
- Worship Tutorials (for clean/ambient)
- Any "how I built this preset" walkthrough

**Quick convert on macOS (from .docx):**
```bash
textutil -convert txt -stdout "YT_MyVideo.docx"
```

**From YouTube subtitles (yt-dlp):**
```bash
yt-dlp --write-auto-sub --sub-format vtt --skip-download -o "YT_%(title)s" "<URL>"
```

---

## LOG.md template

A starter `LOG.md` is included in `templates/LOG.md`. Copy it to your workspace root.

---

## Contributing / Contribuer

Pull requests welcome. Things that would help the community:

- 🇬🇧 Transcriptions of popular QC YouTube tutorials (anonymised, no copyright content)
- Preset JSON examples for the `Presets/factory/` folder
- Tips on specific block combinations that work well

---

## License

MIT — use freely, share widely.

---

*Made with [Claude Code](https://claude.ai/code)*
