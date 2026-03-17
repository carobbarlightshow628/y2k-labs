# PO Skills - Product Owner Automation for Azure DevOps

This project provides 4 agent skills that automate Azure DevOps backlog management using the `az boards` CLI.

## Available Skills

### 1. azure-devops-backlog-creator
**When to use:** User provides a document (PRD, spec, feature brief, meeting notes) and asks to create work items, generate a backlog, or populate Azure DevOps.

Reads the document and creates a full hierarchy: Epics, Features, User Stories, Tasks, Bugs with parent-child links, acceptance criteria (Given/When/Then), story points (Fibonacci), priority, and session tagging for rollback. Supports Agile, Scrum, and Basic process templates.

Full execution protocol: `skills/azure-devops-backlog-creator/SKILL.md`

### 2. backlog-health-audit
**When to use:** User asks to audit, check, clean up, or review backlog quality. Phrases: "audit my backlog", "check my board", "find stale items", "grooming prep".

Scans the existing backlog and generates a health report (0-100 score). Detects stories without acceptance criteria, bugs without repro steps, orphaned tasks, stale items (30+ days), duplicates, unbalanced sprints. Read-only by default; `--fix` auto-fixes LOW severity only.

Full execution protocol: `skills/backlog-health-audit/SKILL.md`

### 3. sprint-planner
**When to use:** User asks to plan sprints, assign items to iterations, balance sprint load, or check capacity. Phrases: "plan the next sprint", "distribute the backlog", "velocity planning".

Analyzes the backlog and suggests optimal sprint assignments based on velocity (auto-calculated from last 3 sprints), priority ordering, dependency awareness, and load balancing (targets 80-90% capacity).

Full execution protocol: `skills/sprint-planner/SKILL.md`

### 4. work-item-templates
**When to use:** User asks to scaffold or generate standard work items for common patterns (API endpoint, CRUD feature, database migration, CI/CD pipeline, etc.).

Generates pre-built hierarchies from 18 proven templates across backend, frontend, full-stack, DevOps, and bug-fix categories.

Full execution protocol: `skills/work-item-templates/SKILL.md`

## Prerequisites

All skills require:
1. Azure CLI installed (`az --version`)
2. Azure DevOps extension (`az extension add --name azure-devops`)
3. Authentication (`az login`)
4. Defaults configured (`az devops configure --defaults organization=https://dev.azure.com/ORG project=PROJECT`)

## Key Rules

- Never create Azure DevOps items without user approval of the plan
- Never modify or delete existing work items unless explicitly asked
- Always verify after creation with count checks and hierarchy validation
- Tag all created items with session tags for rollback support
