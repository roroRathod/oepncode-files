# USER.md — Rohnit Rathod

## Mindset
- Systems-first builder: Architecture → Components → Execution
- Automation, orchestration, scalability over one-off scripts
- Practical implementation > theory

## Tech Profile
- **Strong:** System design, backend workflows, agentic AI, dev tooling
- **Integrations:** Google Workspace APIs, GitHub workflows, Microsoft Teams, MCP servers

## Backend
- Python with **FastAPI** for all fresh projects
- Exception: if existing codebase uses Flask, continue with Flask
- Default libs: `langchain`, `langgraph`, `pydantic`
- Always use OpenAI-compatible API URL + API key — never hardcode provider-specific SDKs

## Project Structure (FastAPI)
```
/agents
/services
/utils
/config
/routes
main.py
.env
Dockerfile
```
- Flat, logical, minimal nesting — never deep hierarchies
- File-level modularity: `calendar_service.py`, `teams_service.py`, `agent_runner.py`

## Coding Style
- Functions: single-purpose, action-named — `create_calendar_event()`, `send_teams_message()`
- Flow: linear `await`-style, sequential steps — readable over clever
- Error handling: catch at boundaries, log useful context, no over-engineered error classes
- Logging: debug-oriented `print()` or `logging.info()` to trace flow fast
- Config: always via `.env` + explicit `os.getenv("KEY")` — no magic values
- Conditionals: `if not user: return` over dense one-liners
- Code answers: *"If this breaks at 2AM, will I understand it in 30 seconds?"*

## Frontend
- Plain HTML + CSS + JS only — no frameworks
- Strict file separation: `index.html`, `style.css`, `script.js`
- No inline CSS or JS in HTML, ever

## Database
- **Always ask** which DB to use — varies per project
- Teaching mindset: explain what the DB does, why it fits, how to query/interpret it

## Monitoring
- **Always ask** which monitoring approach to use — user is exploring and learning
- After user confirms the approach, proceed and explain what each tool does and how to read its output

## Deployment
- Always write a `Dockerfile` — never `docker-compose.yml` or any YAML orchestration file
- Always create a `.env` file for all env vars
- Mirror the same vars as `ENV` in the `Dockerfile` — keep both in sync

## GitHub
- Username: `roroRathod`
- Email: `rohnitrathod12@gmail.com`
- Ask for PAT or password when needed — never assume

## Interaction Rules
- Assume high technical capability — skip basics (except DB and monitoring)
- Lead with working solution, optimize after
- Prefer: CLI commands, config snippets, real examples
- Avoid: theory dumps, vague steps, over-engineering, generic templates
