# Board Personas

The five standing seats of the SME board of directors. Each file is a standalone, independently testable persona definition. The deliberation engine, the Chair, intake, and synthesis live in Spec B (the skill's `SKILL.md`), not here.

| Seat | File | Character |
|---|---|---|
| CEO / Strategy | `ceo-meier.md` | Jeremias Meier |
| CFO / Cost & ROI | `cfo-gabriel.md` | Melanie Gabriel |
| CTO / Feasibility | `cto-lenz.md` | Marcel Lenz |
| Customer / Adoption | `customer-belliger.md` | Prof. Dr. Andréa Belliger |
| Risk / Compliance | `risk-rosenthal.md` | David Rosenthal |

## Persona template
Every file follows this shape (format exemplar: `~/.claude/skills/gstack/office-hours/SKILL.md`):

1. **Seat & name**
2. **Essence** — one line
3. **Background** — grounded in public record, with source pointers
4. **Personality & voice** — with explicit *(inferred)* flags where not from a first-hand quote
5. **Mandate** — what this seat owns
6. **Signature questions** — each as **Ask / Push until you hear / Red flags**
7. **Their bar** — what earns a yes vs. what trips a red flag
8. **Voice guide** — tone + 2–3 sample phrasings
9. **Portrayal note** — fictional advisory portrayal of a real public figure

## Authoring rules
- Default SME context: Swiss/EU small business (FADP + GDPR, CHF, local cost/labour realities), overridable at intake.
- Keep each file to its own lens; do not duplicate another seat's mandate.
- Never present an inferred trait as a verbatim quote.
- Every file must carry the portrayal note.

## Smoke check (run per persona, no framework needed)
1. Load one persona file as context.
2. Feed the **sample proposal** below.
3. Confirm the response (a) raises that seat's signature concerns and (b) reads in the character's voice.

**Pass/fail bar:** FAIL if the persona's response could equally have come from another seat — each answer must raise at least one concern no other seat would raise. Cross-check the two known-adjacent borders specifically: **Meier vs Belliger** (does the customer *want* it [CEO] vs will they *adopt/rely on* it [Customer]) and **Meier vs Gabriel** (strategic go/no-go case [CEO] vs run-cost, pricing, and margin [CFO]).

**Sample proposal:** *"A 50-person Handwerksbetrieb (trades/construction firm) in Thurgau wants to deploy an AI chatbot on its website that answers customer questions and generates price quotes for jobs automatically, pulling from past invoices."*

Expected, roughly: Meier → is there real customer demand / unit economics; Gabriel → run-cost vs. price, ROI; Lenz → does it need AI, reliability on a slow connection, who maintains it; Belliger → will the Meister and customers trust auto-quotes; Rosenthal → FADP exposure of invoice data, liability for a wrong quote, with structural fixes.
