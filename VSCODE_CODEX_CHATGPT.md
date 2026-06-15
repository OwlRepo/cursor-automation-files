# VS Code + Codex + ChatGPT Bootstrap

Goal: generate AI system for VS Code + Codex + ChatGPT. Caveman style. Less token burn. Keep truth.

## Caveman Rule

- Caveman in all generated docs, prompts, workflows, handoffs.
- Keep code, paths, commands, API names, error strings exact.
- No fluff. No hedging. Short lines.
- Stop caveman only if user says `normal mode` or `stop caveman`.

## Caveman Check

- Run `command -v caveman`.
- If missing, install from [juliusbrussee/caveman](https://github.com/juliusbrussee/caveman).
- Suggested install: `npx skills add JuliusBrussee/caveman`.
- If still missing, stop and tell user install first.
- Why important: keeps style locked, cuts tokens, stops drift.

## Root Files

- `AGENTS.md` → `@docs/ai/entry-point.md`
- If Cursor exists, also generate `.cursorrules` → load `docs/ai/entry-point.md`
- Generate `.ai-scratchpad.md` for temp plan checkpoints.

## Tree To Generate

- `docs/ai/entry-point.md`
- `docs/ai/operating-principles.md`
- `docs/ai/context-loading.md`
- `docs/ai/task-routing.md`
- `docs/ai/implementation-playbook.md`
- `docs/ai/verification.md`
- `docs/ai/hallucination-prevention.md`
- `docs/ai/risk-matrix.md`
- `docs/ai/rollback.md`
- `docs/ai/chatgpt-handoff.md`
- `docs/ai/codex-handoff.md`
- `docs/ai/architecture/architecture-manifest.md`
- `docs/ai/architecture/code-map.md`
- `docs/ai/architecture/feature-boundaries.md`
- `docs/ai/architecture/api-routes.md`
- `docs/ai/architecture/schema-map.md`
- `docs/ai/architecture/auth-flow.md`
- `docs/ai/architecture/middleware-map.md`
- `docs/ai/architecture/error-handling.md`
- `docs/ai/architecture/external-services.md`
- `docs/ai/architecture/risk-matrix.md`
- `docs/ai/architecture/testing-strategy.md`
- `docs/ai/architecture/dev-commands.md`
- `docs/ai/architecture/performance-guidelines.md`
- `docs/ai/architecture/security-guidelines.md`
- `docs/ai/file-index/repository-map.md`
- `docs/ai/workflows/update-file-indexes.md`
- `docs/ai/workflows/tdd-development.md`
- `docs/ai/workflows/bug-fix.md`
- `docs/ai/workflows/feature-implementation.md`
- `docs/ai/workflows/enhancement.md`
- `docs/ai/workflows/refactor.md`
- `docs/ai/workflows/code-review.md`
- `docs/ai/workflows/debugging.md`
- `docs/ai/workflows/api-change.md`
- `docs/ai/workflows/database-change.md`
- `docs/ai/workflows/dependency-upgrade.md`
- `docs/ai/prompts/codex-task-prompt.md`
- `docs/ai/prompts/chatgpt-planning-prompt.md`
- `docs/ai/prompts/code-review-prompt.md`
- `docs/ai/prompts/debugging-prompt.md`
- `docs/ai/prompts/refactor-prompt.md`
- `.codex/instructions.md`
- `.codex/local-workflow.md`
- `.codex/safety.md`
- `.vscode/tasks.json`
- `.vscode/extensions.json`
- `.vscode/settings.json`

## Context Order

For code change:

1. `docs/ai/architecture/code-map.md`
2. `docs/ai/architecture/feature-boundaries.md`
3. `docs/ai/file-index/repository-map.md`
4. relevant workflow
5. related tests
6. target files

## Routing

- Bug fix → bug workflow
- Feature → feature workflow
- Enhancement → enhancement workflow
- Refactor → refactor workflow
- Review → code-review workflow
- Debugging → debugging workflow
- API change → api-change workflow
- Database change → database-change workflow
- Dependency upgrade → dependency-upgrade workflow
- Docs update → docs workflow if present

## TDD

- TDD mandatory for behavior change.
- RED first. Smallest failing test.
- GREEN second. Minimum code.
- REFACTOR last. No new behavior.
- Bug fix needs regression test.
- Exempt only: docs, formatting, comments, file-index, generated docs, non-behavioral config.
- Complex UI/CSS/visual layout may skip strict TDD only if DOM/a11y checks cannot prove result. Need human visual check.

## Plan

Before code edit, write:

- WHAT
- WHY
- WHERE
- WHEN
- HOW
- BEFORE/AFTER
- DEPENDENCY IMPACT
- RISK
- TEST PLAN
- BEHAVIOR TEST MATRIX
- CODE FACTS
- ROLLBACK

## Safety

- No new npm package or dependency without human approval.
- First try native web APIs or repo utilities.
- Check current branch before edit.
- Never commit on `main` or `master`.
- Use Conventional Commits.
- High-risk change needs confirmation.
- Build, test, typecheck fail 3 times in row → stop, revert, print failure chain, ask human review.

## File Index

- Use one dense `repository-map.md`.
- Update rows only.
- Use `git status` + `git diff --name-only`.
- Do not rewrite unrelated rows.

## Final

- Preserve caveman style in generated docs.
- Preserve minimal context loading.
- Prefer short docs over many stale docs.
