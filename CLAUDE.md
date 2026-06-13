# CLAUDE.md — sme-board-of-directors-skill

## What this project is
A **Claude Code skill** that convenes a "board of directors" to **advise on and critique** a proposed AI solution for a small/medium enterprise (SME). The board does **not** build or generate solutions — it interrogates a proposal from five distinct perspectives and gives feedback through interactive deliberation.

## Architecture — two compartmentalized specs
Build in order; each gets its own spec → plan → implementation cycle.

- **Spec A — The Board (personas):** five named advisory characters as standalone, independently testable content. Pure persona data; no flow logic. Lives in `skills/board-of-directors/personas/`, one file per seat.
- **Spec B — The Session Engine:** the deliberation machinery that *uses* the personas — `SKILL.md`, intake, round-table, cross-challenge rounds, user weigh-in, the **Chair** (defined here, not in A), termination, and synthesis/verdict.

Specs are written to `docs/superpowers/specs/YYYY-MM-DD-<topic>-design.md`.

## The five seats (fixed standing panel)
CEO/Strategy (Jeremias Meier) · CFO/Cost & ROI (Melanie Gabriel) · CTO/Feasibility (Marcel Lenz) · Customer/Adoption (Prof. Dr. Andréa Belliger) · Risk/Compliance (David Rosenthal).

## Conventions (non-negotiable for persona files)
- **Format exemplar:** match `~/.claude/skills/gstack/office-hours/SKILL.md` — specifically its "Six Forcing Questions" shape (**Ask / Push until you hear / Red flags**) and its Operating Principles / Response Posture sections.
- **Freeform critique:** each seat speaks in its own voice; the engine consumes prose, not structured fields.
- **Named characters with backstory**, grounded in public record, with explicit *(inferred)* flags where personality is not from a first-hand quote.
- **Swiss/EU SME default:** assume FADP + GDPR, CHF, local SME cost/labour realities; overridable at intake.
- **Portrayal note required:** every persona file MUST carry a note that it is a fictional advisory portrayal of a real public figure, not their actual statements. (Enforce-by-review; a future hook may gate this.)

## Working style (user's standing workflow)
Before producing any substantial artifact: (1) define precise success criteria up front, (2) match a concrete past/example format, (3) have a second AI check the final output (codex, or a fresh Claude subagent). Confirm criteria + exemplar with the user before producing.

## Guardrails (enforced by hooks in ~/.claude/settings.json — cannot be bypassed)
- `guard-bash.sh` (PreToolUse/Bash): blocks destructive deletion (incl. `/bin/rm`, `find -delete`, `git clean`), force-push, push to main/master, `reset --hard`/`filter-branch`, `curl|sh`, and commits containing secrets.
- `guard-write.sh` (PreToolUse/Write|Edit): blocks writes to credential/system paths (`.env`, `.ssh`, `.aws`, `/etc`, `*.pem`, `*.key`).
- Permission deny-rules are advisory only; the hooks are the real enforcement. Do not commit/push to `main` directly — use a feature branch + PR.

## Git
- Remote: `github.com/schelcoder/sme-board-of-directors-skill`. Default branch `main` (no branch protection — rely on the hook + branch+PR discipline).
