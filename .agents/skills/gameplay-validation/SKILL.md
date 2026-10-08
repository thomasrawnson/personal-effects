---
name: gameplay-validation
description: Validate Personal Effects rules, suitcase interactions, progression, mobile behaviour and regression safety with clear evidence.
---

# Personal Effects Gameplay Validation
Inspect the authoritative rules and current fixtures before editing or testing. Preserve established semantics unless a change is approved.

Check board bounds, item footprints and orientations, non-overlap, weight, placement constraints, required/optional item semantics, seal eligibility, undo, visual hints, intended case completion, and deterministic feedback. For each new rule test valid/invalid edge conditions and case content.

Prefer pure-rule tests plus independent browser smoke tests. Ensure UI errors and hints arise from the same evaluator as solver decisions. Validate save/campaign behaviour only once implemented. Never imply scripted tests prove that a case is enjoyable.

Report exact commands, fixture counts, pass/fail and baseline, browser viewports, mobile emulation, physical device checks (or pending), defects and remaining uncertainties. Do not silently weaken a test to obtain a pass.
