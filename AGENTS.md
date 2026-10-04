# AGENTS.md — sanitaer-heizungstechnik-ahrens.de

Static single-page website for Thorsten Ahrens Sanitär- und Heizungstechnik, a plumbing and heating business in Kisdorf; audience: prospective customers.

Prozessstand: tide 0.4.4 (2026-10-04)
Sicherheitsstufe: 1 — public info page without login, forms or user data; contact only via `tel:` and `mailto:`.

## Mandatory rules

- Antworten im Chat: kurz und scanbar, Ergebnis oder nächste Handlung zuerst
  (Details: Skill `tide:klartext`).
- Texte für Menschen — Doku, PRs, Commits, Backlog: Antwort zuerst, Struktur
  statt Prosa, nur was der Leser braucht (Details: Skill `tide:leserfreundlich`).
- Sobald du etwas beantwortet hast, behandle diese Antwort als erledigt. Richte
  dein Nachdenken in späteren Beiträgen darauf, was die Person jetzt fragt, und
  gehe frühere Antworten nicht erneut durch, es sei denn, die Person fragt danach
  oder weist auf ein Problem damit hin, oder du selbst einen Fehler bemerkst.
- Lege bei der Ausführung einer Aufgabe zuerst eine Aufgabenliste an und halte
  sie aktuell. Eine Anfrage ist erst erledigt, wenn alle Punkte abgearbeitet
  sind. Ausnahme: Greift ein Stopp-Kriterium, nenne den Grund zuerst und liste
  die offenen Punkte auf.
- Zeit ist wichtig. Aufgabenliste und Checks bleiben davon unberührt.
- Git und GitHub nur als tilloh-bot. Nie direkt auf `main` pushen, jede
  Änderung kommt per PR.
- Sprache: siehe Abschnitt „Language“.

## Language

| Textart | Sprache |
|---|---|
| Code, Bezeichner, Tests | Englisch |
| Code-Kommentare | Englisch |
| Commit-Messages | Englisch |
| PR-Texte | Englisch |
| Doku in `docs/` | Englisch |
| UI-Texte | Deutsch |

Die Pflichtregeln stehen immer auf Deutsch.

## Workflow

1. **Planen:** Feature im Gespräch klären, Anforderungen nach Vorlage in
   `docs/requirements/F-<nr>-<name>.md`. Erst nach Freigabe umsetzen.
2. **Umsetzen:** selbstständig bis zum PR. Nach der Freigabe nennst du Tim die
   fertige Zeile `/goal F-<nr>: alle FA umgesetzt, Checks grün, PR offen, oder
   Stopp-Grund genannt`, mit der er die Umsetzung startet.
3. **Stoppen und fragen** bei: Lücke in den Anforderungen, neuer Dependency,
   DB-Migration oder anderer Sicherheitsstufe, offener Geschmacksfrage im UI,
   Gate nicht erfüllbar, besserer Idee zum aktuellen Feature.
4. **Abschließen:** PR mit Abschluss-Übersicht (Ergebnis, Anforderungen,
   Checks, Geändert, Nächster Schritt, Beobachtungen). Beobachtungen außerhalb
   des Features mit Empfehlung nennen; nur angenommene kommen in
   `docs/backlog.md`.

## Project docs

- `index.html` — the whole site, HTML/CSS/JS inline; images in `static/images/`.
- [`docs/DESIGN.md`](docs/DESIGN.md) — Design-System. Gewinnt vor Referenzen
  und spontanen Wünschen im Chat. Neue Werte nur nach Rückfrage.
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
