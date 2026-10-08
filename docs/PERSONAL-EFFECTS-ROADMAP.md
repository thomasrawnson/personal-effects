# Personal Effects — Roadmap v1.0
**Date:** 2026-10-08  
**Status:** Approved for *foundation trial only*; alpha/beta/release scope conditional  
**Owner:** Pluto Night Labs  
**Repository:** https://github.com/thomasrawnson/personal-effects

## READ FIRST — Decisions
1. Game is the primary product experiment; Studio Lite is a separate tooling experiment. Do not conclude the game failed because Lite failed, or vice versa. All tasks are tool-neutral and may transfer to direct Codex.
2. Start with a **10-case playable alpha**, not a 25-case commitment. Consider 15–18 strong cases for release; 25 is optional.
3. Initial target **60–120 seconds per case**; verify with new players. Hard cases may take longer when justified.
4. Core constraints: existing size/placement/weight rules, then at most **fragile**, **forbidden adjacency**, and **optional sentimental belongings** in the alpha. Do not conflate merely relabelled adjacency constraints with meaningful novelty.
5. A case must have a verified legal solution, explainable feedback, and a meaningful intentional tradeoff where sentimental items are offered. Prefer more than one legitimate resolution (compliant vs emotionally motivated), never one hidden arbitrary answer.
6. Regression baseline before refactor; extract a pure deterministic rules implementation and structured case data, then construct the solver/validator against that same implementation. If extraction needs a different order, document why; avoid duplicate logic.
7. Bring mobile drag, rotation and tap controls forward; a simulated mobile viewport does not replace physical-device testing.
8. Defer art overhaul, extensive narratives, saves beyond demonstrated need, large feature systems, procedural cases, timed modes, upgrades, and monetisation engineering until gameplay gate.
9. No autonomous commits, merges, pushes, deployments or broad refactors without explicit approval. Planning-file commits are not gameplay-task authorisation.
10. Initial execution authorisation covers **PE-001–PE-005 only**, one task at a time, followed by a Lite viability review. Gameplay expansion PE-006 onward needs separate approval.

## Game vision
A compact supernatural packing puzzle: prepare the personal belongings of the recently deceased for the afterlife under absurd official regulations. Spatial satisfaction, darkly comic office atmosphere, and the tension between what is compliant and what is kind. **Every suitcase tells a story.**

## Gameplay pillars
- Fast to understand and tactile on a phone, with clear rotate/undo/seal controls.
- Constraints interact in genuinely different ways; prevent brute force from becoming the only enjoyable strategy.
- Choices should be legible: rule-compliant arrangement versus preserving an optional meaningful object.
- Show why placement or sealing failed; provide an optional rule-violation hint.
- Hand-author quality content; the validator proves correctness, **not fun**.

## Known prototype context, pending PE-001 confirmation
Current GitHub `index.html` is a browser-first single-file prototype with a 6×6 suitcase grid and visual item pieces. Earlier prototype work featured the Postman, Magician, Gardener and a proposed Opera Singer case, rotate, undo and sealing. **This paragraph is historical context, not a verified full mechanic inventory.** PE-001 must inspect current code and record what actually runs and what test/build commands exist.

## Stage A — Foundation & Lite trial (approved to prepare)
| Task | Work | Exit |
|---|---|---|
| PE-001 | Read-only audit, mechanics inventory, architecture and tests map | Evidence-based gap report, no source edits |
| PE-002 | Characterisation/regression tests for existing cases and decisions | Baseline repeatable locally, failures documented |
| PE-003 | Minimal rules extraction + structured case definitions | Same observable results on current cases, tested |
| PE-004 | Deterministic solver/validator using authoritative rules | Existing cases solvable; broken cases rejected; solution counts reported |
| PE-005 | Mobile interaction audit and minimal fixes | Desktop, emulated and two real-device checks documented |

**Foundation exit:** Existing cases behave identically unless a change is explicitly accepted; all tests pass or known baseline failures are documented; Lite measured against predeclared trial thresholds; owner decides Lite vs direct Codex. PE-004 may reveal ambiguities rather than silently reinterpret them.

## Stage B — Ten-case alpha (not yet authorised)
| Task | Work |
|---|---|
| PE-006 | Rule-violation explanations and optional reveal/hint |
| PE-007 | Fragile restrictions + focused tests and two *candidate* cases |
| PE-008 | Forbidden-adjacency restrictions + focused tests and two candidate cases |
| PE-009 | Optional sentimental belongings and distinguishable compliant/compassionate resolutions |
| PE-010 | Human-selected, hand-balanced ten-case set; tune length, difficulty and emotional choices |

**GATE A:** At least five unfamiliar independent testers; observe first solve, median/p90 time per case, abandonments, rule misunderstanding, mobile problems, and unprompted desire to continue. Directional target: at least 4/5 voluntarily continue after three cases; do not mistake small-sample threshold for statistical proof. Record reasons, revise once, then continue / simplify / stop.

## Stage C — Retention and production beta (conditional)
| Task | Work |
|---|---|
| PE-011 | Small versioned save and campaign progression |
| PE-012 | Casebook and completion records |
| PE-013 | Minimal authored outcome text and limited consequence flags |
| PE-014 | Art-direction prototype and style guide for human approval |
| PE-015 | Tactile suitcase, readable objects and coherent interface polish |
| PE-016 | Optional sound/motion, reduced motion, accessibility and mobile refinement |
| PE-017 | Expand only if gates justify it, aiming at 15–18 strong cases |

**GATE B:** Unsponsored external beta: voluntary continuation, comprehensible rule explanations, meaningful tradeoffs, coherent visual treatment and stable mobile experience. Expand beyond 18 only when player demand and design capacity support it.

## Stage D — Release readiness (conditional)
| Task | Work |
|---|---|
| PE-018 | Regression and content validation, save migration, browser compatibility, accessibility, delivery and rollback documentation |

**GATE C:** Owner evaluates distribution and monetisation **after** product and audience evidence. Consider browser demo + premium full game, premium purchase, or alternatives; no payment integration, ads or storefront implementation until separate approval.

## Puzzle content acceptance rules
- Store immutable case ID, board dimensions, items, rotations/shapes, constraints, optionality and intended narrative outcomes in reviewed structured content.
- Solver enumerates or soundly counts distinct legal arrangements, reports count/cap and explains when counts are approximate.
- Test intentional malformed or impossible fixtures and reject invalid input with useful reasons.
- Check orientation, edge conditions, overlap, adjacency, weight, completion and optional choices against the exact game evaluator; never maintain competing rule definitions.
- Detect suspected trivial first-fit/greedy cases as **warnings**, not definitive proof of boredom.
- Flag cases with a single solution where alternative sentimental decisions were intended.
- Do not add generated cases directly to the campaign without human design review.

## Exclusions until specifically approved
No cursed/unstable objects, upgrades, timers, procedural campaign, multiplayer, expensive branch narratives, large custom engine, storefront, or monetisation code. Keep existing static browser launch until evidence warrants change.

## Two independent scorecards
**Game evidence:** solve times per case, observed clarity/errors, abandoned cases, return/continue intention measured by actual behaviour, memorable decisions, repeated play, device issues.  
**Lite evidence for first five tasks:** four of five accepted without wholesale manual rewrites; zero known severe regressions; average <15 minutes human intervention per accepted task, excluding but separately recording setup; test status and actual token/cost telemetry. These are provisional trial thresholds, not causal proof. Compare with *similarly sized* direct Codex work, not aggregate game output.

Record for each task: branch/worktree, baseline SHA, approved scope, elapsed duration, intervention minutes, revisions, actual/unknown tokens and costs, tests and manual checks, code diff, QA verdict and disposition. Do not invent telemetry.

## Decision log
- v0.1 independent review: **APPROVE WITH CHANGES**; reduce 25-case assumption, shorten sessions, prioritise validation and physical-device mobile checks, distinguish game success from Lite success.
- v1.0: foundation trial only; revised PE-001–PE-018 tasks; subsequent implementation conditional on evidence.

**Next action:** execute PE-001 read-only; no gameplay modification in the planning milestone.
