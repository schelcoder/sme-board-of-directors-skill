# Spec A — The Board (Personas)

**Project:** SME Board of Directors skill · **Date:** 2026-06-13 · **Status:** Built, pending second-AI check + user review
**Scope:** Spec A only — the five advisory personas as standalone content. Engine, Chair, intake, synthesis are Spec B.

## Purpose
A Claude Code skill that convenes a board to **advise on / critique** a proposed AI solution for an SME (feedback, not code). Spec A is the "who" — five named characters. Spec B is the "how the meeting runs."

**Success test:** each persona file, loaded alone, makes Claude critique a sample SME AI proposal (a) raising that seat's signature concerns and (b) sounding like the character.

## Success criteria (a result is "great" only if all pass)
1. **Format fidelity** — every file matches the template below (office-hours Ask/Push/Red-flags shape).
2. **Distinctiveness (blind test)** — an unlabeled critique is attributable to the right seat; no two seats raise the same concern.
3. **Mandate coverage** — each seat fully owns its lens; no gaps, no overlap.
4. **Voice authenticity** — reads like the real person; 2–3 sample phrasings per file.
5. **Grounding & honesty** — traits trace to sourced material; inferred traits flagged; first-hand quotes only where real.
6. **Swiss/EU default** — FADP+GDPR, CHF, local SME realities; overridable at intake.
7. **Portrayal safety** — each file carries the portrayal note.
8. **Independently testable** — smoke check in `personas/README.md` passes.
9. **Clean Spec B interface** — stable id/seat, freeform output, no engine logic.

## Decisions locked (2026-06-13 brainstorm)
Skill (not app); advise/review; fixed 5-seat panel; interactive deliberation (engine = Spec B); two specs A→B; freeform critique in voice; Swiss/EU default; named characters with backstory; Chair in Spec B; real names + portrayal note.

## Deliverables (this spec)
```
skills/board-of-directors/personas/
  README.md            # template, authoring rules, smoke-check + sample proposal
  ceo-meier.md         # CEO / Strategy
  cfo-gabriel.md       # CFO / Cost & ROI
  cto-lenz.md          # CTO / Feasibility
  customer-belliger.md # Customer / Adoption
  risk-rosenthal.md    # Risk / Compliance
```
`SKILL.md` (entry point), the Chair, and intake/synthesis are Spec B.

## Per-persona template
`Seat & name` → `Essence` → `Background (sourced)` → `Personality & voice (inferred flags)` → `Mandate` → `Signature questions` (each: **Ask / Push until you hear / Red flags**) → `Their bar` → `Voice guide (sample phrasings)` → `Portrayal note`.

## Interface to Spec B
Each persona exposes a stable id/seat and a loadable definition; when invoked with a proposal it produces freeform critique in voice. The engine owns ordering, Chair, rounds, user weigh-in, termination, synthesis.

## Verification
- Manual smoke check per persona (see `personas/README.md`).
- Second-AI check (codex, fallback Claude subagent) scoring the five files against the criteria above.
