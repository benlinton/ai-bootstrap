# Agents

## Claude Code Commands

https://code.claude.com/docs/en/skills

> Custom slash commands have been merged into skills. A file at `.claude/commands/review.md` and a skill at .`claude/skills/review/SKILL.md` both create `/review` and work the same way. Your existing `.claude/commands/` files keep working. Skills add optional features: a directory for supporting files, frontmatter to control whether you or Claude invokes them, and the ability for Claude to load them automatically when relevant.

### Setup
Setup a project and its documentation.

| Command | Description |
|---------|-------------|
| `/setup:create-prd` | Generate Product Requirements Document from conversation |
| `/setup:create-module-reference` | Generate one file per module so we can split context and load only what's relevant |
| `/setup:init-project` | Install dependencies, start backend and frontend servers|

### Core Development Loop
Create bite-sized features using the `Plan → Implement → Validate` development cycle.

| Command | Description |
|---------|-------------|
| `/plan:prime` | Load project context and codebase understanding |
| `/plan:feature` | Create comprehensive implementation plan with codebase analysis |
| &nbsp; | &nbsp; |
| `/implement:plan` | Execute an implementation plan step-by-step |
| &nbsp; | &nbsp; |
| `/validate:run-tests` | Run full validation: tests, linting, coverage, frontend build |
| `/validate:code-review` | Technical code review on changed files |
| `/validate:code-review-fix` | Fix issues found in code review |
| `/validate:execution-report` | Generate report after implementing a feature |
| `/validate:system-review` | Analyze implementation vs plan for process improvements |

### Improve
Evolve this project's process upon completing each feature.

| Command | Description |
|---------|-------------|
| `/improve:agent-workflow` | Improve this project's agent workflow |

### Commit
Fix, release, and deploy the codebase.

| Command | Description |
|---------|-------------|
| `/commit` | Create atomic commit with appropriate tag (feat, fix, docs, etc.) |
| `/github:bug-fix-rca` | Create root cause analysis document for a GitHub issue |
| `/github:bug-fix-implement-fix` | Implement fix based on RCA document |
| `/github:draft-release` | Draft the next release |
