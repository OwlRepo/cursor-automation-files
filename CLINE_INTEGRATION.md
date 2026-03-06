# Cline Autonomous AI Development System Bootstrap (Final Corrected)

BOOTSTRAP NOTICE

This file is a one-time bootstrap specification used to generate the full AI development support system for Cline in VS Code.

After generation, the repository will contain an AI knowledge system allowing Cline to understand the architecture, navigate safely, and implement changes with minimal hallucinations.

The generated system must allow Cline to automatically determine which documentation to load without requiring the user to reference specific files.

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

EXECUTION PLAN CONTRACT

Before implementing any change create a plan including:

Exact files  
Exact code sections  
Reasons for changes  
Before/after snippets  
Verification steps  

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