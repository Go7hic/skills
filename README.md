# Agent Skills

- **GitHub:** [github.com/Go7hic/skills](https://github.com/Go7hic/skills)
- **About:** **Agent Skills** for **Cursor**, **Codex**, **Claude Code**, and similar environments (`SKILL.md` plus optional `references/`). When installing with the **[skills CLI](https://www.npmjs.com/package/skills)**, prefer the two entry points below—`design-prompts-library` and `favicon-so` (see [Install](#install-via-skills-cli)); the other `design-prompt-*` folders are per-style Design Prompts implementations referenced from the library docs.

## Repository layout

```
skills/
├── design-prompts-library/   # Index: choosing a Design Prompts style
├── design-prompt-*/          # Individual landing-page / UI aesthetics (see table)
└── favicon-so/               # favicon.so API reference
```

## Install via [skills CLI](https://skills.sh/docs/cli)

Source: [Go7hic/skills](https://github.com/Go7hic/skills) (`git@github.com:Go7hic/skills.git`). CLI docs: [skills.sh](https://skills.sh/docs/cli); package: [npm: `skills`](https://www.npmjs.com/package/skills).

This repo has **many directories under `skills/` that contain `SKILL.md`**. Running `npx skills add Go7hic/skills` **without** narrowing the set usually pulls **multiple** skills from the scan (including every `design-prompt-*`), which is heavy. **Prefer explicitly selecting the two public entry points:**

| Entry | Purpose |
|------|---------|
| `design-prompts-library` | Design Prompts style picker / overview; concrete styles live in `design-prompt-*` |
| `favicon-so` | [favicon.so](https://favicon.so) API reference |

**Install one:**

```bash
npx skills add Go7hic/skills --skill design-prompts-library
# or
npx skills add Go7hic/skills --skill favicon-so
```

**Install both:**

```bash
npx skills add Go7hic/skills --skill design-prompts-library --skill favicon-so
```

**List what the CLI discovers (no install):**

```bash
npx skills add Go7hic/skills --list
```

**Install from a subdirectory URL (single skill):**

```bash
npx skills add https://github.com/Go7hic/skills/tree/main/skills/design-prompts-library
npx skills add https://github.com/Go7hic/skills/tree/main/skills/favicon-so
```

Other useful flags: `-g` (user-wide install), `-a cursor` / `-a codex` to target agents—see the [npm readme](https://www.npmjs.com/package/skills).

**Telemetry:** enabled by default (anonymous). Opt out: `export DISABLE_TELEMETRY=1` or `DO_NOT_TRACK`.

## Manual install (or other tools)

- **Cursor:** Copy or symlink the skill folders into your Cursor skills path (e.g. `~/.cursor/skills/`) so the orchestrator can see `SKILL.md`.
- **Codex:** Follow upstream docs for `$CODEX_HOME/skills` (e.g. [Codex skill installer](https://github.com/openai/codex) from a path or repo).
- **Claude Code:** Point the platform’s skill tooling/config at the matching subdirectory in this repo.

Exact paths depend on your client’s documentation.

## Skill index

### Design Prompts

| Skill ID | Summary |
|----------|---------|
| `design-prompts-library` | Help users pick a Design Prompts style or browse aesthetics |
| `design-prompt-academia` | Academia landing / UI |
| `design-prompt-art-deco` | Art Deco |
| `design-prompt-bauhaus` | Bauhaus |
| `design-prompt-bold-typography` | Bold Typography |
| `design-prompt-botanical` | Botanical / Organic Serif |
| `design-prompt-claymorphism` | Clay / Claymorphism |
| `design-prompt-cyberpunk` | Cyberpunk |
| `design-prompt-enterprise` | Corporate Trust |
| `design-prompt-flat-design` | Flat Design |
| `design-prompt-industrial` | Industrial |
| `design-prompt-kinetic` | Kinetic |
| `design-prompt-luxury` | Luxury |
| `design-prompt-material-design` | Material |
| `design-prompt-maximalism` | Maximalism |
| `design-prompt-minimal-dark` | Simple Dark |
| `design-prompt-modern-dark` | Modern Dark |
| `design-prompt-monochrome` | Monochrome |
| `design-prompt-neo-brutalism` | Neo-brutalism |
| `design-prompt-neumorphism` | Neumorphism |
| `design-prompt-newsprint` | Newsprint |
| `design-prompt-organic` | Organic / Natural |
| `design-prompt-playful-geometric` | Playful Geometric |
| `design-prompt-professional` | Business Style |
| `design-prompt-retro` | Retro |
| `design-prompt-saas` | Tech Style / SaaS |
| `design-prompt-sketch` | Hand-Drawn / Sketch |
| `design-prompt-swiss-minimalist` | Swiss |
| `design-prompt-terminal` | Terminal CLI |
| `design-prompt-vaporwave` | Vaporwave |
| `design-prompt-web3` | Crypto / Web3 |

Details, palettes, and constraints: each skill’s `SKILL.md` and `references/style.md` when present.

### Other

| Skill ID | Summary |
|----------|---------|
| `favicon-so` | [favicon.so](https://favicon.so) fetch + image-to-favicon-package APIs—routes, debugging, new endpoints |

## Conventions

- Each skill root **must** include **`SKILL.md`** with YAML frontmatter: `name`, `description` (sometimes `license` / `metadata`).
- Optional **`references/`** for long-form specs or style notes, linked from `SKILL.md`.

## License

MIT
