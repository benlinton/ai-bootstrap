# AI Bootstrap

Add to any project to include commands for an AI-based workflow.

## Get Started
| Command | Description |
|---------|-------------|
| `/init-project` | Install dependencies, start backend and frontend servers|
| `/create-prd` | Generate Product Requirements Document from conversation |


## Core Loop: `Plan -> Implement -> Validate`
### 1) Plan
| Command | Description |
|---------|-------------|
| `/plan:prime` | Load project context and codebase understanding |
| `/plan:feature` | Create comprehensive implementation plan with codebase analysis |

### 2) Implement
| Command | Description |
|---------|-------------|
| `/implement:next-step` | Execute an implementation plan step-by-step |

### 3) Validate
| Command | Description |
|---------|-------------|
| `/validate:run-tests` | Run full validation: tests, linting, coverage, frontend build |
| `/validate:code-review` | Technical code review on changed files |
| `/validate:code-review-fix` | Fix issues found in code review |
| `/validate:execution-report` | Generate report after implementing a feature |
| `/validate:system-review` | Analyze implementation vs plan for process improvements |

### 4) Release
| Command | Description |
|---------|-------------|
| `/commit` | Create atomic commit with appropriate tag (feat, fix, docs, etc.) |
| `/github:bug_fix:rca` | Create root cause analysis document for a GitHub issue |
| `/github:bug_fix:implement-fix` | Implement fix based on RCA document |
| `/github:draft-release` | Draft the next release |
