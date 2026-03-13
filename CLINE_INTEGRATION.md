# Cline Autonomous AI Development System Bootstrap
# Ultimate Deterministic Edition + Smart Environment Detection + Autonomous Task Routing

BOOTSTRAP NOTICE

This file is a one-time bootstrap specification used to generate the full AI development support system for Cline in VS Code.

After generation, the repository will contain an AI knowledge system allowing Cline to understand the architecture, navigate safely, and implement changes with minimal hallucinations.

The generated system must allow Cline to automatically determine which documentation to load without requiring the user to reference specific files.

The system must also produce deterministic implementation plans that describe in precise detail what code will change and why.

---------------------------------------------------------------------

GLOBAL DOCUMENT FORMAT

All generated documentation files must use `.md`.

---------------------------------------------------------------------

ROOT ENTRY FILE

Create the file at repository root:

AGENTS.md

Content must be:

For any task always start by loading:

@.clinerules/entry-point.md

Follow the workflow defined in that file before performing analysis, planning, or implementation.

Always prioritize documentation inside `.ai/` before performing repository scans.

---------------------------------------------------------------------

DIRECTORY STRUCTURE

Create two main directories.

.clinerules/ → AI rules and behavior control  
.ai/ → architecture documentation and indexes

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

---------------------------------------------------------------------

PROJECT DETECTION

Analyze the repository to detect:

Project type

Frontend  
Backend  
Fullstack  
Mobile  
Desktop  
CLI  

Detect technology stack

Frameworks  
Languages  
Libraries  
Database  
ORM  
State management  
Routing  

Use configuration files such as:

package.json  
requirements.txt  
go.mod  
Cargo.toml  
pom.xml  

---------------------------------------------------------------------

SMART ENVIRONMENT DETECTION

Automatically detect development environment and tooling.

Detect:

Runtime Environment
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
Testing Library

Linting / Formatting
ESLint
Prettier
Biome
StandardJS

Containerization
Dockerfile
docker-compose.yml
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

MONOREPO DETECTION

Check for:

turbo.json  
package.json workspaces  
apps/  
packages/  

Document workspace boundaries if detected.

---------------------------------------------------------------------

SEMANTIC SEARCH PROTOCOL

Before scanning directories manually perform semantic search.

Search targets:

function names
services
API routes
components
hooks
database models

Search order:

1 file-index
2 code-map.md
3 semantic repo search
4 direct file inspection

Avoid brute-force repo scans.

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

---------------------------------------------------------------------

API ROUTE DISCOVERY

Detect all API endpoints.

Locations:

Next.js → app/api or pages/api  
Express → router files  
NestJS → @Controller  
FastAPI → decorators  
Spring → @RestController  

Generate:

.ai/architecture/api-routes.md

Document:

method  
route  
request schema  
response schema  
controller  
auth requirements

---------------------------------------------------------------------

SCHEMA DISCOVERY

Detect schemas from:

TypeScript interfaces
Zod
Joi
DTO classes
OpenAPI
JSON schema

Generate:

.ai/architecture/schema-map.md

---------------------------------------------------------------------

AUTHENTICATION FLOW

Detect:

JWT
Session cookies
OAuth
API keys
Passport
Auth middleware

Generate:

.ai/architecture/auth-flow.md

Authentication is HIGH RISK.

---------------------------------------------------------------------

MIDDLEWARE MAP

Detect:

authentication
authorization
validation
rate limiting
logging
error middleware

Generate:

.ai/architecture/middleware-map.md

---------------------------------------------------------------------

ERROR HANDLING

Generate:

.ai/architecture/error-handling.md

Document:

error classes
HTTP responses
logging strategy

---------------------------------------------------------------------

EXTERNAL SERVICE MAP

Detect integrations:

payments
email
analytics
auth providers
third party APIs

Generate:

.ai/architecture/external-services.md

---------------------------------------------------------------------

ENVIRONMENT CONFIGURATION

Generate:

.ai/architecture/environment.md

Document:

env variables
usage
affected modules

---------------------------------------------------------------------

SEMANTIC CODE MAP

Generate:

.ai/architecture/code-map.md

Include:

entry points
system flows
core modules
external integrations

---------------------------------------------------------------------

FEATURE BOUNDARY MAP

Generate:

.ai/architecture/feature-boundaries.md

Define feature ownership boundaries.

---------------------------------------------------------------------

DEPENDENCY GRAPH

Generate:

.ai/architecture/dependency-graph.md

Example chain:

Component → Hook → Service → Utility → API → Database

---------------------------------------------------------------------

ARCHITECTURAL DECISION RECORDS

Directory:

.ai/architecture/adr/

Examples:

0001-state-management.md  
0002-api-pattern.md  

---------------------------------------------------------------------

RISK MATRIX

Generate:

.ai/architecture/risk-matrix.md

LOW
UI components
styles
utilities

MEDIUM
hooks
routes
services

HIGH
authentication
database
global state
shared utilities

---------------------------------------------------------------------

MODULE OWNERSHIP MAP

Document global modules:

authentication
authorization
database
configuration
shared utilities

---------------------------------------------------------------------

API CONTRACT PROTECTION

Before editing APIs:

verify request schema
verify response schema
check dependent consumers
ensure backward compatibility

---------------------------------------------------------------------

DATABASE MIGRATION SAFETY

If schema changes required:

generate migration plan
maintain compatibility
avoid destructive operations
update models and queries

---------------------------------------------------------------------

DEV COMMAND DETECTION

Generate:

.ai/architecture/dev-commands.md

Detect:

build
lint
test
type-check

---------------------------------------------------------------------

PERFORMANCE GUIDELINES

Generate:

.ai/architecture/performance-guidelines.md

Avoid unnecessary rerenders
limit large payloads
use pagination
cache heavy computations

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

Each entry includes:

file path
purpose
dependencies
usage patterns

---------------------------------------------------------------------

FILE ANCHOR VERIFICATION

Before editing files:

confirm path exists
extract code anchor
verify expected function/class

Example:

src/hooks/useAuth.ts

Anchor:

export function useAuth()

---------------------------------------------------------------------

IMPACT ANALYSIS

Before modifying code:

check dependency graph
identify downstream modules
document impact

---------------------------------------------------------------------

CHANGE SCOPE LIMITER

Small → 1 file  
Medium → ≤5 files  
Large → confirmation required  

---------------------------------------------------------------------

CRITICAL MODULE PROTECTION

Protected modules:

authentication
database
global state
shared utilities

---------------------------------------------------------------------

MONOREPO SAFETY

Respect workspace boundaries.

---------------------------------------------------------------------

LARGE REPO NAVIGATION

Always consult:

1 code-map.md
2 feature-boundaries.md
3 file-index
4 architecture docs

Avoid scanning entire repo.

---------------------------------------------------------------------

TEST DISCOVERY

Before modifying modules locate tests.

Search:

__tests__/
tests/
*.test.ts
*.spec.ts

Update tests only if behavior intentionally changes.

---------------------------------------------------------------------

DEBUGGING SYSTEM

Generate:

.ai/debugging/

workflow.md  
root-cause-analysis.md  
common-issues.md  
fix-plan-template.md  

---------------------------------------------------------------------

WORKFLOW SYSTEM

Generate:

.ai/workflows/

feature-development.md  
bug-fix.md  
refactoring.md  
code-review.md  

---------------------------------------------------------------------

RULE SYSTEM

Generate:

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

---------------------------------------------------------------------

AUTONOMOUS TASK ROUTING SYSTEM

entry-point.md must automatically determine user intent.

Classify task type:

Bug Fix
Feature Implementation
Enhancement
Refactor
Code Review
Debugging

Intent detection signals:

keywords
diff context
error messages
user prompt

Routing rules:

Bug Fix → load debugging docs + bug-fix workflow  
Feature → load architecture + feature workflow  
Refactor → load dependency graph + refactor workflow  
Code Review → load architecture + code-review workflow  

---------------------------------------------------------------------

DETERMINISTIC IMPLEMENTATION PLAYBOOK

Before implementing any change the AI must generate a deterministic execution plan.

Plan must include:

1 WHAT
Exact feature or fix.

2 WHY
Problem being solved.

3 WHERE
Exact files modified.

4 WHEN
Step order.

5 HOW
Exact code-level implementation.

6 BEFORE / AFTER CODE
Concrete snippets.

7 DEPENDENCY IMPACT

8 RISK LEVEL

9 VERIFICATION STEPS

Commands:

build
lint
test
typecheck

10 ROLLBACK STRATEGY

---------------------------------------------------------------------

STAFF ENGINEER REVIEW GUARD

Before high-risk changes evaluate:

architecture consistency
dependency impact
security
performance

---------------------------------------------------------------------

QUALITY VERIFICATION

Verify:

build success
lint success
type correctness
tests pass

---------------------------------------------------------------------

HALLUCINATION PREVENTION

Before referencing files:

verify file existence
verify APIs from code
verify architecture patterns

If uncertain ask clarification.

---------------------------------------------------------------------

LEARNING SYSTEM

When patterns appear repeatedly update architecture docs.

Examples:

new service pattern
new component pattern
new API structure

---------------------------------------------------------------------

CONTEXT COMPRESSION

Load context in order:

1 code-map.md
2 feature-boundaries.md
3 file-index
4 architecture docs
5 debugging docs

---------------------------------------------------------------------

SUCCESS CRITERIA

AI understands architecture automatically
Correct files identified before editing
Plans precede edits
Architecture patterns respected
Indexes remain updated
Hallucinations minimized

---------------------------------------------------------------------

FINAL INSTRUCTION

Analyze the repository and generate the AI development system according to this specification.