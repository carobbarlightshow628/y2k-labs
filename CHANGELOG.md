# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned
- `backlog-health-audit` skill — scan existing backlog for missing acceptance criteria, orphans, duplicates, and stale items
- `sprint-planner` skill — auto-assign backlog items to sprints based on velocity and dependencies
- `work-item-templates` skill — pre-built templates for common patterns (API endpoint, frontend page, DB migration)
- Multi-runtime support (Cursor, Copilot, Windsurf native configs)

## [1.1.0] - 2026-03-17

### Added
- Plan review options: show in chat, save to `.md` file, or both
- `--output=<file>` flag to save backlog plan to markdown before creating in Azure DevOps
- User is asked how they want to review the plan before any items are created

### Changed
- Phase 2 (Plan) now has 3 review modes instead of chat-only display
- How it works flow updated from 6 steps to 7 (added REVIEW step)

## [1.0.0] - 2026-03-17

### Added
- `azure-devops-backlog-creator` skill — reads documents and creates full Azure DevOps backlog hierarchy
- Support for Epics, Features, User Stories, Tasks, and Bugs with parent-child relationships
- Acceptance criteria, story points, priority, and tags for all work items
- Process template support: Agile, Scrum, and Basic
- Session tagging (`backlog-creator-YYYYMMDD-HHMMSS`) for bulk querying and rollback
- `--dry-run` flag for previewing without creating
- `--org`, `--project`, `--iteration`, `--area-path`, `--assign-to`, `--tags`, `--priority` arguments
- `scripts/validate-prerequisites.sh` for checking Azure CLI setup
- `scripts/rollback.sh` for undoing a session by tag
- `references/REFERENCE.md` with complete Azure DevOps CLI field reference
- `examples/sample-prd.md` and `examples/sample-output.md`
- `npx po-skills` installer with GUSY2K ASCII banner in #00F0A0
- Multi-runtime installer support (Claude Code, Cursor, Copilot, Windsurf)
- `.claude-plugin/marketplace.json` for plugin discovery
- Apache 2.0 license

[Unreleased]: https://github.com/GusY2K/po-skills/compare/v1.1.0...HEAD
[1.1.0]: https://github.com/GusY2K/po-skills/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/GusY2K/po-skills/releases/tag/v1.0.0
