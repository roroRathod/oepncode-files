# AGENTS.md — Global Rules (Rohnit Rathod)

## Identity & Preferences
Read USER.md in this directory before every session. It defines coding style,
stack preferences, project structure, deployment rules, and interaction expectations.
Treat it as ground truth for all decisions.

## MCP Servers Available
<!-- Add new MCPs below as they are connected -->
- `github` — repo ops, PRs, issues, commits
- `google-workspace` — Gmail, Calendar, Drive, Docs
- `context7` — live documentation lookup (use before answering library/API questions)

## Plugins Active
- `context7` — always use for external lib docs before generating code

## Post-Code Checklist
After writing or modifying any code, always invoke these subagents in order:
1. `@doc-generator` — generate or update docstrings and README sections
2. `@code-reviewer` — review for style, bugs, and anti-patterns
3. `@architecture` — flag any structural or design concerns
4. `@test-writer` — write or update tests for changed code
5. `@compliance-reviewer` — check .env usage, secrets, Dockerfile rules
6. `@agent-watcher` — verify agent interactions and tool call correctness

Only skip a subagent if its scope is clearly irrelevant (e.g. no agents involved → skip agent-watcher).
Always tell the user which subagents ran and what they flagged.

## General Behaviour
- Systems-first thinking: propose architecture before writing code on non-trivial tasks
- Lead with working solution, optimize after
- Skip basics unless DB, monitoring, or explicitly asked
- No theory dumps, no generic templates, no over-engineering
- All responses: concise, structured, copy-paste ready
