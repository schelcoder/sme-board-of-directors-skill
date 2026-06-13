# Spec B — The Session Engine

**Project:** SME Board of Directors skill · **Date:** 2026-06-13 · **Status:** Built, pending second-AI check + user review
**Scope:** Spec B only — the engine that runs a board session using the Spec A personas. Personas themselves are Spec A (done).

## Purpose
`skills/board-of-directors/SKILL.md` is the skill entry point. It loads the five personas and runs an interactive board session over a proposed AI solution for an SME, ending in a bilingual board memo. The engine is the "how the meeting runs"; the personas are the "who."

## Decisions locked (2026-06-13 brainstorm)
- **Arc:** Intake → Round-table → Deliberation → Verdict.
- **Intake:** light structured — free-text proposal + 3 fields (business sector/size; region, Swiss/EU default; the decision being asked).
- **Round-table:** each of the five seats gives an opening read, in voice.
- **Deliberation:** seats challenge each other AND the board puts open questions to the user between rounds; the user's answers feed the next round.
- **Convergence:** a full round that surfaces no materially new concern; hard backstop cap of 4 rounds; user can force the verdict at any time.
- **Chair:** a neutral, unnamed facilitator — runs phases, detects convergence, synthesizes an unbiased verdict. No persona of its own.
- **Verdict:** a written board-memo file, **bilingual** — German first, then English.
- **Working language:** deliberation runs in the user's language; the memo is DE + EN.

## Format exemplar
The phased `SKILL.md` from `~/.claude/skills/gstack/office-hours/SKILL.md` (Phase 1 → 2 → … → synthesis + saved doc). Mirror the phase structure and the "STOP after each question, wait for response" discipline. Do **not** copy gstack-specific preamble/telemetry.

## Deliverables
```
skills/board-of-directors/SKILL.md          # the engine (this spec)
skills/board-of-directors/personas/ …       # Spec A (done) — loaded, not restated
docs/board-memos/YYYY-MM-DD-<slug>.md        # output, one bilingual memo per session
```

## Interface to Spec A
The engine `Read`s each persona file and has that seat critique in voice. It must not duplicate persona content — single source of truth stays in `personas/`. Contract consumed: stable seat id + freeform critique in voice.

## Phase detail
1. **Intake** — capture proposal + 3 fields. Infer/confirm region default (Swiss/EU → FADP+GDPR, CHF).
2. **Round-table** — load all five personas; each gives a short opening read in voice.
3. **Deliberation loop** — repeat: seats react to each other and to the user's last answers; board surfaces open questions; user answers. Stop when a round adds nothing materially new OR cap (4) reached OR user forces verdict.
4. **Verdict** — Chair synthesizes: recommendation (build / don't / build a smaller wedge), one-line position per seat, key risks/conditions, open questions. Write bilingual memo (DE then EN) to `docs/board-memos/`.

## Success criteria (for second-AI check)
1. Faithful phase flow with STOP-and-wait discipline.
2. Loads and uses all five personas, each in its own voice.
3. Deliberation genuinely bounded (convergence + cap 4 + user override) — no runaway, no premature cutoff.
4. Intake minimal but sufficient to ground the seats.
5. Verdict memo complete and genuinely bilingual (real German, not English with stray German).
6. No Spec A content duplicated — engine references personas.
7. Clean skill: valid frontmatter, sensible allowed-tools, no gstack-specific cruft.
