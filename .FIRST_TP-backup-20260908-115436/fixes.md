# FIXES — MERIDIAN Logistique (Group 4, Translog) · FIRST_TP bundle

**Source of truth**: `ISMS module common thread.pdf` — version 2, 8 September 2026.
**Hand-in**: 17 September 2026. **Instance**: `translog-b` · scope `MERIDIAN-LOGISTIQUE`.

Three pieces are handed in: **(1)** the strategy note, 9 sub-sections, 3–5 pages of text · **(2)** the file, nine separate sessions, each containing the CISO's desk *and* the labs · **(3)** proof of state, the dated export of the instance.

> The rule that governs all of it: *sub-section n of the note makes a claim; session n of the file proves it; the export shows the object exists in the tool.* A claim with nothing behind it does not count; a piece the note never mentions is wasted work.

---

## Status board

| # | Fix | Deliverable | Points at risk | Effort | Status |
|---|---|---|---|---|---|
| **F1** | D3 is 13 pages; spec says two pages plus the export | D3 | 4 | Medium | ☐ open |
| **F2** | D3 has no **workload estimate** (required element) | D3 | 4 (shared) | Small | ☐ open |
| **F3** | D2 has no **justified top 5 critical assets** (required element) | D2 | 5 | Medium | ☐ open |
| **F4** | **ReCyF error**: written as absent from the library; the screenshot shows it present | D3 + S3-05 | Accuracy | Small | ☐ open |
| **F5** | Tool objects carry **no owner** (Authors/Status/Domain blank) | All + coefficient | Individual multiplier | Small | ☐ open |
| **F6** | The **93 / 37-8-14-34** counts have no screenshot behind them | D3 evidence | Accuracy | Small | ☐ open |
| **F7** | **CISO's desk** is group-authored and over length; spec says individual, one page | CISO's desk | 10 (coef 1) | Large | ☐ open |
| **F8** | D1 governance chart has no **frequencies** for the bodies | D1 | 4 (shared) | Small | ☐ open |
| **F9** | S1 costed roadmap must **not** be in the hand-in | D1 hygiene | 0 | Trivial | ☐ open |

Deliverables scale: D1 4 · D2 5 · D3 4 · D4 4 · D5 3 · D6 7 · D7 5 · D8 2 · D9 3 · strategy note 3 = **40 points**, converted to a mark out of 20, coefficient 4 of 10.

---

## F1 · D3 is 13 pages; the spec caps it at two

**What the spec says**

> **D3** Business case note: regulatory qualification, argued choice of framework, options set aside, mapping matrix, workload estimate. — **Two pages plus the export** · 4 points

**Where we are.** `writup/MERIDIAN-business-case-framework-selection.md` and its PDF run to 13 pages. That was built to a 9-then-13-page brief given before this spec was available. It is over-spec **as D3**.

**Why it is not wasted.** Piece 2 (the file) is free-form and explicitly wants the labs of each session. The long report belongs there, as the session-3 backing that proves the two-page note's claims.

**Done looks like**: a strict two-page D3 note carrying all five required elements, plus the export; the 13-page report retitled as session-3 supporting material.

---

## F2 · D3 has no workload estimate

**Confirmed absent** — no match for *charge de travail / workload / jours-homme / ETP / person-day* anywhere in `writup/`.

This is **not** the certification costing already written in §III.2 of the long report. That defers a *price*. The spec asks for an *effort* figure: what the work will take in person-days.

**Done looks like**: an effort estimate with its basis stated — the initial assessment across the 123 imported requirements, evidence collection per subsidiary, and the scope-settling work — expressed in person-days, with the assumption behind each figure named.

---

## F3 · D2 has no justified top 5 critical assets

**What the spec says**

> **D2** Subsidiary mapping: business assets, supporting assets, availability, integrity, confidentiality and traceability needs, cross-subsidiary dependencies, **justified top 5 of critical assets**, acknowledged gaps, update process. — Instance and file · **5 points**

**Where we are.** The only mention in our own files is a forward pointer in `Seance-2-TP-S2-05` line 112: *"Ce point de sortie sert directement d'entrée au prochain TP (S2-06, extraction du Top 5)."* The Top 5 itself was produced in plenary and, as our own S3-06 file admits, *"ne figurent pas dans le dossier écrit de notre groupe"*.

Cited by reference is fine for the **strategy note**. It is not fine for **D2**, which lists it as content. This is the largest single deliverable of the three sessions.

**Done looks like**: five critical assets drawn from our own `LOG-PA` / `LOG-SA` inventory, each with a one-line justification tied to the DICT ratings already set, present in the file **and** visible in the instance.

---

## F4 · The ReCyF claim is contradicted by our own evidence

**The evidence**: `Preuves-ecran-CISO-Assistant/S3-05-ex4-library-search-ReCyF-FOUND-see-note.jpg` shows the framework present in the library — provider **ANSSI**, id `ReCyF`, *"RECYF : RÉFÉRENTIEL CYBER France – Version 2.5 du 17/03/2026"*, built-in, language Français, publication date **2026-07-09**, "Showing 1 to 1 of 1".

**What contradicts it**

| Location | Wrong text |
|---|---|
| `Seance-3-TP-S3-05` Ex. 4 | *"Recherché dans la liste : **introuvable**, et c'est **normal**… cette version est antérieure à la publication du ReCyF"* — plus the whole "the tool has a vintage" lesson built on top of it |
| Business case §II.3 cost table | *"No library in the group instance: the tool's build predates the framework's March 2026 publication"* |
| Business case §III.1 provenance | *"ReCyF does not appear in the instance's library, and that is normal"* |

**Impact on the recommendation: none.** If ReCyF's tooling score moves 2 → 3, its total goes 195 → **205** against ISO's **230** — the gap narrows from 35 to 25 but does not flip. The veto rule still excludes it as *backbone* on coverage, which is score-independent.

**Done looks like**: S3-05 Ex. 4 rewritten around what is actually on screen; both business-case passages corrected; the grid sensitivity note updated to say the gap is 25, not 35, and why that still holds.

---

## F5 · Tool objects carry no owner

**The evidence**: `S3-05-ex3-compliance-assessment-detail.jpg`. Good: name `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, perimeter `Global/MERIDIAN-LOGISTIQUE`, framework ISO/IEC 27001:2022, blank, created 9/7/2026 14:03. **Blank: Authors, Reviewers, Status, Description, ID.** Domain is `Global`.

**Why it costs marks.** The individualising coefficient — 0.85 / 0.95 / 1.05 / 1.15, applied to **both** group components (deliverables coefficient 4, defence coefficient 3) — rests on two elements of equal weight, the first being *"named traceability in the tool, where every object created carries an owner"*.

A second symptom: the framework report reads *"Detected 1 audits (0 counted, 1 excluded): Unknown 1"* — the blank Status excludes our own audit from its own report.

Our S2-05 convention also said never to leave `Global` as the domain.

**Done looks like**: Authors set on the assessment and on the assets, Status set so the audit is counted, Domain corrected, then fresh screenshots.

---

## F6 · The 93 / 37-8-14-34 counts have no evidence behind them

`S3-05-ex2-framework-detail-123-requirements-annexA-4themes.jpg` confirms **123** associated requirements and the two blocks (`core - Clauses`, `annex-a - Statement of Applicability`) with the four themes A.5 / A.6 / A.7 / A.8 — but the tree is collapsed, so no count per theme is visible.

Both S3-05 and the business case state **93** and **37 / 8 / 14 / 34** as fact.

**Done looks like**: either a screenshot with the tree expanded showing the counts, or the claim softened to what the evidence supports.

---

## F7 · The CISO's desk is the wrong format and the wrong authorship

**What the spec says**

> The CISO's desk is written: **each student** answers, in **one page at most**, the question of the day transposed to their subsidiary, and **closes with a recommendation to their management**; it is the only individual mark running across the nine sessions.

Marked on: accuracy and relevance (4) · CISO stance, one page and explicit recommendation (3) · writing, readable by a non-technical executive (3) = **10 points, coefficient 1**.

**The questions**

| Session | Question of the day | Our current file |
|---|---|---|
| S1 | What does a board actually need from its CISO? | `Seance-1-TD-S1-03-principes` — different subject |
| S2 | Why is every asset inventory wrong, and what do we do about it? | `Seance-2-TD-S2-01-inventaire` — right subject |
| S3 | Are we in scope for NIS2, and on what grounds? | `Seance-3-TD-S3-01-applicabilite-nis2` — right subject |

**The problem**: all three are headed *"Réponses du Groupe 4"* — group-authored, where the mark is individual — and S3-01 runs 199 lines against a one-page ceiling. The content is there; the format and the authorship are not.

**Done looks like**: one page per student per session — Miguel and Maxime separately — each closing with an explicit recommendation to management, written for a non-technical reader.

---

## F8 · D1 governance chart has no frequencies

**What the spec says**: *"three-level governance chart with bodies, **frequencies** and nature of decisions"*.

**Where we are**: `Seance-1-TP-S1-05` Section 1 gives instance / governance role / risk-appetite role. The only cadence anywhere in the file is `[PSSI-CADRE-ACC-02]`, a quarterly privilege review — a directive, not a meeting frequency. No body carries a frequency.

**Done looks like**: a frequency against each body (board, executive management, executive committee, group CISO reporting), consistent with the quarterly review already promised in the scoping note.

---

## F9 · The S1 costed roadmap is not part of the hand-in

**What the spec says**

> The costed multi-year roadmap from session 1 is kept by the group but is **not part of the hand-in**: it is the subject of the resit. The scoping document, on the other hand, stays in session 1 of the file as evidence of governance.

`Seance-1-TP-S1-06` Exercise 2 is the roadmap and budget. Keep it, do not feature it as a session-1 deliverable. The budget axes are still legitimately *cited* by the business case as the envelope the decision fits inside.

**Done looks like**: session 1 of the file leads with the scoping document and target governance; the roadmap sits clearly as retained working material.

---

## Verified good — do not re-open

- **123 requirements** imported, two blocks, four Annex A themes — screenshot confirms.
- **Assessment created, blank, attached to `MERIDIAN-LOGISTIQUE`**, dated 9/7/2026 — screenshot confirms; blank is the correct state at this stage.
- **Library screenshots** exist for the hygiene guide, DORA, HDS v2.0 and RGS 2.0 Annexe B2 — the D3 "options set aside" and sorting work is evidenced.
- **Assets list** screenshots (2 pages) and the empty business-impact view exist for D2.
- **Regulatory qualification** (D3 element 1) is done thoroughly, subsidiary by subsidiary, with both readings kept for Logistique.
- **Mapping matrix** (D3 element 4) exists with the four-field anatomy and no `equivalence` line.
- **Strategy note**: sub-sections 1, 2 (by reference) and 3 drafted; 3–5 page budget intact with six sessions still to come.

---

## Working order

F5 and F4 first — they are small, and one of them is an untruth sitting in front of a marker who has the same screenshots we do. Then F3, the largest deliverable. Then F1 + F2 + F6 together, since they all land in the same two-page D3. Then F7, the biggest writing job. F8 and F9 are quick and can close any time.
