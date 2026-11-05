# CampusConnect Static Wireframe

A minimal, browser-openable visual baseline for Session 3: **Building a Real-World Application Using AI-Assisted Development Tools**.

This folder intentionally contains a static wireframe, not a completed application. It gives students a starting point for understanding the CampusConnect page structure before they use AI coding tools to implement the real functionality.

## What this baseline includes

- Home page
- Events page
- Static registration form
- Static admin dashboard
- Shared grayscale stylesheet
- Session example events
- Empty registration and participant states

## How to open

Open the home page directly in a browser:

```bash
open starter-app/index.html
```

Or double-click `starter-app/index.html`.

No installation, build step, server, Python environment or dependencies are required.

## What is intentionally missing

- Form validation
- Saving registrations
- Duplicate registration prevention
- Updating admin statistics
- Adding and deleting events
- localStorage, Flask, SQLite and authentication
- Any JavaScript behavior

## Requirements

None. There is no `requirements.txt` because this baseline is pure HTML/CSS and has no Python or Node dependencies.

If students later implement backend persistence with Flask and SQLite, any Python dependencies should be recorded in a `requirements.txt` at that stage (for example, `Flask`). The wireframe itself does not need one.

## Suggested student workflow

1. Open and inspect the wireframe.
2. Use an AI coding agent to explain the current structure.
3. Decide whether to keep the static baseline or rebuild selected pieces.
4. Add validation and registration behavior.
5. Add persistence (localStorage or Flask + SQLite).
6. Update the admin dashboard from stored data.
7. Test registration and duplicate prevention.
8. Debug with the AI coding agent while reviewing every change.
