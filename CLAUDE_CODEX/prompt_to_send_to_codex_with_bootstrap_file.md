[$caveman](/Users/romeoangelesjr/.agents/skills/caveman/SKILL.md)

Codex Prompt: Bootstrap Project AI Workflow from CLAUDE_CODEX.md

You are working inside the target project repository.

A bootstrap source spec is available as:

CLAUDE_CODEX.md

Objective

Use CLAUDE_CODEX.md to set up or update this project’s Claude + Codex AI workflow.

CLAUDE_CODEX.md is the bootstrap source spec.

Do not treat CLAUDE_CODEX.md as a generated project file.

Use it to generate/update the project AI setup files it defines.

Expected Developer Workflow

The generated setup should support this simple developer flow:

Developer:
Handle this task: [raw details]
Claude:
Routes, investigates, plans, and writes handoff after approval.
Developer:
Approved. Create implementation handoff.
Claude:
Writes `.ai-scratchpad.md`.
Developer to Codex:
Implement from `.ai-scratchpad.md`.
Developer to Codex:
Validate from `.ai-scratchpad.md`.

Required Behavior

1. Read CLAUDE_CODEX.md fully.
2. Inspect the current project tree.
3. Detect existing AI setup files.
4. Preserve useful existing project-specific content.
5. Generate missing AI setup files from the bootstrap spec.
6. Update stale AI setup files to match the bootstrap spec.
7. Do not overwrite project-specific docs blindly.
8. Do not invent package scripts.
9. Do not create active .claude/settings.json unless the supported Claude Code settings schema is verified.
10. If Claude Code settings schema is not verified, create .claude/settings.example.json instead.
11. Do not commit.
12. Do not push.

Files To Generate Or Update

Generate/update the files required by CLAUDE_CODEX.md, including where applicable:

CLAUDE.md
AGENTS.md
.codex/instructions.md
.ai-scratchpad.md
.claude/settings.example.json
docs/ai/entry-point.md
docs/ai/task-router.md
docs/ai/architecture-manifest.md
docs/ai/module-ownership-map.md
docs/ai/file-index/repository-map.md
docs/ai/contracts/api-contracts.md
docs/ai/contracts/db-contracts.md
docs/ai/testing-strategy.md
docs/ai/risk-register.md
docs/ai/context-refresh.md
docs/ai/prompts/bugfix-rca.md
docs/ai/prompts/bugfix-plan.md
docs/ai/prompts/feature-plan.md
docs/ai/prompts/refactor-plan.md

Only create files that are defined by CLAUDE_CODEX.md.

If some files are not defined in the current bootstrap spec, do not invent them.

Bootstrap Rules

Follow the bootstrap spec exactly.

Generated files must not contradict CLAUDE_CODEX.md.

Generated files must support:

- Claude as router, planner, investigator, and handoff writer.
- Codex as implementor, validator, and diff guard.
- Human approval before risky implementation.
- Natural developer task input.
- Task routing through docs/ai/task-router.md.
- Context docs as maps only, not proof.
- Source-code verification as final truth.
- .ai-scratchpad.md status-gated handoff.
- Codex implementation only when .ai-scratchpad.md is ready.
- Codex validation only from .ai-scratchpad.md.
- Git diff boundary check.
- No RCA or architecture planning by Codex.

Required Safety Rules

Do not:

- edit application source code
- implement any product feature
- fix unrelated bugs
- refactor unrelated files
- install dependencies
- modify package scripts unless explicitly required by the bootstrap spec
- run destructive commands
- commit
- push

This task is only for AI workflow bootstrap setup.

Verification

After setup:

1. Validate Markdown manually.
2. Ensure all fenced code blocks are closed.
3. Ensure generated files are internally consistent.
4. Confirm generated files do not contradict CLAUDE_CODEX.md.
5. Confirm CLAUDE.md routes Claude to the generated workflow docs.
6. Confirm .codex/instructions.md tells Codex to implement/validate only from .ai-scratchpad.md.
7. Confirm .ai-scratchpad.md is an empty handoff shell.
8. Confirm context docs state they are maps only and not proof.
9. Confirm no application source files were changed.
10. Run git diff --name-only and report changed files.

Do not run project build/test commands unless the repo clearly documents a safe docs validation command.

Do not invent verification commands.

Final Output Required

When done, output:

1. Files created
2. Files updated
3. Files skipped
4. Existing content preserved
5. Verification performed
6. git diff --name-only result
7. Any config uncertainty
8. Any manual follow-up required

Do not commit.

Do not push.
