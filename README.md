# Image Generation

A Claude Code plugin (also installable as a standalone Agent Skill) that teaches your agent how to prompt modern text-to-image models well — Imagen, Gemini Image, GPT Image, DALL·E, Stable Diffusion, Flux, Ideogram, Leonardo, Midjourney, and others.

Distilled from the public prompting guides published by major image-model providers, plus practical patterns that hold up across vendors and across versions.

## What this skill teaches

- The six-element prompt skeleton (subject, action, setting, composition, lighting, style)
- Vendor-fluent vocabulary for photography, illustration, materials, and composition
- Mode-specific patterns for photoreal scenes, illustrations, logos, in-image text, product shots, infographics, UI mockups, and minimalist layouts
- The preserve-list pattern for iterative editing without drift
- A debugging checklist for when output is wrong
- Anti-patterns to avoid (keyword soup, negation, over-stuffed prompts, named-font chasing)
- The API parameters that actually matter (aspect ratio, resolution, quality tier, `n`, reference fidelity, seed)

## Install

### Option A — As a plugin (Claude Code)

Once accepted into Anthropic's plugin marketplace, install with:

```bash
/plugin install image-generation@claude-plugins-official
```

Until then, install directly from this repo by cloning into your Claude Code plugins directory:

```bash
git clone https://github.com/ahmedraza28/image-generation-skill ~/.claude/plugins/image-generation
```

Restart Claude Code (or start a new session) and the skill activates automatically when its triggers match.

### Option B — As a standalone skill

Drop just the `skills/image-generation/` directory into your skills folder:

```bash
# User-level (available in every project)
cp -r skills/image-generation ~/.claude/skills/

# Or project-level
cp -r skills/image-generation .claude/skills/
```

### Option C — Other agent runtimes

The skill is plain Markdown with YAML frontmatter conforming to the [Agent Skills specification](https://agentskills.io/specification). It works in any runtime that supports that spec — including Codex, Gemini CLI, and Copilot CLI — as long as you place the `image-generation/` directory in that runtime's skills location.

## Repository layout

```
image-generation-skill/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── skills/
│   └── image-generation/
│       └── SKILL.md             # The skill itself
├── README.md
└── LICENSE
```

## Use

Once installed, the skill loads automatically when you ask Claude (or your agent) to generate, prompt for, or debug an image. You don't need to invoke it explicitly.

You can also read [`skills/image-generation/SKILL.md`](skills/image-generation/SKILL.md) directly as a standalone prompting reference — it's structured to be useful to humans, not only to agents.

## Contributing

Issues and PRs are welcome. Especially:

- Vendor-specific quirks worth calling out
- Failure modes the debugging checklist doesn't cover
- New mode templates (e.g., album covers, book jackets, scientific figures)
- Corrections — image-model behavior shifts version to version

Please keep contributions model-agnostic where possible. Anything vendor-specific should be flagged as such.

## License

MIT — see [LICENSE](LICENSE).
