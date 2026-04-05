# Godot AI Rule Templates

Reusable AI rule templates for Godot game development across Claude, Cursor, and other coding assistants.

Use this repo when you want to start a new Godot project and immediately give your AI tooling a sane, reusable working agreement.

[中文说明](./README.zh-CN.md)

## What This Repo Gives You

- copy-ready rule files for new Godot projects
- clearer boundaries between text-safe AI work and editor-heavy human work
- cross-tool guidance that stays portable across machines and assistants
- a small starting point that you can customize per project

## Included Files

- `CLAUDE.md`: stronger agent-policy style guidance for assistants that ingest repository instruction files directly
- `AGENTS.md`: collaboration-oriented guidance for multi-session human + AI work, including handoff expectations
- `.cursorrules`: shorter Cursor-style rules for lightweight editor enforcement
- `CLAUDE.zh-CN.md`: Chinese companion reference for `CLAUDE.md`
- `AGENTS.zh-CN.md`: Chinese companion reference for `AGENTS.md`
- `.cursorrules.zh-CN`: Chinese companion reference for `.cursorrules`

## Bilingual File Guidance

- In most projects, keep the English rule files as the primary files that tools actually read.
- Use the Chinese companion files as human-readable references when reviewing, customizing, or explaining the rules.
- Do not assume every AI tool will automatically discover or prioritize the Chinese companion files.
- If you modify a rule, update the matching English and Chinese files together.

## Pick The File You Need

| File | Use it when... |
| --- | --- |
| `CLAUDE.md` | your coding assistant reads repository markdown as direct operating policy |
| `AGENTS.md` | you want stronger collaboration rules, handoff notes, and session discipline |
| `.cursorrules` | your editor expects a compact rules file instead of a long markdown document |

If a project uses multiple tools, it is fine to keep more than one file in the repo as long as the guidance stays aligned.

## Fastest Setup

1. Open your new Godot project root.
2. Copy in the file or files you want to use:
   - `CLAUDE.md`
   - `AGENTS.md`
   - `.cursorrules`
3. Keep them at the repository root so your tools can discover them.
4. Adjust the project-specific items listed below.
5. Commit the rules early so every future AI session starts with the same baseline.

## Recommended Default

For a solo Godot project that may use more than one AI tool, a practical default is:

- keep `CLAUDE.md` for strong agent instructions
- keep `.cursorrules` for editor-level enforcement
- add `AGENTS.md` only if you want more explicit handoff and session protocol

## Customize Before First Use

Review and adjust these items before treating the templates as project policy:

- pinned Godot version, if the project standardizes on one
- folder conventions such as `scenes/`, `scripts/`, `data/`, `addons/`, or `tests/`
- any team-specific testing, commit, branching, or review expectations
- whether the project wants stronger guidance around scene inheritance, data-driven content, or tool usage
- any rules about when humans must take over editor-heavy tasks

## Design Principles

These templates are intentionally cross-tool and cross-machine:

- they avoid machine-specific paths
- they avoid project-specific assumptions
- they prioritize deterministic, diff-friendly work
- they make the handoff between text edits and editor-driven work explicit
- they focus on Godot tool choice, coding habits, and human + AI coordination

## Before You Reuse Or Publish Them Elsewhere

Before copying these templates into another repository or sharing them with a team:

- confirm the wording matches the tools your team actually uses
- remove instructions that would conflict with your real workflow
- keep duplicated guidance synchronized across `CLAUDE.md`, `AGENTS.md`, and `.cursorrules`
- add a project README note telling contributors which rule files are authoritative
