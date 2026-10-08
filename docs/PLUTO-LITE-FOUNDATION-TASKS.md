# Personal Effects — Pluto Studio Lite foundation task cards
**Authority:** [Roadmap v1.0](PERSONAL-EFFECTS-ROADMAP.md). These are tool-neutral specifications, **not** an assumed Pluto Lite YAML schema. Map to verified Lite task registry after inspecting Studio's implementation.

## Common task contract
- One task per branch/worktree, one at a time; base from approved SHA.
- Before work: inspect `git status`, relevant files, existing tests and constraints.
- No unrelated cleanup, gameplay expansion, external dependencies, deployment, push or merge without owner approval.
- Give evidence: before/after behaviour, exact commands and results, touched files, automated/browser/mobile/manual distinction, risks, revisions, and token/cost telemetry (or **unavailable**).
- A failed task remains visible for diagnosis; never rewrite history or report a test passed without running it.
- Keep Night Parcel Office and other repositories untouched.

### PE-001 — Read-only baseline and mechanics audit
**Dependencies:** none. **Mode:** read-only. **Complexity:** S. **Human review:** yes.  
**Deliverable:** `docs/PROTOTYPE-BASELINE.md` with file map, case inventory, exact rules, interaction controls (rotate/undo/seal/touch), narrative/content, persistence, test commands, mobile issues, and divergences from roadmap assumptions. 
**Accept:** reference filenames/functions; list actual cases versus proposed; identify test/build/deploy commands without inventing them; capture git SHA and state; no runtime source edits; unknowns labelled.
**Verify:** static inspection plus run existing safe tests if present; disclose any that could not run.

### PE-002 — Characterisation tests
**Depends:** PE-001 accepted. **Complexity:** M. **Human review:** QA.  
**Deliverable:** tests covering original case definitions, legality/sealing, invalid/valid placements, rotation, weight and any existing special rule actually found in audit. 
**Accept:** tests lock current behaviour, including quirks flagged in baseline; no requirement to fix them; do not update implementation simply to make tests pass.
**Verify:** run tests twice and report baseline, command, cases exercised, pass/fail; document any browser-only coverage gaps.

### PE-003 — Minimal rules extraction and structured case definitions
**Depends:** PE-002 accepted. **Complexity:** M. **Human review:** QA plus scope review.
**Deliverable:** authoritative pure rules API and case data representation with minimal UI integration and migration.
**Accept:** original outcomes equivalent for existing cases, including edge cases; no two competing evaluators; no unnecessary framework or build migration; preserve direct browser play unless separately approved; stable IDs and explicit errors for malformed content.
**Verify:** old-vs-new fixture equivalence and full tests; browser smoke test for seal/rotate/undo and two screen sizes.

### PE-004 — Deterministic validator/solver
**Depends:** PE-003 accepted. **Complexity:** L; split into schema validation / solvability / solution-count reporting if needed. **Human review:** mandatory.
**Deliverable:** read-only validation command and focused fixture tests, reusing game evaluator semantics.
**Accept:** every existing case checked; report solutions or bounded count with honesty about truncation; reject unsatisfiable and malformed fixtures; indicate intended optional sentimental alternatives where applicable; greedy-triviality diagnostic is advisory, not a rejection criterion; deterministic output for identical input.
**Verify:** positive and intentionally broken cases, repeated deterministic run, performance envelope recorded; do not assume a solved case is fun.

### PE-005 — Mobile audit and targeted interaction fixes
**Depends:** PE-001, and preferably PE-003/004 accepted. **Complexity:** M. **Human review:** indispensable for feel.
**Deliverable:** before/after issue log, minimal fixes for tap/drag/rotate/undo/seal if defects reproduced.
**Accept:** play a full existing case using tap and drag where supported; no accidental scrolling while manipulating items; no clipped controls; visible placement feedback; functional touch targets; avoid regressions for desktop mouse/keyboard; preserve reduced-motion setting if already present.
**Verify:** Playwright/emulated small and large viewports plus **two distinct physical devices** or mark that gate pending; record browser/OS, screenshots and human findings. Automation never counts as real-device testing.

## Trial disposition after PE-005
Create one owner-reviewed outcome record: tasks accepted/rejected, revisions, human minutes/task, measured cost/tokens, defects, setup burden, comparison limitations, and decision: CONTINUE LITE / RETRY LITE / SWITCH TO CODEX. PE-006 is blocked until this decision is recorded.
