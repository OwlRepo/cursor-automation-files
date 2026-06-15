# Cline Autonomous AI Development System Bootstrap
# Ultimate Deterministic Edition + Smart Environment Detection + Autonomous Task Routing + Dynamic Context Loading

BOOTSTRAP NOTICE

This file is a one-time bootstrap specification used to generate the full AI development support system for Cline in VS Code.

After generation, the repository will contain an AI knowledge system allowing Cline to understand the architecture, navigate safely, and implement changes with minimal hallucinations.

The generated system must allow Cline to automatically determine which documentation to load without requiring the user to reference specific files.

The system must produce deterministic engineering plans and dynamically load only the minimal required context.

---------------------------------------------------------------------

GLOBAL DOCUMENT FORMAT

All generated documentation files must use `.md`.

COMMUNICATION STYLE

Every generated document, workflow, prompt, and handoff file must instruct AI to use caveman style by default:

- terse
- no fluff
- preserve technical accuracy
- keep code, file paths, API names, and error strings exact
- switch to normal mode only when user explicitly asks

---------------------------------------------------------------------

ROOT ENTRY FILE

Create the file at repository root:

AGENTS.md

Content:

For any task always start by loading:

@.clinerules/entry-point.md

Follow the workflow defined in that file before performing analysis, planning, or implementation.

Always prioritize documentation inside `.ai/` before performing repository scans.
Always make generated docs, prompts, workflows, and handoff files default to caveman style.
Every generated file must carry the caveman style rule so future docs inherit it.

---------------------------------------------------------------------

DIRECTORY STRUCTURE

Create two directories:

.clinerules/
.ai/

Final structure:

.clinerules/
.ai/

---------------------------------------------------------------------

PRIMARY OBJECTIVE

Analyze the repository and generate an AI development system that enables Cline to:

• Understand architecture automatically
• Navigate large repositories safely
• Avoid hallucinations
• Identify correct files before editing
• Respect architecture patterns
• Automatically load relevant documentation context
• Produce deterministic implementation plans
• Dynamically load minimal context for large repositories

---------------------------------------------------------------------

PROJECT DETECTION

Detect project type:

Frontend
Backend
Fullstack
Mobile
Desktop
CLI

Detect technology stack:

Frameworks
Languages
Libraries
Database
ORM
State management
Routing

Use configuration files:

package.json
requirements.txt
go.mod
Cargo.toml
pom.xml

---------------------------------------------------------------------

SMART ENVIRONMENT DETECTION

Detect development environment automatically.

Detect:

Runtime
Node.js
Bun
Deno
Python
Java
Go
Rust

Package Manager
npm
pnpm
yarn
bun

Framework Versions
Next.js
React
Vue
Angular
Express
NestJS
FastAPI
Spring

Build Systems
Vite
Webpack
Turbopack
Parcel
Rollup

Testing Framework
Jest
Vitest
Mocha
Cypress
Playwright

Linting / Formatting
ESLint
Prettier
Biome

Containerization
Dockerfile
docker-compose
Kubernetes

CI/CD
GitHub Actions
GitLab CI
CircleCI
Jenkins

Environment Files

.env
.env.local
.env.production
.env.development

Generate:

.ai/architecture/environment-detection.md

---------------------------------------------------------------------

SEMANTIC SEARCH PROTOCOL

Before scanning directories manually perform semantic search.

Search targets:

function names
service names
API routes
components
hooks
database models

Search order:

1 file-index
2 code-map
3 semantic repository search
4 direct file inspection

Avoid brute-force repository scanning.

---------------------------------------------------------------------

MONOREPO DETECTION

Check for:

turbo.json
package.json workspaces
apps/
packages/

If detected document workspace boundaries.

---------------------------------------------------------------------

ARCHITECTURE DOCUMENTATION

Generate inside:

.ai/architecture/

overview.md
tech-stack.md
module-structure.md
api-integration.md

Conditional:

routing.md
state-management.md
data-fetching.md
component-patterns.md
database.md
service-patterns.md

---------------------------------------------------------------------

WEB + REST API INTELLIGENCE

Generate specialized REST architecture documentation.

---------------------------------------------------------------------

API ROUTE DISCOVERY

Automatically identify all API endpoints.

Possible locations:

Next.js → /app/api or /pages/api
Express → router files
NestJS → @Controller
FastAPI → decorators
Spring → @RestController

Generate:

.ai/architecture/api-routes.md

Each endpoint must document:

HTTP method
route path
request schema
response schema
controller
authentication requirements

---------------------------------------------------------------------

SCHEMA DISCOVERY

Detect request and response schemas.

Possible schema sources:

TypeScript interfaces
Zod schemas
Joi validation
DTO classes
OpenAPI
JSON schemas

Generate:

.ai/architecture/schema-map.md

---------------------------------------------------------------------

AUTHENTICATION FLOW

Detect authentication mechanisms.

Examples:

JWT
OAuth
Session cookies
API keys
Passport strategies
Auth middleware

Generate:

.ai/architecture/auth-flow.md

Authentication modules are HIGH RISK.

---------------------------------------------------------------------

MIDDLEWARE MAP

Identify middleware layers.

Examples:

authentication
authorization
validation
rate limiting
logging
error handling

Generate:

.ai/architecture/middleware-map.md

---------------------------------------------------------------------

ERROR HANDLING SYSTEM

Generate:

.ai/architecture/error-handling.md

Document:

error classes
response mapping
logging strategy

---------------------------------------------------------------------

EXTERNAL SERVICE MAP

Detect integrations.

Examples:

payments
email
analytics
third-party APIs
auth providers

Generate:

.ai/architecture/external-services.md

---------------------------------------------------------------------

ENVIRONMENT CONFIGURATION

Generate:

.ai/architecture/environment.md

Document:

environment variables
usage
affected modules

---------------------------------------------------------------------

SEMANTIC CODE MAP

Generate:

.ai/architecture/code-map.md

Include:

system entry points
application flows
core modules
external integrations

---------------------------------------------------------------------

FEATURE BOUNDARY MAP

Generate:

.ai/architecture/feature-boundaries.md

Defines logical boundaries between features.

---------------------------------------------------------------------

DEPENDENCY GRAPH

Generate:

.ai/architecture/dependency-graph.md

Example chain:

Component → Hook → Service → Utility → API → Database

---------------------------------------------------------------------

MODULE OWNERSHIP MAP

Document global modules.

Examples:

authentication
database
configuration
shared utilities

---------------------------------------------------------------------

ARCHITECTURAL DECISION RECORDS

Create directory:

.ai/architecture/adr/

Example:

0001-state-management.md
0002-api-pattern.md

---------------------------------------------------------------------

RISK MATRIX

Generate:

.ai/architecture/risk-matrix.md

LOW RISK

UI components
styles
utilities

MEDIUM RISK

hooks
routes
services

HIGH RISK

authentication
database
global state
shared utilities

---------------------------------------------------------------------

API CONTRACT PROTECTION

Before modifying APIs:

verify request schema
verify response schema
check dependent consumers
ensure backward compatibility

Breaking changes require confirmation.

---------------------------------------------------------------------

DATABASE MIGRATION SAFETY

If database schema changes required:

generate migration plan
preserve compatibility
avoid destructive operations
update models
update queries

---------------------------------------------------------------------

DEV COMMAND DETECTION

Generate:

.ai/architecture/dev-commands.md

Detect commands:

build
lint
test
type-check

---------------------------------------------------------------------

PERFORMANCE GUIDELINES

Generate:

.ai/architecture/performance-guidelines.md

Avoid unnecessary rerenders
avoid large payloads
prefer pagination
cache expensive computations

---------------------------------------------------------------------

FILE INDEX SYSTEM

Generate inside:

.ai/file-index/

src-index.md
components-index.md
hooks-index.md
routes-index.md
stores-index.md
utils-index.md
controllers-index.md
services-index.md
models-index.md

Each generated workflow and prompt file must include caveman style by default.

Each index must include:

file path
purpose
relationships
usage patterns

---------------------------------------------------------------------

FILE INDEX UPDATE PROTOCOL (LLM-DRIVEN)

File index maintenance must be performed by the LLM using the workflow defined in:

.ai/workflows/update-file-indexes.md

Do not treat unattended index generators or scripts as the sole maintenance mechanism; the LLM must explicitly follow that workflow (user-invoked agent prompt or a named project command when defined).

Triggers:

setting up indexes
after substantive code edits
when the user requests a navigation index refresh

Procedure:

1 Run `git status` in the project repository; use `git diff --name-only` as needed so changed paths reflect staged and unstaged work.

2 Map each changed path to the affected index file(s) under `.ai/file-index/` (for example `components/` → `components-index.md`). Do not modify unrelated indexes.

3 Update only those index files that are stale (add/remove rows, correct paths, purpose, relationships). Do not rewrite every index unless a full refresh is required (for example a large-scale rename).

---------------------------------------------------------------------

FILE ANCHOR VERIFICATION

Before editing a file:

1 confirm file path exists
2 extract code anchor
3 verify expected function/class/component

Example:

src/hooks/useAuth.ts

Anchor:

export function useAuth()

---------------------------------------------------------------------

TEST DISCOVERY

Before modifying modules locate related tests.

Search locations:

__tests__/
tests/
*.test.ts
*.spec.ts

---------------------------------------------------------------------

CHANGE SCOPE LIMITER

Small change → single file
Medium change → ≤5 files
Large change → confirmation required

---------------------------------------------------------------------

CRITICAL MODULE PROTECTION

Protected modules:

authentication
database
global state
shared utilities

---------------------------------------------------------------------

LARGE REPOSITORY NAVIGATION

Before scanning repository:

1 consult code-map.md
2 consult feature-boundaries.md
3 consult file-index docs
4 consult dependency graph

Avoid scanning entire repository.

---------------------------------------------------------------------

DEBUGGING SYSTEM

Generate inside:

.ai/debugging/

workflow.md
root-cause-analysis.md
common-issues.md
fix-plan-template.md

---------------------------------------------------------------------

WORKFLOW SYSTEM

Generate inside:

.ai/workflows/

feature-development.md
bug-fix.md
refactoring.md
code-review.md
update-file-indexes.md

---------------------------------------------------------------------

RULE SYSTEM

Generate inside:

.clinerules/

entry-point.md
bug-fix.md
feature-implementation.md
enhancement.md
refactoring.md
code-review.md
testing.md
automation-guidelines.md
architecture-compliance.md

entry-point.md must:

• detect user intent
• identify relevant modules
• load architecture docs
• route to correct workflow

---------------------------------------------------------------------

AUTONOMOUS TASK ROUTING

Entry-point must classify tasks automatically.

Task types:

Bug Fix
Feature Implementation
Enhancement
Refactor
Code Review
Debugging

Routing rules:

Bug → debugging workflow
Feature → feature workflow
Refactor → dependency graph + refactor workflow
Review → architecture + code-review workflow

---------------------------------------------------------------------

DYNAMIC CONTEXT LOADING (DCL)

Large repositories contain too many documentation files to load simultaneously.

Dynamic Context Loading ensures only necessary documentation is loaded.

Stage 1 — Task Classification

Determine task type and load workflow.

Stage 2 — Minimal Architecture Context

Load only:

.ai/architecture/code-map.md
.ai/architecture/feature-boundaries.md

Stage 3 — Feature Scope Detection

Determine feature module using:

route names
service names
component names
file index

Stage 4 — Targeted Documentation Loading

Load only documentation related to that feature.

Examples:

Auth feature

.ai/architecture/auth-flow.md
.ai/architecture/middleware-map.md

API feature

.ai/architecture/api-routes.md
.ai/architecture/schema-map.md

Database feature

.ai/architecture/database.md
.ai/file-index/models-index.md

Stage 5 — Implementation Context

Load relevant:

file-index docs
dependency graph
workflow documentation

Never load entire `.ai` documentation set.

---------------------------------------------------------------------

DETERMINISTIC IMPLEMENTATION PLAYBOOK

Before implementing code generate a deterministic execution plan.

Hard gate:
No implementation is allowed until the full plan is present and approved.

Plan must include:

WHAT
exact feature or change

WHY
problem solved

WHERE
exact files modified

WHEN
execution order

HOW
code-level implementation

BEFORE / AFTER CODE

DEPENDENCY IMPACT

RISK LEVEL

VERIFICATION STEPS

Commands:

build
lint
test
typecheck

ROLLBACK STRATEGY

BEHAVIOR TEST MATRIX (REQUIRED)

Success cases
expected user-visible behavior

Error cases
expected user-visible failure behavior and handling

Edge cases
boundary and unusual real-user scenarios

Behavior-first test rule:
Define tests by expected behavior when a real user uses the feature/fix, not by internal production implementation details.

CODE-FACT EVIDENCE (REQUIRED)

exact file paths inspected
exact symbols affected
current behavior confirmed from repository code/tests/config
constraints derived from existing architecture and dependencies

Do not use assumptions, theory, or hypothesis-based planning.

WEB VERIFICATION RULE

If required facts are external, time-sensitive, or missing from repository evidence, verify using authoritative web sources before finalizing the plan.

OPEN PREFERENCE DECISIONS (ONLY IF NEEDED)

Ask clarifying questions only after evidence-based options are preselected.
Questions must be developer preference/tradeoff choices, not discoverable repo facts.

STRICT TDD ENFORCEMENT

For all behavior-changing code tasks, TDD is mandatory.

RED
write or update the smallest failing test first

GREEN
implement the minimum production code required to pass

REFACTOR
improve structure only after tests pass

Bug fixes must include a regression test that fails before the fix.
Do not implement production code before a failing test exists.

TDD EXEMPTIONS (NON-BEHAVIORAL ONLY)

documentation-only
formatting-only
comment-only
file-index-only
generated documentation-only
non-behavioral configuration-only

---------------------------------------------------------------------

STAFF ENGINEER REVIEW GUARD

Before high-risk changes evaluate:

architecture consistency
dependency impact
security
performance

---------------------------------------------------------------------

QUALITY VERIFICATION

Verify automatically:

build success
imports resolve
types valid
lint passes
tests pass

---------------------------------------------------------------------

HALLUCINATION PREVENTION

Before referencing files:

verify file existence
verify architecture patterns
verify APIs
verify types

If uncertainty remains after evidence-based inspection, ask only preference/tradeoff clarification questions.

---------------------------------------------------------------------

LEARNING SYSTEM

When patterns appear repeatedly update architecture documentation.

Examples:

new service pattern
new component pattern
new API structure

---------------------------------------------------------------------

CONTEXT COMPRESSION

Prioritize documentation loading:

1 code-map.md
2 feature-boundaries.md
3 relevant file-index docs
4 relevant architecture docs
5 debugging docs

---------------------------------------------------------------------

SUCCESS CRITERIA

AI understands architecture automatically
Correct files identified before editing
Plans precede edits
Architecture patterns respected
Indexes remain updated incrementally via git-informed edits following `.ai/workflows/update-file-indexes.md`
Hallucinations minimized

---------------------------------------------------------------------

FINAL INSTRUCTION

Analyze the repository and generate the AI development system according to this specification.
