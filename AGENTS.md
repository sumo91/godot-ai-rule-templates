# AGENTS.md

## Purpose

This file defines the working agreement for Godot projects developed through human + AI collaboration across multiple sessions and multiple tools.

## Core Principle

Use the simplest tool that can complete the task safely, deterministically, and with clear feedback.

Prefer text-first, diff-friendly work whenever possible. Use the Godot editor when the task genuinely depends on editor state, inspector configuration, or visual validation.

## Tool Selection Policy

### Priority Order

1. Prefer direct text edits for GDScript, JSON, config files, documentation, and safe text-editable scene/resource files.
2. Use Godot MCP-style tools for structured inspection, editor launch, and automation only when the specific integration is reliable in the current environment.
3. Use the standard Godot editor executable for interactive editor work.
4. Use the Godot console executable for command-line diagnostics, validation, scripts, and terminal-visible output.

### Direct Text Edits

Use direct text edits for:

- scripts
- gameplay data
- docs
- project settings
- safe `.tscn` / `.tres` edits

Do not open Godot when the task is fully text-based and clearly reviewable in diff form.

### Standard Editor Usage

Use the standard Godot editor for:

- inspector changes
- drag-and-drop scene wiring
- import workflows
- animation setup
- tile or map editing
- anchor and layout adjustment
- visual validation

### Console Usage

Use the Godot console executable for:

- version checks
- CLI diagnostics
- script execution
- automated validation
- CI-friendly workflows
- terminal-visible logs and errors

### MCP Usage

Use Godot MCP-style tools for:

- editor launch
- project inspection
- debug output capture
- structured automation when verified stable

Do not assume all MCP scene or node editing tools are safe by default. Verify tool behavior before relying on it.

## Coding Rules

- Use typed GDScript whenever practical.
- Keep functions focused and scripts narrow in responsibility.
- Prefer composition by default, but use inheritance when it clearly matches Godot’s scene or class model.
- Prefer `@onready`, exported references, or explicit dependency setup over fragile deep node lookups.
- Use signals for decoupling and clear event-style communication.
- Use `preload()` for always-needed resources and `load()` for dynamic resources.
- Handle missing resources and invalid content data with explicit errors or safe fallbacks.
- Keep naming consistent:
  - files, variables, functions: `snake_case`
  - classes: `PascalCase`
  - constants: `ALL_CAPS_SNAKE_CASE`
  - signals: `snake_case`

## Collaboration Rules

### AI-first work

- GDScript
- JSON and content data
- docs
- architecture notes
- safe scene scaffolding in text
- deterministic refactors

### Human-first work

- inspector-heavy setup
- drag-and-drop scene wiring
- visual layout tuning
- animation timeline editing
- tile painting
- import troubleshooting
- feel-based validation

### Shared work

- architecture decisions
- scene boundaries
- gameplay direction
- testing and validation strategy
- release readiness

## Session Protocol

### Start of session

1. Read the project instructions.
2. Review the current focus and recent changes.
3. Choose the simplest suitable tool for the task.
4. Confirm whether the task is text-first or editor-dependent.

### End of session

Before ending the session:

1. Record what was completed.
2. Record the next focus.
3. Record any human editor action still needed.
4. Record blockers or environment limitations.
5. Commit coherent completed work when appropriate.

## Human Handoff Rules

When a task becomes editor-heavy, visual, or inspector-dependent, stop at a clean checkpoint and record:

- exact files prepared
- exact editor action needed
- expected success criteria
- what the next session should verify
