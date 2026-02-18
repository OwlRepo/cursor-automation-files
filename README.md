# Cursor Automation Files

Reusable master prompts and integration specs for AI-assisted development in **Cursor** and **Visual Studio Code + GitHub Copilot**. Use these files to standardize planning, implementation, and verification workflows across projects.

## What This Repository Provides

- **CURSOR_INTEGRATION.mdc** – Master prompt for Cursor AI (entry-point-first, auto-routing, `.cursor/` structure)
- **VSCODE_COPILOT_INTEGRATION.mdc** – Master prompt for VS Code + GitHub Copilot (prompt-first, plan-before-implement)
- Shared concepts: planning contract, quality gates, project detection, file specifications, maintenance triggers

Copy the relevant file into your project and reference it when starting AI-assisted workflows.

## Which File to Use

<!-- markdownlint-disable MD060 -->
| Use Case                                             | File                            |
| ---------------------------------------------------- | ------------------------------- |
| Developing in **Cursor**                             | `CURSOR_INTEGRATION.mdc`        |
| Developing in **VS Code** with **GitHub Copilot**     | `VSCODE_COPILOT_INTEGRATION.mdc` |
<!-- markdownlint-enable MD060 -->

Both files enforce the same core principles: plan before implement, fact-based planning, strict adherence to approved plans, and quality gates. The main difference is how context and rules are loaded:

- **Cursor**: Entry-point auto-loads rules and file indexes; you describe intent and the system routes automatically.
- **VS Code + Copilot**: You explicitly reference the master prompt and rules; Copilot does not auto-load context.

## Quick Start

### Cursor

1. Copy `CURSOR_INTEGRATION.mdc` to `.cursor/` in your project (or keep at root).
2. Use `@.cursor/entry-point.mdc` as the first prompt context (if you have a `.cursor/` setup).
3. Or: Reference `@CURSOR_INTEGRATION.mdc` and ask the AI to analyze the codebase and follow its specifications.

### Visual Studio Code + GitHub Copilot

1. Install [VS Code](https://code.visualstudio.com/) and the [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) extension.
2. Sign in with a GitHub account that has Copilot access.
3. Copy `VSCODE_COPILOT_INTEGRATION.mdc` to your project root or docs folder.
4. Open Copilot Chat (`Ctrl+Shift+I` / `Cmd+Shift+I`).
5. Reference the file: `@VSCODE_COPILOT_INTEGRATION.mdc`
6. Describe your task; follow the planning → implement → verify workflow.

## Recommended Workflow (Plan → Implement → Verify → Document)

Both integrations follow the same high-level workflow:

1. **Plan** – Produce an execution plan with:
   - Exact file list to update
   - Exact code sections and before/after snippets
   - Reason for each edit
   - Verification steps
   - Any doc/index update requirements

2. **Implement** – Apply edits strictly according to the approved plan. For complex changes, do it in steps.

3. **Verify** – Run quality checks (compile, lint, tests) and confirm pattern compliance.

4. **Document** – Update architecture docs, file indexes, or common-issues when applicable.

## How to Use Each Integration File

### Using CURSOR_INTEGRATION.mdc

**When to use**: You develop in Cursor and want automated AI assistance with entry-point routing, file-index discovery, and rule application.

**Steps**:

1. Copy `CURSOR_INTEGRATION.mdc` into your project (e.g. `.cursor/` or project root).
2. If you have a full `.cursor/` setup, start every new chat with `@.cursor/entry-point.mdc` as the first context.
3. If you only have the integration file, reference it explicitly: `@CURSOR_INTEGRATION.mdc`
4. Describe what you need in plain language; the system will detect intent (bug/feature/enhancement/refactor/review).
5. The AI will automatically load relevant rules, file-indexes, and architecture docs.
6. Approve the execution plan when presented, then let the AI implement, verify, and update docs.

**Example prompt**:

```text
@CURSOR_INTEGRATION.mdc

I need to add pagination to the user list component. The API returns total count and page size.
```

**Notes**: You do not need to reference command files or rules; the entry-point routes automatically. For regeneration, use: "Analyze the codebase and regenerate all `.cursor/` files according to @CURSOR_INTEGRATION.mdc".

### Using VSCODE_COPILOT_INTEGRATION.mdc

**When to use**: You develop in VS Code with GitHub Copilot and want structured planning and implementation with explicit prompt orchestration.

**Steps**:

1. Copy `VSCODE_COPILOT_INTEGRATION.mdc` into your project root or docs folder.
2. Open Copilot Chat (`Ctrl+Shift+I` / `Cmd+Shift+I`).
3. Start every new workflow by referencing the file: `@VSCODE_COPILOT_INTEGRATION.mdc`
4. Use the **Planning** phase first: ask for an execution plan with exact files, edits, and verification steps.
5. Review and approve the plan before any edits.
6. Use the **Implementation** phase: ask Copilot to apply one step at a time (or the full plan for simple changes).
7. Use the **Verification** phase: run compile, lint, and tests; confirm the changes match the plan.

**Example prompts**:

```text
@VSCODE_COPILOT_INTEGRATION.mdc

I need to add pagination to the user list component. Following the Planning Contract, produce an execution plan with exact files, before/after snippets, and verification steps.
```

```text
Here is the approved plan: [paste plan]. Implement step 1 only.
```

```text
Run verification: compile, lint, and confirm we follow project patterns.
```

**Notes**: Unlike Cursor, Copilot does not auto-load rules or file-indexes. Include relevant file paths or `@file` references when you need context. Use the prompt templates in the integration file for planning, implementation, and verification.

## File Map

```text
cursor-automation-files/
├── README.md                      # This file – onboarding and usage
├── CURSOR_INTEGRATION.mdc         # Cursor master prompt (entry-point, .cursor/ structure)
└── VSCODE_COPILOT_INTEGRATION.mdc # VS Code + Copilot master prompt (prompt-first, plan-before-implement)
```

### CURSOR_INTEGRATION.mdc

- **Audience**: Cursor users
- **Assumes**: `.cursor/` directory, entry-point, file-index, rules, commands
- **Setup**: May use `bun run scripts/setup-cursor-integration.ts` if available
- **Workflow**: Entry-point-first; auto-routing to rules and file-index

### VSCODE_COPILOT_INTEGRATION.mdc

- **Audience**: VS Code + GitHub Copilot users
- **Assumes**: VS Code, Copilot extension, explicit prompt orchestration
- **Setup**: Manual; no scripts required
- **Workflow**: Prompt-first; explicit rule and file references; plan-before-implement

## Maintenance

### When to Update Integration Files

- **New project types** – Add detection and adaptation guidance.
- **New workflow patterns** – Update planning contract or automation levels.
- **Breaking changes** – Document migration steps in the relevant file.

### When to Update Project Documentation (per integration spec)

- **New files** – Update file-index (components, hooks, routes, controllers, services, models, utils).
- **New features** – Update architecture docs (module-structure, routing, state, etc.).
- **Breaking changes** – Update overview, tech-stack, and common-issues.

See the **Update Triggers & Maintenance** section in each integration file for details.

## Cross-Project Usage

Both integration files are designed to work across project types (frontend, backend, full-stack, mobile, CLI). They include:

- Project detection (type, tech stack, monorepo)
- Adaptive file specifications (architecture, file-index, rules)
- Update triggers for documentation maintenance

Copy the relevant file into a new project and prompt the AI to analyze the codebase and adapt accordingly.

## Migration: Cursor ↔ VS Code + Copilot

If you switch editors, use the **Migration Map** in `VSCODE_COPILOT_INTEGRATION.mdc` to translate concepts:

<!-- markdownlint-disable MD060 -->
| Cursor                         | VS Code + Copilot                    |
| ------------------------------ | ------------------------------------ |
| `@.cursor/entry-point.mdc`      | `@VSCODE_COPILOT_INTEGRATION.mdc`    |
| Auto-context from file-index   | Explicit `@file` or path references  |
| Auto-routing to rules          | Explicit rule references in prompts  |
| Cursor Composer                | Copilot Chat + Inline Chat           |
<!-- markdownlint-enable MD060 -->

## License

See repository license file if present.
