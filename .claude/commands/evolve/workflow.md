---
description: Evolve our agent command workflow
argument-hint: [feature-id]
---

Given  `.agents/system-reviews/[feature-id]-review.md` I want to make the recommended improvements.
I want you to go into the rules, read all of the commands we used here, and I want you
to figure out what we could imporove in our workflow process so these issues don't happen again.

# Implement Fix: GitHub Issue #$ARGUMENTS

## Prerequisites

**This command implements fixes for GitHub issues based on RCA documents:**
- Working in a local Git repository with GitHub origin
- RCA document exists at `docs/rca/issue-$ARGUMENTS.md`
- GitHub CLI installed and authenticated (optional, for status updates)

## System Review Document to Reference

Read system review: `.agents/system-reviews/[feature-id]-review.md`

## Implementation Instructions

### 1. Read and understand System Review

- Read the ENTIRE System Review document thoroughly
- Remember any referenced documents
- Review what did not work well

### 2. Understand our current workflow

- Review global rules document `/.agents/GLOBAL-RULES.md` 
- Review product requirement document `/.agents/PRD.md` 
- Review any relevant reference documents `/.agents/reference/` 
- Review used project AI agent commands `/.claude/commands/`
- Review any documents referenced by the system review document

### 3. Propose a solution

Propose what could change in this project so these issues don't happen again.
