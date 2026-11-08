---
name: quad-cortex
description: Neural DSP Quad Cortex orchestrator — 6 specialized agents for manual lookup, YouTube technique research, preset library, band/project context, live device building (MCP), and session documentation. Invoke for any QC work — hardware or software.
---

# Neural DSP Quad Cortex — Claude Code Skill

> 🇫🇷 Ce skill est bilingue. Réponds à Claude dans la langue de ton choix, il s'adapte.
> 🇬🇧 This skill is bilingual. Reply to Claude in your preferred language, it adapts.

---

## First Run — Onboarding / Configuration initiale

**If no `QC_BASE` path is set in this conversation**, ask the user the following questions before doing anything else. Wait for all answers before proceeding.

---

### Questions to ask / Questions à poser

**Q1 — Workspace path / Dossier de travail**

> 🇬🇧 Where should I store your QC documentation and session logs?
> This will be your `QC_BASE` folder. Example: `~/Documents/QuadCortex/` or a Google Drive path.
>
> 🇫🇷 Où stocker la documentation QC et les journaux de session ?
> Ce sera ton dossier `QC_BASE`. Exemple : `~/Documents/QuadCortex/` ou un chemin Google Drive.

**Q2 — MCP server / Serveur MCP**

> 🇬🇧 Do you have the `quad-cortex` MCP server installed in Claude Code?
> (This is needed to build/modify presets directly on the hardware.)
> → Yes / No / What is that?
>
> 🇫🇷 As-tu le serveur MCP `quad-cortex` installé dans Claude Code ?
> (Nécessaire pour construire/modifier des presets sur le boîtier physique.)
> → Oui / Non / C'est quoi ?

If the user answers **No** or **What is that**, display this:

```
── MCP Setup / Installation MCP ──────────────────────────────────────

🇬🇧 The quad-cortex MCP server lets Claude control your Quad Cortex
directly over USB — building presets, setting parameters, managing scenes.

Install steps:
1. Plug your Quad Cortex into USB and power it on.
2. Install the MCP server (see README for the link).
3. Add it to your Claude Code settings:
   claude mcp add quad-cortex <command>
4. Restart Claude Code and re-invoke /quad-cortex.

Without MCP, all agents work EXCEPT A5 (Builder).
You can still research tones, build plans, and document everything.

🇫🇷 Le serveur MCP quad-cortex permet à Claude de contrôler ton boîtier
directement via USB — construire des presets, régler les paramètres, gérer les scènes.

Sans MCP, tous les agents fonctionnent SAUF A5 (Builder).
Tu peux quand même rechercher des tones, planifier et documenter.
──────────────────────────────────────────────────────────────────────
```

**Q3 — Context / Contexte d'usage**

> 🇬🇧 What is your main use case?
> (a) Live / gigging    (b) Studio / recording    (c) Both    (d) Home practice
>
> 🇫🇷 Quel est ton contexte principal ?
> (a) Live / scène    (b) Studio / enregistrement    (c) Les deux    (d) Pratique maison

**Q4 — Style**

> 🇬🇧 What is your primary playing style?
> (a) Clean / funk    (b) Blues / crunch    (c) Rock    (d) High-gain / metal    (e) Mixed
>
> 🇫🇷 Quel est ton style principal ?
> (a) Clean / funk    (b) Blues / crunch    (c) Rock    (d) High-gain / métal    (e) Mixte

**Q5 — Band / Project (optional)**

> 🇬🇧 Do you have a band or project? (optional — used to create a dedicated subfolder)
>
> 🇫🇷 Tu as un groupe ou un projet ? (optionnel — crée un sous-dossier dédié)

---

### After onboarding / Après l'onboarding

Once answers are collected:

1. **Confirm the workspace structure** that will be created (see below).
2. Set `QC_BASE = <user answer to Q1>` for the rest of the session.
3. If a band/project was given, set `QC_BAND = QC_BASE/Band/<band-name>/`.
4. Suggest creating the folder structure with a single `mkdir -p` command.

**Workspace structure to propose:**

```
QC_BASE/
├── Manual/              # QC User Manual (HTML or PDF — download from Neural DSP)
├── Transcriptions/      # YouTube educational videos converted to .txt or .docx
│   └── YT_*.docx        # Naming convention: YT_<topic>.docx
├── Presets/
│   ├── factory/         # Factory preset exports (JSON / CSV)
│   └── notes/           # Your custom preset notes (Markdown)
├── Backups/             # Preset backups exported from the QC
├── Band/                # Optional: one subfolder per band/project
│   └── <band-name>/
│       ├── presets.md   # Band preset list and descriptions
│       └── LOG.md       # Band-specific session journal
├── LOG.md               # Main session journal (auto-updated by Agent A6)
└── README.md            # Your personal rig notes
```

**mkdir command to offer:**

```bash
mkdir -p "<QC_BASE>/Manual" \
         "<QC_BASE>/Transcriptions" \
         "<QC_BASE>/Presets/factory" \
         "<QC_BASE>/Presets/notes" \
         "<QC_BASE>/Backups" \
         "<QC_BASE>/Band/<band-name>"
```

---

## Agents

### A1 — QC-Manual
**Role:** Hardware reference — block parameters, signal chain, firmware behaviour, I/O, plugins.

**Files to read:**
- `QC_BASE/Manual/` → any `.html` or `.pdf` file found
- Any `.md` file the user placed in `QC_BASE/Manual/`

**Reading method:**
- `.html` / `.md` / `.json` → `Read` tool
- `.pdf` → `Read` tool (paginated if large)
- `.docx` → `Bash: textutil -convert txt -stdout "<path>"` (macOS) or `python3 -m docx2txt <path>` (Linux/Windows)

**Dispatch prompt:**
```
You are an expert on the Neural DSP Quad Cortex hardware manual.
Read [relevant files] and answer: [QUESTION]
Return: exact block names, parameter values, firmware behaviour.
No prose. Raw facts.
```

---

### A2 — QC-Transcriptions
**Role:** Practical techniques and workflows from educational YouTube video transcriptions.

**Files to read:** all files in `QC_BASE/Transcriptions/` matching `YT_*.docx` or `YT_*.txt`

**Selection by theme:**
| Need | Priority files |
|---|---|
| Scenes / stomps | files mentioning "scenes", "hybrid mode" |
| Live / gigging | files mentioning "live", "covers band" |
| John Mayer tone | files mentioning "mayer", "two rock" |
| Routing / lanes | files mentioning "lanes", "routing" |
| General preset | files mentioning "tweak", "EQ" |
| Heavy / rock | files mentioning "high gain", "metal" |
| Mistakes / Fundamentals | `QC_16_common_mistakes_avoid.md` (too many FX, cab, gain staging, cuts, volume) |

**Dispatch prompt:**
```
You are a QC technique specialist using YouTube video transcriptions.
Read [selected files] via textutil and extract what answers: [QUESTION]
Return: actionable tips, mentioned parameters, source file name.
Concise. Bullet points.
```

---

### A3 — QC-Presets
**Role:** Preset library — factory, shared, personal notes.

**Files to read:**
- `QC_BASE/Presets/factory/` → any `.json` or `.csv` file
- `QC_BASE/Presets/notes/` → any `.md` file
- Any `.xlsx` or `.docx` file found in `QC_BASE/Presets/`

**Dispatch prompt:**
```
You are the Neural DSP QC preset librarian.
Read [files above] and find presets relevant to: [TONE_TARGET / STYLE]
Return: preset names, key blocks, tonal character. Ranked by relevance.
```

---

### A4 — QC-Band (optional)
**Role:** Band/project preset specialist — current state, setlist needs, session history.

**Files to read:**
- `QC_BASE/Band/<band-name>/presets.md`
- `QC_BASE/Band/<band-name>/LOG.md`

**Context to inject:**
- Band name, style, context (live/studio), role in band (sole guitarist? dual?)

**Dispatch prompt:**
```
You are the [BAND_NAME] preset specialist.
Read [band files] and answer: [QUESTION]
Context: [STYLE], [CONTEXT], [ROLE].
Return: current preset state, what's missing, setlist coherence.
```

---

### A5 — QC-Builder *(requires quad-cortex MCP)*
**Role:** Builds and modifies presets on the physical device via MCP.

**Available tools:** MCP `quad-cortex` — `connect`, `find_devices`, `build_preset`, `set_parameter`, `set_parameter_scenes`, `set_block_bypass`, `assign_stomp`, `switch_scene`, `cpu_load`, `save_preset_as`, `get_current_preset`, `list_empty_slots`, `recall_preset`, etc.

**Safety rules (always enforce):**
1. `connect()` first — verify device is reachable.
2. **Never build over a named preset.** If the current slot has a name → `list_empty_slots` → `recall_preset` to an empty slot. If slot shows "Unsaved" → use it.
3. After build: always `get_current_preset` + `cpu_load` (target < 85%).
4. Delete blocks, don't bypass, to free CPU.
5. `save_preset_as` → verify with `current_preset_position`.

**Scenes (A–H):**
- Use `set_block_bypass(scenes=[...])` for drives/amps per scene.
- Use `set_parameter_scenes` to vary amp gain/EQ per scene.
- Label scenes with `set_preset_meta`.
- Scenes on delays: scene the **Mix** parameter, not the bypass.

**Dispatch prompt:**
```
You are the QC Builder. Build [PRESET_SPEC] on the physical device.
Research findings: [OUTPUT FROM A1/A2/A3]
Enforce slot safety rules. Check CPU. Save.
Return: slot used, blocks built, CPU %, save confirmation.
```

---

### A6 — QC-Doc
**Role:** Documents session changes.

**Files to read/write:**
- `QC_BASE/LOG.md` → append dated entry
- `QC_BASE/Band/<band-name>/LOG.md` → if band preset changed
- `QC_BASE/Band/<band-name>/presets.md` → update if preset list changed

**Entry format for LOG.md:**
```markdown
## [YYYY-MM-DD] — [Session title]

**Preset(s):** [name(s)]
**Slot:** [position]
**Blocks:** [key blocks used]
**Scenes:** [A=x, B=y, ...]
**CPU:** [%]
**Notes:** [anything relevant]
```

**Dispatch prompt:**
```
You are the QC documentalist.
Session [DATE] — Summary: [OUTPUT FROM A5]
1. Append to LOG.md: preset(s) created/modified, slot, CPU, scenes, notes.
2. If band preset: update Band/<band>/presets.md.
Confirm both files updated.
```

---

## Workflow — Decision Tree

```
Request received
      │
      ├─ Band/project context? → dispatch A4 in parallel with the rest
      │
      ├─ Tone / technique / parameter question?
      │   ├─ Hardware parameter → A1 (Manual)
      │   ├─ Practical technique → A2 (Transcriptions) [select by theme]
      │   ├─ Both → A1 + A2 in parallel
      │   └─ Existing preset as base → A3 (Presets)
      │
      ├─ Build / modify preset?
      │   ├─ MCP available? → synthesise A1/A2/A3/A4 → dispatch A5 (Builder)
      │   └─ No MCP? → return a build plan (block list, parameters, scenes)
      │                 so the user can build manually
      │
      └─ Always last, if something changed → A6 (Doc)
```

**Golden rule:** A1 + A2 always in parallel. A5 waits for their outputs. A6 always after A5.

**No MCP fallback:** if the user doesn't have the MCP server, A5 produces a **written build plan** instead:
```
BUILD PLAN — [Preset Name]
Chain: [block 1] → [block 2] → ...
Key parameters: [block]: [param] = [value]
Scenes: A=[description], B=[description]
```

---

## Output Format / Format de sortie

```
## Summary / Synthèse
[What was done / decided]

## Preset(s)
[Slot, blocks, scenes, CPU — if build]
[OR: build plan if no MCP]

## Open points / Points ouverts
[Open questions, adjustments needed]

## Doc
[LOG.md ✓ / Band presets ✓ — or: nothing to document]
```

No essays. Facts + actions. Research-only → just the findings.
Pas de prose inutile. Faits + actions. Recherche seule → juste les findings.
