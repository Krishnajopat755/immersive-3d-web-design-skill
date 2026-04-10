# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## What this repo is

This repository is a **Claude Code skill** implemented entirely as Markdown.

The "runtime" artifact is `SKILL.md`: Claude Code reads the YAML frontmatter (metadata + allowed tools) and the instructions that follow. No build step. No dependencies. Just Markdown.

`README.md` is for humans: installation, usage, and a compact overview of what the skill covers.

## Key files (and how they relate)

- `SKILL.md`
  - The actual skill definition.
  - Starts with YAML frontmatter (`---` … `---`) containing `name`, `version`, `description`, and `allowed-tools`.
  - After the frontmatter: the full skill instructions — philosophy, color theory, code patterns, case studies, checklist, anti-patterns, and starter scaffold.
  - **This is the source of truth.** When changing behavior or adding patterns, edit here first.
- `README.md`
  - Installation and usage instructions.
  - Contains a summary of what's covered (tables, pattern list, case studies, tool selection).
  - Should stay consistent with `SKILL.md` content — if you add a new pattern to the skill, add a row to the README table.

## Common commands

### Install the skill into Claude Code

Recommended (clone directly into Claude Code skills directory):

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/YOUR_USERNAME/immersive-3d-web-design.git ~/.claude/skills/immersive-3d-web-design
```

Manual install/update:

```bash
mkdir -p ~/.claude/skills/immersive-3d-web-design
cp SKILL.md ~/.claude/skills/immersive-3d-web-design/
```

### How to "run" it (Claude Code)

```
/immersive-3d-web-design

[describe what you want to build]
```

## Making changes safely

### Versioning (keep in sync)

- `SKILL.md` has a `version:` field in its YAML frontmatter.
- `README.md` has a "Version History" section.

If you bump the version, update both.

### Editing `SKILL.md`

- Preserve valid YAML frontmatter. The `description:` field uses a `|` block scalar — preserve the indentation.
- Keep the section structure stable: Philosophy → Color → 3D Construction → Particles → Shaders → Scroll → Typography → Tool Selection → Case Studies → Checklist → Anti-Patterns → Scaffold.
- GLSL shader code blocks must stay as ` ```glsl ` fenced blocks — Claude Code parses them correctly.
- If adding a new case study, add both the section in `SKILL.md` and a row in the case studies table in `README.md`.

### Documenting non-obvious changes

If you edit a shader or interaction pattern to fix a specific failure mode (e.g., a shader that broke on certain GPU drivers, or a scroll pattern that conflicted with Lenis), add a short note to `README.md`'s version history explaining what was fixed and why.

### Scope of this skill

This skill is intentionally focused on **browser-based immersive web** — Three.js, WebGL, GSAP, Lenis, shader post-processing. It does not cover:

- Native game engines (Unity, Unreal)
- React Native or mobile-native
- Server-side rendering architecture
- Design tools (Figma, Spline)

If a request is outside this scope, the skill should acknowledge this and suggest the right tool.
