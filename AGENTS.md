# AGENTS.md — sanitaer-heizungstechnik-ahrens.de

Static single-page website for Thorsten Ahrens Sanitär- und Heizungstechnik, a plumbing and heating business in Kisdorf; audience: prospective customers.

Prozessstand: tide 0.7.0 (2026-10-06)
Sicherheitsstufe: 1 — public info page without login, forms or user data; contact only via `tel:` and `mailto:`.

This file is the project's contract: it applies to everyone working here,
human or AI. How the AI works with Tim comes with the tide plugin; without
tide, only this file applies.

## Rules

- Every change comes as a PR, never directly to `main`. A PR is merged only
  when the `gate` check is green and Tim has approved.
- The design lives in `index.html` (inline CSS) until `docs/DESIGN.md` exists.
  New design values (colour, font size) only after asking.
- Dependencies: as few as possible; every new one is justified in the PR.
- Tests: an E2E smoke test that the page loads (still open); no logic, so no
  unit tests.
- Secrets never go into the repo; `.env` files stay local.

## Language

| Textart | Sprache |
|---|---|
| Code, Bezeichner, Tests | Englisch |
| Code-Kommentare | Englisch |
| Commit-Messages | Englisch |
| PR-Texte | Englisch |
| Doku in `docs/` | Englisch |
| UI-Texte | Deutsch |

## Requirements

Features are described before implementation in
`docs/requirements/F-<nr>-<name>.md`, from the template `F-000-template.md`.
After implementation the document is frozen; it gets the line
`Umgesetzt: PR #<nr> (<date>)`. If a later feature changes the behaviour, the
new document names it: `Ersetzt: F-<nr> FA-<n>`.

## Project docs

- `index.html` — the whole site, HTML/CSS/JS inline; images in `static/images/`.
- `docs/DESIGN.md` — design system, still open (`/tide:design`).
- [`docs/requirements/`](docs/requirements/) — Anforderungen `F-<nr>`,
  eingefroren nach Freigabe.
- [`docs/features/`](docs/features/) — Erklärungen, die mit dem Code aktuell
  bleiben.
- [`docs/backlog.md`](docs/backlog.md) — angenommene Beobachtungen.
- [`docs/betrieb.md`](docs/betrieb.md) — wo und wie das Projekt läuft,
  Deploy, Überwachung, Backup, Orte der Secrets.

## Commands

| Zweck | Befehl |
|---|---|
| Abhängigkeiten installieren | `pnpm install` |
| Entwicklungsserver | `python3 -m http.server 8080` → <http://localhost:8080> |
| Lint (html-validate) | `pnpm lint` |

## Deliberate deviations

Vom Prozess bewusst abweichend entschieden, eine Zeile pro Punkt mit Grund.
Der Bootstrap lässt diese Punkte in Ruhe.

- No `check`, `test` or `build` scripts: static site without build step or TypeScript; CI runs `lint` only (2026-10-04).
