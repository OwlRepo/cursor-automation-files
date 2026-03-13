# Cline Autonomous AI Development System Bootstrap (Ultimate Deterministic Edition + Smart Environment Detection)

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

The AI must automatically detect the runtime environment and development tooling used by the repository.

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

Linting and Formatting
ESLint
Prettier
Biome
StandardJS

Containerization
Dockerfile
docker-compose.yml
Kubernetes manifests

CI/CD Systems
GitHub Actions
GitLab CI
CircleCI
Jenkins

Environment Configuration
.env
.env.local
.env.production
.env.development

Generate documentation:

.ai/architecture/environment-detection.md

Document:

runtime
package manager
framework versions
build system
test framework
CI/CD
container setup

---------------------------------------------------------------------

MONOREPO DETECTION

Check for:

turbo.json  
package.json workspaces  
apps/  
packages/  

If detected document workspace boundaries.

---------------------------------------------------------------------

SEMANTIC SEARCH PROTOCOL

Before scanning directories manually, perform semantic search.

Search targets:

function names  
service names  
API routes  
component names  
hooks  
database models  

Search order:

1. file-index docs  
2. code-map.md  
3. semantic search across repository  
4. direct file inspection  

Avoid brute force repository scans.

---------------------------------------------------------------------

ARCHITECTURE DOCUMENTATION

Generate inside:

.ai/architecture/

Files:

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

WEB + REST API ARCHITECTURE INTELLIGENCE

Generate specialized documentation for web applications and REST APIs.

---------------------------------------------------------------------

API ROUTE DISCOVERY

Automatically identify all API endpoints.

Possible locations:

Next.js → /app/api or /pages/api  
Express → router definitions  
NestJS → @Controller decorators  
FastAPI → @app.get/post  
Spring → @RestController  

Generate:

.ai/architecture/api-routes.md

Each endpoint must document:

HTTP method  
route path  
request schema  
response schema  
controller/service handling  
authentication requirements  

---------------------------------------------------------------------

SCHEMA DISCOVERY

Identify request and response schemas used by APIs.

Possible schema sources:

TypeScript interfaces  
Zod schemas  
Joi validation  
DTO classes  
OpenAPI definitions  
JSON schemas  

Generate:

.ai/architecture/schema-map.md

Each schema must document:

fields  
types  
validation rules  
where it is used  

---------------------------------------------------------------------

AUTHENTICATION FLOW DOCUMENTATION

Detect authentication mechanisms.

Examples:

JWT  
Session cookies  
OAuth  
API keys  
Bearer tokens  
Passport strategies  
Auth middleware  

Generate:

.ai/architecture/auth-flow.md

Document:

login flow  
token validation  
middleware guards  
authorization checks  
role based access  

Authentication modules are HIGH RISK.

---------------------------------------------------------------------

MIDDLEWARE MAP

Identify middleware layers.

Examples:

authentication middleware  
authorization middleware  
request validation  
rate limiting  
logging  
error handling  

Generate:

.ai/architecture/middleware-map.md

Document execution order and scope.

---------------------------------------------------------------------

ERROR HANDLING SYSTEM

Identify how errors propagate through the system.

Examples:

global error middleware  
try/catch patterns  
error classes  
HTTP response mapping  

Generate:

.ai/architecture/error-handling.md

Document:

error types  
response formatting  
logging behavior  

---------------------------------------------------------------------

EXTERNAL SERVICE MAP

Detect integrations with external services.

Examples:

payment providers  
email services  
auth providers  
analytics  
third party APIs  

Generate:

.ai/architecture/external-services.md

Each integration must document:

service name  
client library  
API wrapper location  
retry strategy  
error handling  

---------------------------------------------------------------------

ENVIRONMENT CONFIGURATION

Identify environment variables used by the system.

Generate:

.ai/architecture/environment.md

Document:

variable name  
purpose  
default behavior  
affected modules  

---------------------------------------------------------------------

SEMANTIC CODE MAP

Generate:

.ai/architecture/code-map.md

Purpose:

Provide a navigation map for the repository.

Include:

System entry points  
Application flows  
Core modules  
External integrations  

---------------------------------------------------------------------

FEATURE BOUNDARY MAP

Generate:

.ai/architecture/feature-boundaries.md

Purpose:

Define boundaries between system features to prevent unrelated edits.

---------------------------------------------------------------------

DEPENDENCY GRAPH

Generate:

.ai/architecture/dependency-graph.md

Document relationships:

Component → Hook → Service → Utility → API

Used for impact analysis.

---------------------------------------------------------------------

ARCHITECTURAL DECISION RECORDS

Create directory:

.ai/architecture/adr/

Example files:

0001-state-management.md  
0002-api-pattern.md  

Purpose:

Preserve architecture decisions.

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

HIGH RISK edits must trigger confirmation.

---------------------------------------------------------------------

MODULE OWNERSHIP MAP

Critical modules must be identified and documented.

Examples:

authentication  
authorization  
database access  
configuration  
shared utilities  

These modules are global dependencies.

Changes require deeper impact analysis.

---------------------------------------------------------------------

API CONTRACT PROTECTION

Before modifying any API layer:

1. Identify request schema  
2. Identify response schema  
3. Verify dependent consumers  
4. Verify backward compatibility  

If breaking change detected:

Require explicit user confirmation.

---------------------------------------------------------------------

DATABASE MIGRATION SAFETY

If database schema changes are required:

1. Generate migration plan  
2. Preserve backward compatibility  
3. Avoid destructive operations unless confirmed  
4. Update related models  
5. Update dependent queries  

Schema changes require confirmation.

---------------------------------------------------------------------

DEV COMMAND DETECTION

Generate:

.ai/architecture/dev-commands.md

Detect commands such as:

build  
lint  
test  
type-check  

Examples:

npm run build  
npm run lint  
npm run test  

---------------------------------------------------------------------

PERFORMANCE GUIDELINES

Generate:

.ai/architecture/performance-guidelines.md

Guidelines:

Avoid unnecessary rerenders  
Avoid large websocket payloads  
Prefer pagination for large datasets  
Cache expensive computations  

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

Each index must include:

file path  
purpose  
relationships  
usage patterns  

---------------------------------------------------------------------

FILE ANCHOR VERIFICATION

Before editing a file:

1. Confirm file path exists  
2. Extract code anchor  
3. Verify anchor matches expected function/class/component  

Example:

File:

src/hooks/useAuth.ts

Anchor:

export function useAuth()

---------------------------------------------------------------------

IMPACT ANALYSIS

Before modifying code:

1. Check dependency graph  
2. Identify downstream modules  
3. Document impact  

---------------------------------------------------------------------

CHANGE SCOPE LIMITER

Small change → single file  
Medium change → ≤5 files  
Large change → confirmation required  

---------------------------------------------------------------------

CRITICAL MODULE PROTECTION

Critical modules include:

Authentication  
Database access  
Global state stores  
Shared utilities  

Changes require additional verification.

---------------------------------------------------------------------

MONOREPO SAFETY

If monorepo detected:

Respect workspace boundaries.

Avoid editing outside the relevant workspace.

---------------------------------------------------------------------

LARGE REPOSITORY NAVIGATION

Before scanning repository:

1. Consult code-map.md  
2. Use file-index docs  
3. Use dependency graph  

Avoid scanning entire repository unnecessarily.

---------------------------------------------------------------------

TEST DISCOVERY

Before modifying a module:

Locate related tests.

Search locations:

__tests__/  
tests/  
*.test.ts  
*.spec.ts  

Understand expected behavior before editing.

After modification:

Update failing tests only if behavior intentionally changes.

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
• locate relevant files  
• load architecture docs  
• route to correct workflow  

---------------------------------------------------------------------

DETERMINISTIC IMPLEMENTATION PLAYBOOK

Before implementing any change the AI must generate a deterministic execution plan.

The plan must NOT be high level.

It must include precise technical implementation details.

Each plan must include the following sections:

1. WHAT  
Exact functionality or change being implemented.

2. WHY  
Reason for the change including problem being solved.

3. WHERE  
Exact files to be modified.

Example:

src/controllers/userController.ts  
src/services/userService.ts  

4. WHEN  
Execution order of implementation steps.

5. HOW  
Exact code-level modifications including functions, imports, data structures, and API calls.

6. BEFORE / AFTER CODE  
Concrete code snippets showing current implementation and new implementation.

7. DEPENDENCY IMPACT  
Modules affected downstream.

8. RISK ASSESSMENT  
Risk level based on risk matrix.

9. VERIFICATION STEPS  
Commands to validate build, lint, tests, and type checking.

10. ROLLBACK STRATEGY  
Steps to revert changes if implementation fails.

---------------------------------------------------------------------

STAFF ENGINEER REVIEW GUARD

Before large or high-risk changes evaluate:

Architecture consistency  
Dependency impact  
Security implications  
Performance impact  

---------------------------------------------------------------------

QUALITY VERIFICATION

Verify automatically:

Compilation success  
Imports resolve  
Types valid  
Lint passes  
Tests pass  
Build succeeds  

---------------------------------------------------------------------

HALLUCINATION PREVENTION

Before referencing files:

Verify file existence  
Verify architecture patterns  
Verify APIs from code  
Verify types  

If uncertain request clarification.

---------------------------------------------------------------------

LEARNING SYSTEM

When patterns are repeatedly observed:

Update architecture documentation.

Examples:

new service pattern  
new component pattern  
new API structure  

Architecture documentation must evolve with the repository.

---------------------------------------------------------------------

FINAL UPGRADE — CONTEXT COMPRESSION

Large repositories contain too many documentation files to load simultaneously.

Prioritize loading context in this order:

1 code-map.md  
2 feature-boundaries.md  
3 relevant file-index docs  
4 architecture docs  
5 debugging docs  

Only load minimal required context.

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