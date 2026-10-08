# Personal Effects — Agent Instructions

## Read first
- Read `docs/PERSONAL-EFFECTS-ROADMAP.md` and `docs/PLUTO-LITE-FOUNDATION-TASKS.md` before changing code. They define approved scope. Do **not** treat proposed campaign features as implemented.
- **Only PE-001–PE-005 are authorised for foundation preparation**, one at a time, with owner review between tasks. PE-001 itself is read-only. Later tasks and gates need explicit approval.
- Inspect actual repository code, git status, tests and commands before assuming anything. Do not import Night Parcel Office mechanics into this game.

## Game identity
Personal Effects is a short supernatural suitcase-packing puzzle about possessions of the deceased. Tone: dry, humane, faintly unsettling British bureaucracy. Core tension: compliant packing versus preserving a meaningful object. Aim for 60–120 seconds per normal case, subject to human playtesting. Prefer clarity, tactile play and intriguing rule interactions over feature volume.

## Engineering rules
- The actual game rules, solver, validator and feedback must share authoritative semantics; no duplicated implementations that drift.
- Any authored case must be demonstrably solvable. Flag intentional narrative alternatives and unclear, impossible, trivially greedy or unfair content for human review.
- Baseline tests come **before** rules refactors. Preserve current outcomes unless the owner explicitly accepts a behaviour change.
- Make incremental changes; no rewrites, framework migration, packages or extensive new architecture without demonstrated need and approval.
- Maintain browser play, usable mobile manipulation, legible rules and clear rotate/undo/seal actions.
- Separate observed defects from speculative enhancements. Tests verify deterministic correctness, not game enjoyment.

## Workflow and safety
- Studio Lite and direct Codex are interchangeable executors; do not depend on undocumented Lite internals. Read actual Lite schema before publishing registry YAML.
- One approved task, branch and isolated worktree at a time. Verify correct repo/root and clean or documented working state. Never edit Night Parcel Office or unrelated repositories.
- No commit, merge, push, deploy, changes to remote settings, or production content promotion without explicit owner permission.
- If the task conflicts with roadmap, cannot be proven safe, or demands a moral/story/visual design decision, stop that change and seek approval.
- Bound token/cost usage; if a hard budget/timeout cannot be enforced, say so before running high-cost jobs. Do not claim limits were enforced if they were only requested.
- Preserve error logs, revision outcomes and Lite telemetry; do not fabricate success/cost data.

## Verification
- Discover actual test/run commands from the repo; do **not** assume Night Parcel Office's `node --test` setup exists here.
- Run focused and full tests when available, browser checks for interactions and mobile layouts when relevant, and report exact results.
- A simulated phone viewport is not a physical touch device. Human playtest and game-feel judgments are distinct from automated QA.
- Track issue reproduction, evidence, accepted tradeoffs, untouched risks and outstanding manual checks.

## Skills / MCP
- Use scoped skills only when relevant: `.agents/skills/game-design-review/SKILL.md`, `.agents/skills/gameplay-validation/SKILL.md`, `.agents/skills/case-design-validation/SKILL.md`.
- Playwright for rendered browser and responsive interaction checks when available; Context7 only for external library documentation genuinely needed; GitHub connector for relevant remote tasks, otherwise local Git.
- Update `docs/AI-SKILLS-REGISTER.md` for material skills/tool usage only, with measured effects or explicitly unknown metrics.

## Deliver
Report: task ID and scope; changed files; tests actually run; case/validator evidence; browser and device evidence; unresolved QA; human intervention/revisions and token/cost availability; next eligible task. No unapproved implementation beyond the assigned slice.
