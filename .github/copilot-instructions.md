## Repository overview

This repository is a personal portfolio that collects small projects across multiple languages (C, Java, Python, HTML/CSS/JavaScript). The only guaranteed file at the moment is `README.md` which states the intent: a collection of projects organized by language.

When contributing as an AI coding agent, assume each project will live in its own top-level folder (e.g. `c/`, `java/`, `python/`, `web/` or `projects/<name>/`). Always verify before making assumptions by searching the repository for build files described below.

## Quick actionable rules for agents

- Start by opening `README.md` (root) to confirm the owner's stated intent and any manual notes.
- Search for language-specific build or metadata files before editing a project folder:
  - C: `Makefile`, `CMakeLists.txt`
  - Java: `pom.xml`, `build.gradle`
  - Python: `pyproject.toml`, `requirements.txt`, `setup.py`
  - Web/JS: `package.json`, `vite.config.js`, `index.html`
- If you add or modify code that requires a new build step, include a minimal README inside that project directory describing how to build/run on Windows PowerShell (the user's default shell).

## What to change vs. what to ask

- Safe autonomous edits: small bug fixes, formatting, README clarifications inside a project, or adding a short example runner (<= 50 lines) that does not change project structure.
- Ask the user before: moving large directories, deleting projects, adding CI, or migrating build systems.

## Patterns & conventions to follow

- Project layout: prefer a self-contained folder containing source, a short README, and a single build/run script (Makefile, build script, or `run.ps1`). Example: `python/project-name/README.md` and `python/project-name/run.ps1`.
- Cross-language examples should not mix build systems at top-level; keep language-specific tooling inside the project folder.
- Use Windows PowerShell-friendly commands in added run scripts (use `.
un.ps1` or `python -m`), and include an alternate POSIX command in parentheses when relevant.

## Integration points & external dependencies

- Do not assume any external services are configured. If a project uses external APIs or package registries, add a short note in that project's README listing required credentials or package sources.

## Minimal 'contract' for changes from an AI

1. Inputs: the folder for a single project and any detected build files.
2. Outputs: code changes limited to that project, updated project README describing build/run steps.
3. Error modes: if builds fail locally, add a clear note in the project README describing the failure and leave the code untouched beyond a small, reversible change.

## Examples (how to find them)

- To find a C project, search for `Makefile` or files ending with `.c` in a folder named `c` or `projects/`.
- For a web project, open `index.html` or `package.json` if present and prefer adding a `web/<name>/README.md` describing `npm install` and `npm run dev` (PowerShell: `npm install; npm run dev`).

## Verification and PR notes

- When creating a PR, include: short description, which project folder was changed, how to run the changed project on Windows PowerShell, and one-line summary of tests or manual checks performed.

---
If any section is unclear or you want the agent to follow a stricter convention (naming, folder layout, or CI), tell me which convention you prefer and I will update this file.
