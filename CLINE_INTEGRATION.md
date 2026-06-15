# Cline Bootstrap

Goal: generate repo AI system. Caveman style. Less token burn. Keep technical truth.

## Caveman Rule

- Use caveman in all generated docs, prompts, workflows, handoffs.
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

- `AGENTS.md` → `@.clinerules/entry-point.md`
- If Cursor exists, also generate `.cursorrules` → load `docs/ai/entry-point.md`
- Generate `.ai-scratchpad.md` for temp plan checkpoints.

## Tree To Generate

- `.clinerules/entry-point.md`
- `.clinerules/*.md` for bug, feature, enhancement, refactor, review, testing, automation, architecture
- `.ai/architecture/architecture-manifest.md`
- `.ai/architecture/code-map.md`
- `.ai/architecture/feature-boundaries.md`
- `.ai/architecture/api-routes.md`
- `.ai/architecture/schema-map.md`
- `.ai/architecture/auth-flow.md`
- `.ai/architecture/middleware-map.md`
- `.ai/architecture/error-handling.md`
- `.ai/architecture/external-services.md`
- `.ai/architecture/risk-matrix.md`
- `.ai/architecture/testing-strategy.md`
- `.ai/architecture/dev-commands.md`
- `.ai/architecture/performance-guidelines.md`
- `.ai/architecture/security-guidelines.md`
- `.ai/file-index/repository-map.md`
- `.ai/workflows/update-file-indexes.md`
- `.ai/workflows/tdd-development.md`
- `.ai/workflows/bug-fix.md`
- `.ai/workflows/feature-implementation.md`
- `.ai/workflows/enhancement.md`
- `.ai/workflows/refactor.md`
- `.ai/workflows/code-review.md`
- `.ai/workflows/debugging.md`
- `.ai/workflows/api-change.md`
- `.ai/workflows/database-change.md`
- `.ai/workflows/dependency-upgrade.md`
- `.ai/debugging/*.md`

## Entry Point

`entry-point.md` must:

- load `code-map` first
- load `feature-boundaries` next
- load `repository-map` next
- load one relevant workflow
- load related tests
- load target source files last
- route tasks by type
- keep context minimal
- no brute-force repo scan

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
