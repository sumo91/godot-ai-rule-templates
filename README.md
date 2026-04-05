# Godot AI Rule Templates

Reusable rule templates for AI-assisted Godot development across multiple tools and machines.

The goal is simple: copy the relevant file into a new Godot project, make a few project-specific edits, and start collaborating with AI immediately without rethinking the same workflow rules each time.

## Included Files

- `CLAUDE.md`: stronger agent-policy style guidance for assistants that ingest repository instruction files directly
- `AGENTS.md`: collaboration-oriented guidance for multi-session human + AI work, including handoff expectations
- `.cursorrules`: shorter Cursor-style rules for lightweight editor enforcement

## Which File Should I Use?

- Use `CLAUDE.md` when the coding assistant treats repository markdown as high-priority operating instructions.
- Use `AGENTS.md` when you want stronger session discipline, human handoff notes, and clearer boundaries between AI-safe work and editor-heavy work.
- Use `.cursorrules` when the editor expects a compact rules file instead of a long-form instruction document.
- If a project uses multiple tools, it is fine to keep more than one of these files in the repo as long as they stay aligned.

## Quick Start For A New Godot Project

1. Open your new Godot project root.
2. Copy in the template file or files you want to use:
   - `CLAUDE.md`
   - `AGENTS.md`
   - `.cursorrules`
3. Keep them at the repository root so AI tools can discover them easily.
4. Make the small project-specific edits listed below.
5. Commit the rules early so every future AI session starts from the same working agreement.

## Recommended Customization Before First Use

Review and adjust these items before treating the templates as final project policy:

- pinned Godot version, if the project standardizes on one
- folder conventions such as `scenes/`, `scripts/`, `data/`, `addons/`, or `tests/`
- any team-specific testing, commit, branching, or review expectations
- whether the project wants stronger guidance around scene inheritance, data-driven content, or tool usage
- any rules about when humans must take over editor-heavy tasks

## Design Goals

These templates are intentionally cross-tool and cross-machine:

- they avoid machine-specific paths
- they avoid project-specific assumptions
- they prioritize deterministic, diff-friendly work
- they make the handoff between text edits and editor-driven work explicit
- they focus on Godot tool choice, coding habits, and human + AI coordination

## Publishing Notes

Before publishing these templates inside another repository or sharing them with a team:

- confirm the wording matches the tools your team actually uses
- remove instructions that would conflict with your real workflow
- keep duplicated guidance synchronized across `CLAUDE.md`, `AGENTS.md`, and `.cursorrules`
- add a project README note telling contributors which rule files are authoritative
