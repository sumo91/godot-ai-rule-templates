# CLAUDE.md

## Godot Development Policy

When working on a Godot project, always choose the simplest tool that can complete the task safely, deterministically, and with clear feedback.

### Tool Selection

- Prefer direct text edits for GDScript, JSON, config files, documentation, and safe text-editable `.tscn` / `.tres` changes.
- Do not launch Godot when the task is fully text-based and can be reviewed clearly in diff form.
- Use Godot MCP-style tools only when they provide a clear advantage, such as structured inspection, editor launch, debug output, or reliable automation.
- Do not assume every MCP scene or node editing tool is safe or appropriate. Verify the specific tool behavior before relying on it.
- Use the standard Godot editor executable for interactive editor work, especially inspector changes, drag-and-drop scene wiring, import workflows, animation setup, tile editing, layout changes, and visual validation.
- Use the Godot console executable for command-line workflows such as version checks, diagnostics, script execution, validation, CI tasks, and terminal-visible logs.

### Coding Rules

- Use typed GDScript whenever practical.
- Keep functions focused and scripts narrow in responsibility.
- Prefer composition by default, but use inheritance when it is the clearest fit for Godot’s scene or class model.
- Prefer `@onready`, exported references, or explicit dependency setup over fragile deep node lookups.
- Use signals for decoupling and event-style communication. Keep signal names clear and pass only the data listeners need.
- Use `preload()` for resources that are always needed and `load()` for resources that are dynamic or optional.
- Handle missing resources and invalid content data with explicit errors or safe fallbacks.
- Keep naming consistent:
  - files, variables, and functions use `snake_case`
  - classes use `PascalCase`
  - constants use `ALL_CAPS_SNAKE_CASE`
  - signals use `snake_case`

### Scene And Architecture Rules

- Keep scene trees as shallow as practical.
- Keep reusable logic in scripts and reusable composition in scenes.
- Use scene inheritance only when the inherited structure is genuinely stable.
- Avoid hiding core gameplay logic inside inspector-only configuration when a text-editable script or data file would be clearer.
- Prefer data-driven content definitions for classes, items, enemies, regions, and progression systems when the project benefits from iteration speed and reviewable diffs.

### Human Handoff Rules

When a task becomes editor-heavy, visual, or inspector-dependent:

- stop at a clean checkpoint
- record the exact files already prepared
- record the exact editor action required
- record the expected success criteria
- record what the next session should verify after the editor step

### Agent Behavior Rules

- Do not use the editor for changes that are easier to make and review as text.
- Do not use MCP automation blindly; verify that the specific tool and operation are appropriate for the task.
- Prefer the console executable for scripted or diagnostic workflows.
- Prefer the standard editor executable for interactive or visual workflows.
- When a task crosses from text-safe work into editor-owned work, stop and hand off cleanly instead of forcing automation.
