# Prelegal

Prelegal is a SaaS product that lets users draft legal agreements through an AI chat interface. The AI helps establish which document a user needs and gathers the information required to fill it in, based on a catalog of templates.

## 🚧 Status: In Progress

This project is under active development and is targeted for completion by **September 17, 2026** (one week out). The application code (backend, frontend, document templates) is being built out now — check back soon, or see open issues/PRs for current progress.

## Planned architecture

- **Backend**: FastAPI (Python), managed with `uv`, in `backend/`
- **Frontend**: in `frontend/`, statically built and served by FastAPI
- **Database**: SQLite, recreated fresh on each container start (users table with sign up/sign in)
- **Packaging**: single Docker container
- **AI**: LLM calls via LiteLLM through OpenRouter to `openrouter/openai/gpt-oss-120b` on Cerebras inference, using Structured Outputs to populate document fields
- **Documents**: 11 supported agreement types, defined in `catalog.json`

## Running the project

Once built, the project will include start/stop scripts per platform:

```bash
# Mac
scripts/start-mac.sh
scripts/stop-mac.sh

# Linux
scripts/start-linux.sh
scripts/stop-linux.sh

# Windows
scripts/start-windows.ps1
scripts/stop-windows.ps1
```

The backend will be available at `http://localhost:8000`.

## Contributing / development process

See `CLAUDE.md` for the full project spec, coding conventions, and development process.
