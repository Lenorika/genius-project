## Short project orientation

This repository is a very small static web project. The codebase currently contains a single HTML entry file and a Prettier configuration:

- `index.html` — the full site/content (single-page). Edit this file for content or markup changes.
- `prettierrc.json` — formatting rules used across the project. Follow its settings when changing whitespace/formatting.

There is no package.json, build system, or test runner in the repository as-is. Treat changes as direct edits to the static site.

## Big-picture architecture (what matters)

- Single-page static site. All content currently lives in `index.html`.
- No server-side code or build pipeline is present. Any new JS/CSS you add should be referenced directly from `index.html`.

## Developer workflows (what an AI agent should do)

- Editing content: update `index.html` and keep changes small and atomic (one user-visible change per patch).
- Formatting: apply Prettier settings from `prettierrc.json`. Key rules:
  - printWidth: 80
  - tabWidth: 2
  - singleQuote: true, semi: true, trailingComma: "all"

- Local verification: since there's no build step, preview changes by opening `index.html` in a browser or by running a lightweight static server. Example (PowerShell):

```pwsh
# from repository root - start a simple static server (PowerShell / Python 3)
python -m http.server 8000
# then open http://localhost:8000/index.html in your browser
```

## Patterns & conventions discovered in this repo

- Minimal markup: the current `index.html` uses plain HTML5 with a UTF-8 charset and viewport meta tag.
- Keep changes consistent with Prettier settings. There is no linter or additional config to enforce rules.

## Integration points & external dependencies

- None presently. If you add dependencies (npm, toolchain), also add a `package.json` and document install/run steps in the README.

## Examples for common edits (concrete)

- Change the page title: update the `<title>` element in `index.html`.
- Update the body text: edit the HTML within `<body>`; the example greeting currently is `Hello,team 123!`.

## Safety & scope for AI agents

- Only modify files tracked in the repository. Don’t create sprawling scaffolding unless requested.
- If adding a build system or toolchain, include minimal manifest files (`package.json` or similar) and update this instructions file to reflect the new developer workflow.

## When to ask the human

- If a change requires adding a dependency, build step, or CI integration, ask the repo owner for permission and preferred tooling.
- If you need to reorganize the project (split assets into `css/` or `js/`), propose a short plan and wait for approval.

---
If anything here is unclear or you want more detail (for example, preferred file layout for added assets or a recommended local dev server), tell me and I'll update this file.
