# PO Skills - Product Owner Automation for Azure DevOps

This project provides 4 agent skills that automate Azure DevOps backlog management using the `az boards` CLI.

## Skills

### 1. azure-devops-backlog-creator
Reads any document (PRD, spec, feature brief) and creates a complete Azure DevOps backlog hierarchy: Epics, Features, User Stories, Tasks, Bugs with parent-child links, acceptance criteria, story points, and tags. Always shows a plan for approval before creating items. Supports Agile, Scrum, and Basic process templates.

- Full protocol: `skills/azure-devops-backlog-creator/SKILL.md`
- Usage: provide a document path and ask to "create backlog", "generate work items", or "populate Azure DevOps"

### 2. backlog-health-audit
Scans an existing Azure DevOps backlog and generates a health report (0-100 score). Detects: stories without acceptance criteria, bugs without repro steps, orphaned tasks, stale items (30+ days), duplicates, unbalanced sprints. Read-only by default.

- Full protocol: `skills/backlog-health-audit/SKILL.md`
- Usage: "audit my backlog", "check board health", "find stale items"

### 3. sprint-planner
Suggests optimal sprint assignments based on team velocity (auto-calculated from last 3 sprints), priority ordering, dependency awareness, and load balancing. Can create iterations and move items after approval.

- Full protocol: `skills/sprint-planner/SKILL.md`
- Usage: "plan the next sprint", "distribute backlog across sprints", "velocity planning"

### 4. work-item-templates
Generates standardized work item hierarchies from 18 proven templates: api-endpoint, crud-feature, database-migration, auth-flow, cicd-pipeline, microservice, frontend-page, dashboard, bug-fix, and more.

- Full protocol: `skills/work-item-templates/SKILL.md`
- Usage: "create API endpoint template", "scaffold CRUD feature", "generate migration tasks"

## Prerequisites

All skills require Azure CLI with the `azure-devops` extension, authenticated access (`az login`), and configured defaults (`az devops configure --defaults organization=https://dev.azure.com/ORG project=PROJECT`).

## Key Rules

1. Never create Azure DevOps items without showing the plan and getting user approval first
2. Never modify or delete existing work items unless explicitly asked
3. Always verify after creation with count checks and hierarchy validation
4. Tag all created items with session tags (`backlog-creator-YYYYMMDD-HHMMSS`) for rollback
