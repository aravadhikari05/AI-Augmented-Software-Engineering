# AGENTS.md

Guidance for AI coding agents (Claude Code, Codex, Antigravity, Copilot, etc.) working in this repository.

## What this repo is

Course materials for the **AI-Augmented Software Engineering** lecture series. It is mostly Markdown and PDFs, plus small starter apps inside some assignments. There is no top-level build, test suite, or package manifest.

## Layout

```
lectures/<NN-slug>/      # Lecture README + slide PDFs, one folder per week
assignments/<NN-slug>/   # assignment.md, optionally a starter/ app
resources/<NN-slug>/     # README.md + papers-to-read.md per week
resources/midterm-study-guide/   # Per-topic study guide files
```

- Week folders use a two-digit prefix and kebab-case slug (e.g. `06-agentic-code-review-and-testing`). Keep the same slug across `lectures/`, `assignments/`, and `resources/`.
- The lecture list in the top-level `README.md` must stay in sync with the `lectures/` folders.

## Working with content

- Write in GitHub-flavored Markdown. Use relative links between files and check they resolve.
- Do not edit or regenerate the slide PDFs; they are authored outside this repo.
- Keep assignment specs (`assignment.md`) stable once published — prefer adding clarifications over rewriting requirements.
- New readings go in the matching week's `resources/<NN-slug>/papers-to-read.md`.

## Starter apps

Some assignments ship a runnable `starter/` (Python / FastAPI). Run commands from inside that `starter/` folder:

```bash
pip install -r requirements.txt
pytest
uvicorn main:app --reload
```

- Use a virtualenv (`.venv/`, already gitignored).
- Never commit local databases (`*.db`), `.env`, or `__pycache__/`.
- Add or update tests alongside any behavior change.

## Git & PRs

- Branch off `main`; do not commit directly to it.
- Keep commits small and focused, with imperative-mood messages (e.g. "Add week 7 reading list").
- PR descriptions should state the problem, the approach, and how it was tested.
- PRs may be reviewed by an AI reviewer (CodeRabbit by default); address or respond to its comments.

## Don'ts

- Don't commit secrets, API keys, or personal data.
- Don't add large binaries other than lecture PDFs.
- Don't reorganize the folder structure without updating every README that links into it.
