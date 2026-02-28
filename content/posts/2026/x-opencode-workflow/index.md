+++
title = 'My OpenCode Workflow'
date = 2026-06-15T18:33:11+02:00
draft = true
version = 1
author = 'Colin'
categories = ['OpenCode', 'Workflow', 'TDD', 'Quality Gate', 'Conventional Commits']
+++

# Prerequisites:
your project must have a thoroughly executed set of lining rules, arch rules, and testing concept.

# make a list of system requirements & NFRs

# let the agent write structured tasks based on the requirements (Important: verification step)


# Execution Contract:
One-time kickoff prompt (copy/paste)
Execute TASK-23 through TASK-30 autonomously in order.
For each task:
1) implement via TDD,
2) run full frontend quality gate (test, lint, build),
3) stage all changes,
4) commit immediately using Conventional Commit style (feat|fix|chore: ...),
5) continue with next task without waiting for me.
   Do not stop between tasks unless truly blocked. If blocked, explain the blocker and your recommended default.
   At the end, provide a compact report with:
- tasks completed
- commit hashes + messages
- any deviations/assumptions
- final quality gate status.



# Example Task Structure:
```markdown
# TASK-25: Move Camera Tool (Drag + Arrow Keys)

**Status:** pending  
**Priority:** high  
**Phase:** 10 — Editor Tools V2  
**Dependencies:** TASK-10, TASK-24  
**Estimated effort:** medium  

---

## Description

Add a dedicated `Move Camera` tool to the modeler toolbox. When active, users can move the camera by drag-and-drop (left mouse drag) and by arrow keys. This gives an explicit panning tool in addition to existing middle-mouse/space pan.

---

## Requirements Addressed

- **V2-ED-01** Dedicated move-camera tool in toolbox
- **V2-ED-02** Camera movement via drag and arrow keys

---

## Architecture Decisions

- Implement `MoveCameraTool` in `pages/modeler/tools/`
- Tool behavior:
  - Left mouse down starts camera drag pan
  - Mouse move updates camera offset
  - Mouse up ends drag
  - Arrow keys pan camera by fixed world-space step
- Reuse existing camera model from TASK-09 (`camera.ts`) and avoid camera math duplication
- `EditorCanvasComponent` should expose a minimal camera-control API for tool-driven pan/translate
- Register shortcut for the tool (via TASK-24 registry), and show it in toolbox hints

---

## Files to Create

| File | Path |
|------|------|
| `move-camera.tool.ts` | `frontend/src/app/pages/modeler/tools/` |
| `move-camera.tool.spec.ts` | `frontend/src/app/pages/modeler/tools/` |

## Files to Modify

| File | Change |
|------|--------|
| `frontend/src/app/pages/modeler/state/tool.service.ts` | Support registration/activation of move-camera tool |
| `frontend/src/app/pages/modeler/modeler.page.ts` | Register the new tool and its shortcut |
| `frontend/src/app/pages/modeler/ui/toolbox/toolbox.component.ts` | Render move-camera tool button + hint |
| `frontend/src/app/pages/modeler/ui/editor-canvas/editor-canvas.component.ts` | Expose camera pan API used by active tool |

---

## Acceptance Criteria

- [ ] `MoveCameraTool` exists and implements `Tool`
- [ ] Tool is visible in toolbox with icon, name, and shortcut hint
- [ ] Left-drag pans camera while the move-camera tool is active
- [ ] Arrow keys pan camera while the move-camera tool is active
- [ ] Existing middle-mouse/space panning remains functional
- [ ] Tool lifecycle (`activate`/`deactivate`) resets drag state correctly
- [ ] Pan interactions are ignored in simulation mode
- [ ] `move-camera.tool.spec.ts` covers drag and key-pan behavior

---

## TDD Hints

1. Drive tool behavior from tests first: drag start, drag move, drag end, arrow movement
2. Mock camera control surface rather than coupling tests to canvas internals
3. Add toolbox rendering test for the new tool registration

---

## Verification

```bash
# From frontend/
bun run test -- --watch=false --include **/move-camera.tool.spec.ts
bun run test -- --watch=false --include **/toolbox.component.spec.ts
bun run build
```


```