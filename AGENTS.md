# AGENTS.md

## Cursor Cloud specific instructions

This repository is a **GitHub profile README** repo (`jackgong666/jackgong666`). It contains only `README.md`, which renders on the owner's GitHub profile page. There is **no application code, package manifest, lockfile, build system, test suite, or backend/frontend service** in this repo.

### What "developing" means here
- The only artifact is `README.md`. Editing it changes how the GitHub profile page renders.
- There is nothing to install for the repo itself and nothing to build/lint/test in a conventional sense.

### Previewing the profile locally
- Use [`grip`](https://github.com/joeyespo/grip) to render `README.md` exactly as GitHub does (it calls the GitHub Markdown API):
  - `python3 -m grip README.md 0.0.0.0:<port>` then open `http://localhost:<port>`.
- `grip` is a personal dev/preview tool, not a repo dependency. It renders via the GitHub API, so it needs network egress to `api.github.com` and is subject to unauthenticated rate limits (set `GRIP_ACCESS_TOKEN` for a higher limit if needed).
- Offline fallback: `python3 -m markdown README.md > /tmp/readme.html` renders locally without the GitHub API (styling will differ from GitHub).
