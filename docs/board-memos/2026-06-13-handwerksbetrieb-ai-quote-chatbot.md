# Verwaltungsrat-Memo — KI-Chatbot mit automatischer Offert-Erstellung
**Datum:** 2026-06-13 · **Antrag:** Sollen wir den KI-Chatbot mit automatischer Offert-Erstellung bauen? · **Unternehmen:** Handwerksbetrieb (~50 Mitarbeitende), Thurgau (CH)

## Empfehlung
**Kleinere Variante umsetzen.** Nicht den vollautomatischen, verbindlichen Offert-Bot bauen. Stattdessen einen *Offert-Anfrage-Assistenten* mit Richtpreis-Vorschlag und obligatorischer manueller Freigabe: Anfragen erfassen und triagieren, einen indikativen Preis aus Vorlagen/Regeln entwerfen, KI nur für die sprachliche Beantwortung von Fragen. Erst einen Monat mit Vorlagen und manueller Prüfung testen, bevor KI-gestützte Preisfindung gebaut wird.

## Positionen des Gremiums
- **CEO / Strategie (Meier):** Nur sinnvoll, wenn nachweislich Aufträge an langsamen Offerten verloren gehen; die kleinere Variante schlägt die Vollvision. — *bedingt*
- **CFO / Kosten & ROI (Gabriel):** Bei ~30 Anfragen/Woche sind die Kosten gering; ROI entsteht nur durch eingesparte Kalkulationsstunden — die Variante zahlt sich aus, die Vollautomatik nicht. — *bedingt*
- **CTO / Machbarkeit (Lenz):** Preise aus Rechnungen sind ein Regel-/Vorlagenproblem; KI nur für Freitext. Vollständige LLM-Preisfindung ist Over-Engineering. — *dagegen (für Vollvision), dafür (für Variante)*
- **Kunde / Akzeptanz (Belliger):** Richtpreis plus „ein Mensch bestätigt" schafft Vertrauen; das Frontoffice wechselt vom Erstellen zum Prüfen — dieser Wandel ist zu begleiten. — *bedingt*
- **Risiko / Compliance (Rosenthal):** Indikativ + Haftungshinweis + manuelle Freigabe macht die Haftung beherrschbar; zwingend nötig sind ein Auftragsverarbeitungsvertrag und CH/EU-Datenhaltung für das Modell. — *bedingt*

## Wesentliche Risiken & Bedingungen
- Offerten bleiben **indikativ** (Richtpreis), niemals automatisch verbindlich; Mitarbeitende bestätigen jede Offerte.
- **FADP/DSGVO:** Rechnungsdaten sind Personendaten — Rechtsgrundlage klären, Auftragsverarbeitungsvertrag abschliessen, CH/EU-Datenresidenz sicherstellen.
- Preislogik über **Regeln/Vorlagen**, nicht über ein generatives Modell; KI nur für Sprache.
- ROI hängt an **eingesparten Kalkulationsstunden** — vor dem Bau messen.

## Offene Fragen
- Gibt es belastbare Nachweise für verlorene Aufträge wegen langsamer Offerten?
- Wer im Frontoffice übernimmt Freigabe und Pflege der Preisvorlagen?
- Genügt die Datenqualität der Rechnungen für verlässliche Richtpreise?

---

# Board Memo — AI Chatbot with Automatic Quote Generation
**Date:** 2026-06-13 · **Decision requested:** Should we build the AI chatbot with automatic quote generation? · **Business:** Trades/construction firm (~50 staff), Thurgau (CH)

## Recommendation
**Build a smaller wedge.** Do not build the fully automatic, binding auto-quote bot. Instead build a *quote-request assistant* with an indicative price suggestion and mandatory human sign-off: capture and triage requests, draft an indicative number from templates/rules, use AI only for answering free-text questions. Test it for one month with templates and human review before building any AI-driven pricing.

## Board positions
- **CEO / Strategy (Meier):** Only worth it with evidence that jobs are lost to slow quoting; the wedge beats the full vision. — *conditional*
- **CFO / Cost & ROI (Gabriel):** At ~30 requests/week cost is trivial; ROI comes only from saved estimator hours — the wedge pays back, full automation doesn't. — *conditional*
- **CTO / Feasibility (Lenz):** Pricing from invoices is a rules/template problem; AI only for free text. Full LLM pricing is over-engineering. — *oppose (full vision), support (wedge)*
- **Customer / Adoption (Belliger):** An indicative price plus "a person will confirm" builds trust; the front desk shifts from creating to reviewing — manage that change. — *conditional*
- **Risk / Compliance (Rosenthal):** Indicative + disclaimer + human sign-off makes liability manageable; a data-processing agreement and CH/EU data residency for the model are mandatory. — *conditional*

## Key risks & conditions
- Quotes stay **indicative**, never automatically binding; staff confirm every quote.
- **FADP/GDPR:** invoice data is personal data — establish the legal basis, sign a data-processing agreement, ensure CH/EU data residency.
- Pricing logic via **rules/templates**, not a generative model; AI for language only.
- ROI hinges on **saved estimator hours** — measure before building.

## Open questions
- Is there solid evidence of jobs lost to slow quoting?
- Who in the front office owns sign-off and maintenance of the price templates?
- Is the invoice data quality good enough for reliable indicative prices?
