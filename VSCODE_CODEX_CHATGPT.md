# VS Code + Codex + ChatGPT AI Development System
# Ultimate Edition — Token-Efficient Autonomous Engineering Workflow

BOOTSTRAP NOTICE

This file is a one-time bootstrap specification used to generate a complete AI development system for this repository.

Target environment:

- VS Code
- Codex CLI
- Codex VS Code Extension
- ChatGPT for planning, architecture review, debugging, and high-level reasoning

After generation, all development workflows must rely on the generated AI documentation instead of this bootstrap file.

The generated system must help AI agents:

- Understand the repository architecture
- Navigate large codebases safely
- Identify correct files before editing
- Avoid hallucinated paths, APIs, and dependencies
- Respect existing patterns
- Load only minimal required context
- Produce deterministic implementation plans
- Verify work using project commands
- Keep navigation indexes updated incrementally

---

# GLOBAL OUTPUT FORMAT

All generated documentation MUST use `.md`.

Do not generate `.mdc`.

---

# ROOT AGENT ENTRY FILE

Generate at repository root:

AGENTS.md

Content:

Any AI coding agent working in this repository must start by reading:

@docs/ai/entry-point.md

Then follow the routing, context-loading, planning, implementation, verification, and safety rules defined there.

Always prioritize generated AI documentation before scanning repository files.

Never edit files before verifying:
- file path exists
- relevant architecture pattern
- affected dependencies
- related tests
- risk level

---

# DIRECTORY STRUCTURE TO GENERATE

Generate:

docs/ai/
  entry-point.md
  operating-principles.md
  context-loading.md
  task-routing.md
  implementation-playbook.md
  verification.md
  hallucination-prevention.md
  risk-matrix.md
  rollback.md
  chatgpt-handoff.md
  codex-handoff.md

docs/ai/architecture/
  overview.md
  tech-stack.md
  environment-detection.md
  module-structure.md
  code-map.md
  feature-boundaries.md
  dependency-graph.md
  api-routes.md
  schema-map.md
  auth-flow.md
  middleware-map.md
  error-handling.md
  external-services.md
  environment.md
  dev-commands.md
  performance-guidelines.md
  testing-strategy.md
  security-guidelines.md

docs/ai/file-index/
  src-index.md
  components-index.md
  hooks-index.md
  routes-index.md
  stores-index.md
  utils-index.md
  controllers-index.md
  services-index.md
  models-index.md
  tests-index.md

docs/ai/workflows/
  bug-fix.md
  feature-implementation.md
  enhancement.md
  refactor.md
  code-review.md
  debugging.md
  update-file-indexes.md
  api-change.md
  database-change.md
  dependency-upgrade.md

docs/ai/prompts/
  codex-task-prompt.md
  chatgpt-planning-prompt.md
  code-review-prompt.md
  debugging-prompt.md
  refactor-prompt.md

.codex/
  instructions.md
  local-workflow.md
  safety.md

.vscode/
  tasks.json
  extensions.json
  settings.json

---

# PRIMARY OBJECTIVE

Analyze the repository and generate a complete AI development system for VS Code + Codex + ChatGPT.

The system must allow the AI to automatically determine:

- what type of task is being requested
- what documentation must be loaded
- what files are likely affected
- what commands verify correctness
- what risks are involved
- when user confirmation is required

---

# PROJECT DETECTION

Detect project type:

- Frontend
- Backend
- Fullstack
- Mobile
- Desktop
- CLI
- Library
- Monorepo

Detect technologies using:

- package.json
- pnpm-lock.yaml
- yarn.lock
- bun.lockb
- package-lock.json
- turbo.json
- nx.json
- requirements.txt
- pyproject.toml
- go.mod
- Cargo.toml
- pom.xml
- build.gradle
- Dockerfile
- docker-compose.yml
- .github/workflows

Generate:

docs/ai/architecture/environment-detection.md

Document:

- runtime
- package manager
- framework
- language versions
- build system
- test framework
- linting
- formatting
- database
- ORM
- auth system
- deployment target
- CI/CD
- environment files

---

# VS CODE SETUP

Generate `.vscode/extensions.json` recommending relevant extensions based on detected stack.

Always include when applicable:

- OpenAI / Codex extension
- ESLint
- Prettier
- TypeScript tooling
- Tailwind CSS IntelliSense
- Docker
- Prisma
- Python
- Playwright
- GitHub Actions

Generate `.vscode/settings.json` with safe defaults:

- format on save only if formatter detected
- TypeScript SDK path if applicable
- lint integration if detected
- editor code actions on save if safe

Generate `.vscode/tasks.json` with tasks for detected commands:

- install
- dev
- build
- lint
- typecheck
- test
- test:watch
- e2e
- format
- db:migrate
- db:generate

Do not invent commands. Only include commands that exist or can be safely inferred from package scripts/tooling.

---

# CODEX SETUP

Generate:

.codex/instructions.md

Content must tell Codex:

- Start with AGENTS.md
- Load docs/ai/entry-point.md
- Never brute-force scan the repo first
- Use semantic navigation docs first
- Verify files before editing
- Prefer small diffs
- Ask for confirmation before high-risk changes
- Run verification commands after edits
- Summarize changed files and rollback path

Generate:

.codex/local-workflow.md

Include:

- how to start Codex in VS Code terminal
- how to give Codex scoped tasks
- how to avoid token waste
- how to request plan-only mode
- how to request implementation mode
- how to request review mode

Generate:

.codex/safety.md

Include:

- no secrets exposure
- no destructive git commands
- no production database changes
- no dependency upgrades without confirmation
- no broad rewrites unless explicitly requested

---

# CHATGPT ROLE

Generate:

docs/ai/chatgpt-handoff.md

ChatGPT should be used for:

- architecture planning
- debugging strategy
- interview-style explanation
- reviewing Codex plans
- breaking down large work
- creating implementation prompts
- comparing approaches
- reviewing risky changes

ChatGPT should not be the source of truth for repo files unless the user provides files or connects GitHub/project context.

When using ChatGPT with the repo:

- paste relevant docs from docs/ai
- paste Codex plan
- paste exact error logs
- paste minimal file snippets
- ask for decision support, not blind implementation

---

# CODEX ROLE

Generate:

docs/ai/codex-handoff.md

Codex should be used for:

- local repository inspection
- precise file edits
- running tests
- running lint/typecheck
- producing diffs
- updating docs/ai indexes
- implementing scoped tasks

Codex must not start implementation until it has produced a deterministic plan unless the task is trivial.

---

# SEMANTIC SEARCH PROTOCOL

Before scanning repository files, search in this order:

1. docs/ai/file-index
2. docs/ai/architecture/code-map.md
3. docs/ai/architecture/feature-boundaries.md
4. semantic repo search
5. direct file inspection

Avoid brute-force full-repo scans unless indexes are missing or stale.

---

# DYNAMIC CONTEXT LOADING

To minimize tokens, entry-point.md must enforce this loading order:

1. docs/ai/architecture/code-map.md
2. docs/ai/architecture/feature-boundaries.md
3. relevant file index
4. relevant architecture document
5. relevant workflow document
6. related tests
7. target source files

Do not load all documentation for every task.

---

# TASK ROUTING

entry-point.md must classify tasks as:

- Bug Fix
- Feature Implementation
- Enhancement
- Refactor
- Code Review
- Debugging
- API Change
- Database Change
- Dependency Upgrade
- Documentation Update

Routing:

Bug Fix → workflows/bug-fix.md
Feature → workflows/feature-implementation.md
Enhancement → workflows/enhancement.md
Refactor → workflows/refactor.md
Review → workflows/code-review.md
Debugging → workflows/debugging.md
API change → workflows/api-change.md
Database change → workflows/database-change.md
Dependency upgrade → workflows/dependency-upgrade.md

---

# DETERMINISTIC IMPLEMENTATION PLAN

Before code edits, generate a plan with:

WHAT:
Exact functionality or fix

WHY:
Problem being solved

WHERE:
Exact files expected to change

WHEN:
Implementation order

HOW:
Code-level approach

BEFORE / AFTER:
Relevant snippets when useful

DEPENDENCY IMPACT:
Affected modules and imports

RISK LEVEL:
LOW / MEDIUM / HIGH

TEST PLAN:
Specific commands and test files

BEHAVIOR TEST MATRIX (REQUIRED):
- Success cases (expected user-visible behavior)
- Error cases (expected error handling and user-visible failures)
- Edge cases (boundary and unusual real-user scenarios)

All test definitions must validate expected behavior from user perspective, not internal production implementation details.

CODE-FACT EVIDENCE (REQUIRED):
- exact file paths inspected
- exact functions/components/classes/routes involved
- current behavior observed from repository evidence
- constraints derived from existing code/tests/config

Plans must be evidence-grounded. Do not use theory, guesses, or hypothetical internals.

WEB VERIFICATION RULE:
If required facts are external, time-variant, or not derivable from repository evidence, perform targeted web verification before finalizing the plan and cite the source category used (official docs, vendor docs, standards, release notes).

ROLLBACK:
How to undo safely

OPEN PREFERENCE DECISIONS (ONLY IF NEEDED):
- ask questions only after best options are preselected from evidence
- questions must be preference/tradeoff decisions, not discoverable repo facts

Hard gate: Do not edit until this plan is complete. Missing any required section blocks implementation.

---

# FILE ANCHOR VERIFICATION

Before editing any file:

- confirm the path exists
- identify the function/component/class/hook to modify
- inspect nearby code
- verify imports and exports
- check related tests
- check consumers if public API is affected

---

# RISK MATRIX

Generate:

docs/ai/risk-matrix.md

LOW:
- styles
- isolated UI components
- copy changes
- small utilities

MEDIUM:
- hooks
- services
- routes
- data fetching
- forms
- validation

HIGH:
- authentication
- authorization
- database schema
- migrations
- global state
- shared utilities
- payment logic
- security-sensitive middleware
- API response contracts
- dependency upgrades
- build configuration
- CI/CD

High-risk changes require explicit confirmation before implementation.

---

# API CONTRACT PROTECTION

Before modifying APIs:

- identify route
- identify request schema
- identify response schema
- identify consumers
- preserve backward compatibility
- update tests
- update docs/ai/architecture/api-routes.md
- update docs/ai/architecture/schema-map.md

Breaking changes require confirmation.

---

# DATABASE SAFETY

Before schema/database changes:

- inspect ORM/schema files
- inspect existing migrations
- identify affected queries
- generate migration plan
- avoid destructive operations
- preserve backward compatibility where possible
- update models
- update seed scripts if needed
- update tests

Never run production migrations.

---

# ENVIRONMENT SAFETY

Document environment variables in:

docs/ai/architecture/environment.md

For each variable include:

- name
- purpose
- required/optional
- local usage
- production usage
- affected modules

Never print secret values.

Use placeholders only.

---

# FILE INDEX SYSTEM

Each file index entry must include:

- file path
- purpose
- main exports
- dependencies
- consumers
- usage patterns
- risk level

Indexes must be concise and navigation-focused.

Do not paste full source code into indexes.

---

# FILE INDEX UPDATE WORKFLOW

Generate:

docs/ai/workflows/update-file-indexes.md

Rules:

1. Run `git status`.
2. Run `git diff --name-only` if needed.
3. Map changed files to affected indexes.
4. Update only stale index entries.
5. Add new files.
6. Remove deleted files.
7. Do not rewrite unrelated indexes.
8. For large renames, perform a focused full refresh.
9. Keep entries concise.

Triggers:

- after substantive code edits
- after file moves
- after new feature creation
- when user requests index refresh

---

# TEST DISCOVERY

Before modifying code, locate tests using:

- __tests__/
- tests/
- *.test.*
- *.spec.*
- e2e/
- playwright/
- cypress/

Generate:

docs/ai/architecture/testing-strategy.md
docs/ai/file-index/tests-index.md

Document:

- test framework
- test command
- test locations
- mocking patterns
- e2e setup
- minimum verification required

---

# DEV COMMAND DETECTION

Generate:

docs/ai/architecture/dev-commands.md

Detect and document:

- install
- dev
- build
- lint
- typecheck
- test
- e2e
- format
- database commands

Do not invent commands.

If missing, write:

“Not detected.”

---

# HALLUCINATION PREVENTION

Generate:

docs/ai/hallucination-prevention.md

Rules:

- never reference a file without verifying it exists
- never assume API shape
- never assume package availability
- never assume environment variables
- never assume test command
- never invent routes
- never invent components
- never edit based only on filename guesses
- when uncertain, inspect first

---

# CHANGE SCOPE LIMITER

Default limits:

Small:
- 1 to 2 files
- no architecture change

Medium:
- up to 5 files
- localized behavior change

Large:
- more than 5 files
- architectural impact
- requires confirmation

Large changes must be broken into phases.

---

# STAFF ENGINEER REVIEW GUARD

Before medium/high-risk changes, evaluate:

- architecture consistency
- dependency direction
- API compatibility
- security
- performance
- test coverage
- rollback safety

Generate this review before implementation.

---

# PERFORMANCE GUIDELINES

Generate:

docs/ai/architecture/performance-guidelines.md

Include relevant stack-specific guidance.

For React/Next.js:

- avoid unnecessary rerenders
- memoize only when useful
- avoid oversized client components
- avoid unnecessary global state
- prefer server components where appropriate
- use pagination for large data
- cache expensive operations
- optimize images
- avoid waterfall requests

For backend:

- avoid N+1 queries
- validate payloads
- paginate list endpoints
- use indexes for common queries
- avoid blocking operations
- centralize error handling

---

# SECURITY GUIDELINES

Generate:

docs/ai/architecture/security-guidelines.md

Include:

- input validation
- auth checks
- authorization boundaries
- secret handling
- dependency risk
- XSS prevention
- CSRF/session handling if applicable
- SQL injection prevention
- rate limiting if applicable

---

# WORKFLOW DOCUMENTS

Each workflow must include:

- when to use it
- required context files
- required inspection steps
- planning requirements
- implementation rules
- verification commands
- documentation update requirements
- rollback steps

---

# PROMPT TEMPLATES

Generate reusable prompts.

docs/ai/prompts/codex-task-prompt.md:

Create a concise Codex prompt template:

- task
- expected behavior
- files/area
- constraints
- verification commands
- output format

docs/ai/prompts/chatgpt-planning-prompt.md:

Create a ChatGPT planning prompt template:

- problem
- repo context
- relevant docs pasted
- current errors/logs
- desired output
- ask for plan, risks, edge cases

docs/ai/prompts/code-review-prompt.md:

Create a review prompt focused on:

- correctness
- maintainability
- security
- performance
- tests
- edge cases

---

# CONTEXT COMPRESSION RULES

Keep generated docs token-efficient.

Rules:

- prefer tables
- avoid long prose
- summarize patterns
- include file paths
- include only useful architecture facts
- do not duplicate the same information across many docs
- link to related docs instead of repeating
- keep indexes concise

---

# LEARNING SYSTEM

When repeated patterns are discovered, update the appropriate architecture doc.

Examples:

- new service pattern
- new component pattern
- new API convention
- new validation pattern
- new testing pattern
- new state management pattern

Do not update architecture docs for one-off code.

---

# QUALITY VERIFICATION

After edits, run the strongest available safe commands:

Preferred order:

1. typecheck
2. lint
3. related tests
4. full test suite if reasonable
5. build

If a command is unavailable, document that it was not detected.

If a command fails, report:

- command
- failure summary
- likely cause
- whether failure is related to the change

---

# FINAL GENERATION TASK

Analyze this repository and generate the complete VS Code + Codex + ChatGPT AI development system exactly as specified.

After generating files, output:

1. created files
2. detected stack
3. detected commands
4. high-risk areas
5. how to use this system with Codex in VS Code
6. first recommended Codex prompt to run
