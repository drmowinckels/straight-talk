# straight-talk

Claude skills for capturing specific writing voices and styles. These skills are **content-agnostic**—they teach Claude how to write in a particular voice, not what to write about.

## What These Skills Do

These skills distill the voice, style, and structural patterns from exemplary writing to make technically complex or professional content more approachable and human. They capture **how** to write, not **what** to write.

Think of them as voice cloning for writing style: the patterns, rhythms, and techniques that make writing feel direct, warm, honest, and intelligent—without dictating subject matter.

**See it in action:** Check out [test-skill-usage.md](test-skill-usage.md) for before/after examples showing how both skills transform generic writing into clear, human communication.

## Skills in This Repo

### codex-voice
**Voice & style for long-form technical writing**

Captures the writing patterns from The Composable Codex: how to make technically complex material approachable while respecting the reader's intelligence. This is about sentence structure, opening moves, transition patterns, and voice markers—not about data systems or composability.

Use when writing about any technical topic where you want to:
- Make complexity accessible without dumbing it down
- Write with warmth and personality, not corporate blandness
- Trust your reader to keep up while still being clear

**Location:** `codex-voice/`  
**Packaged file:** `codex-voice.skill`

### brand-voice
**Voice & style for brand and corporate communications**

Combines the best of three worlds: Aesop's respectful formality and word discipline, Intuit's conversational clarity, and The Composable Codex's honest directness. This is about word choice, tone, and philosophy—not about skincare or financial software.

Use when writing any brand or customer-facing content where you want to:
- Sound human, not like a marketing robot
- Be clear and precise without being cold
- Show respect for your reader's time and intelligence
- Be honest about tradeoffs instead of claiming perfection

**Location:** `brand-voice/`  
**Packaged file:** `brand-voice.skill`

## Using the Skills

To use a skill with Claude:
1. Download the `.skill` file
2. Import it into your Claude workspace
3. The skill will guide Claude's writing style for your content

**Important:** These skills teach Claude *how* to write (voice, structure, patterns), not *what* to write about. You bring the subject matter and expertise; the skill brings the voice and style.

## Development

### Creating New Skills

Initialize a new skill:

```bash
python scripts/init_skill.py <skill-name> --path .
```

### Packaging Skills

Package a skill for distribution:

```bash
python scripts/package_skill.py <skill-folder-name>
```

The script validates the skill structure and creates a `.skill` file (zip archive).

### Skill Structure

```
skill-name/
├── SKILL.md (required)
│   ├── YAML frontmatter with name and description
│   └── Markdown instructions
└── references/ (optional)
    └── Additional documentation loaded as needed
```

## Repository Structure

```
straight-talk/
├── scripts/                    # Utility scripts
│   ├── init_skill.py          # Initialize new skill
│   └── package_skill.py       # Package skill for distribution
├── codex-voice/               # Composable Codex writing style
│   ├── SKILL.md              # Main skill file
│   └── references/
│       └── patterns.md       # Sentence patterns to emulate
├── brand-voice/               # Brand voice writing skill
│   ├── SKILL.md              # Main skill file
│   └── references/
│       └── word-lists.md     # Vocabulary guidance
├── codex-voice.skill         # Packaged skill files
└── brand-voice.skill
```
