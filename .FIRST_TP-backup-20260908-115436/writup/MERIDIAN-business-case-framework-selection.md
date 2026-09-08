# BUSINESS CASE — SELECTION OF THE MERIDIAN GROUP SECURITY FRAMEWORK

**Issuer** Group CISO · **Recipient** Executive Committee · **Subject** Adoption of a single security framework for the four subsidiaries
**Instructing team** Group 4 (Translog) — instance `translog-b`, instructed scope `MERIDIAN-LOGISTIQUE`
**Decision requested** Approve ISO/IEC 27001:2022 as the group framework, launch the initial assessment, mandate the Group CISO on deployment scope

---

## Executive summary

MERIDIAN has four subsidiaries with four different obligation profiles and, to date, no common security framework. Three of the four will enter the scope of the European NIS 2 directive upon promulgation of the French transposition law; the fourth will not, and remains the one carrying 45,000 user accounts. Obligations already in force — GDPR across all four, HDS for Santé's hosting providers, RGS in the environment of Territoires' clients — depend on no legislative calendar at all, and two client relationships are already asking for security evidence in writing.

We examined three candidates against a weighted grid: the ANSSI hygiene guide, the forthcoming French control framework (ReCyF), and ISO/IEC 27001:2022. **We recommend ISO/IEC 27001:2022 as the group's backbone framework, across all four subsidiaries.** It is the only candidate that covers the whole perimeter — regulated and unregulated subsidiaries, information systems and industrial environments — and the only one producing evidence a third party can act on. The framework is already imported into the group's governance tool and an initial assessment is created and attached to the MERIDIAN scope: a favourable opinion requires no technical prerequisite.

**On cost, the position is explicit rather than deferred.** ISO is the only one of the three options whose text must be purchased and the only one carrying a third-party audit — and it is also the only one that buys the deliverable two clients have already demanded in writing. The Direction Générale's requirement of *no new budget in the first year* is met, and met by sequencing rather than by promise: the certification audit cannot be contracted before the deployment scope is settled, which is exactly what this decision mandates. §II.3 sets out what each option costs and where; §III.2 states what we commit, what we defer, against what trigger, and what we cannot price today — together with the named input we are missing and the person who owns it.

This choice delivers no regulatory compliance by itself, and we say so before an auditor does. What it delivers is a single language in which the group can finally measure itself.

---

# THEME I — WHY THIS DECISION, AND WHY NOW

## I.1 Four subsidiaries, four obligation profiles, one absent framework

MERIDIAN is a 150-person holding and four subsidiaries totalling 7,550 employees. Their businesses do not overlap, and neither do their obligations.

| Subsidiary | Headcount | Activity | Obligation profile in one line |
|---|---|---|---|
| MERIDIAN Santé | 3,200 | 4 care establishments | Care mission, health data, HDS requirement on its hosting providers |
| MERIDIAN Logistique | 2,800 | 6 warehouses; transport, temperature-controlled storage, third-party dispatch | Industrial perimeter, contractual commitments to a pharmaceutical client |
| MERIDIAN Éducation | 900 | Teaching portal, 45,000 user accounts | Personal data of minors, shared IT department with Territoires |
| MERIDIAN Territoires | 650 | Citizen services platform for ~30 client local authorities | Clients are public bodies; RGS applies to their environment |

Until this week the group had no common framework, no consolidated compliance measurement, and no shared vocabulary in which one subsidiary's security posture could be compared with another's. Each subsidiary managed its security as it saw fit — which is precisely the structural gap identified as the root of every other gap in our group gap analysis (dossier S1).

## I.2 Three of four subsidiaries enter NIS 2 scope — and the fourth does not stop existing

NIS 2 applies through two cumulative filters: the sector (Annex I "highly critical", Annex II "other critical"), then size. At MERIDIAN **the size filter discriminates nothing** — all four subsidiaries are far above every threshold. The entire characterisation therefore turns on the sector, which is to say on an exact description of the activity actually performed. That is mapping work, not legal work (applicability).

| Subsidiary | Annex | Provisional characterisation | Why it is not closed |
|---|---|---|---|
| Santé | I — health | **Essential entity** | No serious alternative reading |
| Logistique | I *or* II | **Essential or important**, depending on qualification | Annex I "road transport" names road authorities and intelligent transport system operators, not every private freight carrier; Annex II "postal and courier services" fits the dispatch activity. The annex, not the size, decides the category |
| Territoires | I, under two hypotheses | **Depends on a choice France has not made** | Either local authorities are brought into the "public administration" heading, or the platform qualifies as a managed ICT service (B2B) — which would make it essential regardless of that choice |
| Éducation | Neither | **Out of scope** | Annex II names research, not teaching. The sector filter fails at step one, so the size filter is never reached |

Two consequences deserve to be stated in committee. First, **the category has a price**: an essential entity is supervised both ex ante and ex post, with fines capped at 2% of worldwide turnover; an important entity is supervised ex post only, capped at 1.4%. The qualification arbitration on Logistique is therefore a financial question, not a taxonomic one. Second, **out of scope is not out of risk**: Éducation carries 45,000 accounts (applicability) and eleven ungoverned online services discovered by its own inventory work, one of them a generative-AI tool receiving pupils' marked work (dossier S2). No NIS 2 obligation targets it. Nothing about that removes the exposure.

We therefore prepare Logistique on the **high hypothesis** — essential entity — while carrying the qualification question to arbitration. Preparing for the more demanding regime and then being classified "important" costs a few months of advance; the reverse costs a compliance plan redone under calendar pressure.

## I.3 The obligations already in force depend on no calendar

It would be a mistake to present this decision as a bet on a law. Three obligation sets already bind the group today, and none of them waits for a transposition (applicability):

- **GDPR** applies to all four subsidiaries, without exception and without threshold.
- **HDS** (health data hosting) applies to Santé's hosting providers, and is therefore a requirement the subsidiary must impose contractually and verify.
- **RGS** governs the environment of Territoires' public-sector clients, and reaches the subsidiary through those clients.

A framework decision that only made sense if a particular law were promulgated on a particular date would be a fragile decision. This one does not depend on that.

## I.4 The commercial pressure is already at the door

Two demands are already formulated, in writing, by paying clients (grid):

- The **~30 client local authorities** of Territoires ask for security guarantees as a condition of the relationship.
- The **pharmaceutical client of Logistique has announced a security questionnaire** for its next audit — on a contract already carrying €12,000/day penalties for stoppage and annual cold-chain audits (dossier S2).

This is the point on which we ask the Committee to be explicit, because our recommendation rests on it: at MERIDIAN, **evidence a third party can act on is not a communications luxury, it is a commercial condition**. A self-declaration answers neither of those two demands.

## I.5 The internal trigger: we can now decide on an instructed file

Since this week the group holds a mapping maintained in a common governance tool and a framework imported and ready to be assessed (import). The material for a reasoned choice — the weighted grid, the mapping verdicts, the framework identity sheet, the import proof — exists and is attached to this file. **Deciding now, on an instructed file, costs less than deciding under the constraint of a regulatory calendar, whatever that calendar turns out to be.**

## I.6 What this theme does not claim

Applicability **triggers obligations; it measures nothing**. An entity can be in scope and well protected, or out of scope and vulnerable. Nothing in this section says MERIDIAN is compliant, nor that it will be at promulgation — on Logistique specifically, with no incident procedure, no IT/OT segmentation and no nominative accounts on the provider side, we are far from it.

---

# THEME II — WHAT WE COMPARED, AND WHAT WE RECOMMEND

## II.1 The three candidates

Three frameworks were on the Committee's table. Each is summarised here by its **real strength** first, because a note that caricatures the alternatives convinces only its author.

| Option | Real strength | Limit |
|---|---|---|
| **ANSSI hygiene guide** | Free, 42 measures, two levels, its own tracking tool: **usable tomorrow morning**, and the fastest way to bring a concrete risk down | No legal force, no evidence beyond a self-declaration, weak on group governance (grid) |
| **ReCyF** (forthcoming ANSSI control framework) | **Best placed on the binding-nature criterion**: its security objectives are intended to be set by decree; it is before ReCyF that NIS 2 compliance will be demonstrated (grid) | Working version circulated since March 2026, no certification possible, and **silent on a subsidiary outside NIS 2 scope** (mappings) |
| **ISO/IEC 27001:2022** | Covers all four subsidiaries, information systems and industrial alike, and **alone leads to third-party certification** (grid) | Voluntary: binding only through contract; the clause 4–10 management system and the certification audit are a real, and at this stage unpriced, effort |

## II.2 The selection grid

Five criteria, weighted against the MERIDIAN context, scored 0–3, with a written justification behind every score. The mechanics matter less than the discipline: **a weighted grid does not compute the right answer, it makes the deliberation transparent and contestable.**

| Criterion | Weight | ISO/IEC 27001:2022 | ReCyF | Hygiene guide |
|---|---|---|---|---|
| Binding nature, current or forthcoming | 30 | **1** — voluntary; binding only by contract, which is already happening | **3** — objectives to be set by decree | **1** — no legal force; state-of-the-art argument only |
| Coverage of the group perimeter | 25 | **3** — 93 controls, four themes, plus management clauses: IS, OT and steering | **2** — 20 objectives built for NIS 2 entities; silent on Éducation; objectives 16–20 target essential entities only | **1** — 42 generalist measures, weak on group governance and industrial systems |
| Evidence enforceable towards third parties | 20 | **3** — the only one of the three leading to third-party certification, on a written scope | **1** — no certification; usable before the authority, not before a client local authority | **1** — its tracking tool yields a self-declaration only |
| Maturity and stability of the text | 15 | **3** — 2022 edition, maintained international standard, ~1,000 certified organisations in France end-2023 | **1** — working version, objectives not yet set by decree | **2** — stable, but the 2017 v2: stable by immobility as much as by maturity |
| Tooling and implementation effort | 10 | **2** — imports natively into the group tool, but the management system and audit are a real charge | **2** — free, 20 objectives, tooling still uncertain | **3** — free, two levels, its own tracking tool |
| **Weighted total (out of 300)** | **100** | **230** | **195** | **135** |

*Detail — ISO: 30+75+60+45+20 · ReCyF: 90+50+20+15+20 · Hygiene: 30+25+20+30+30.*

ISO leads ReCyF by 35 points out of 300 and the hygiene guide by nearly 100. **The hygiene guide wins the effort column and loses every other: it is a starting point, not a group backbone.**

## II.3 What each option costs

The grid scores tooling and implementation effort at weight 10 — deliberately low, because the charge cannot be allowed to choose the backbone of a 7,550-employee group, but deliberately not zero, because the Direction Générale requires **no new budget in the first year** (grid). That single cell compresses several different kinds of money. Before arbitrating, the Committee should see them separated, because the three options do not carry cost in the same places.

**The rule applied below is the group's own**: every figure carries its base, and where the file gives no figure we say what the number will be computed from rather than inventing one. A bare number is not an arbitration; it is an opinion in costume (dossier S1).

| Cost component | ANSSI hygiene guide | ReCyF | ISO/IEC 27001:2022 |
|---|---|---|---|
| **Acquiring the text** | None — published free by ANSSI (grid) | None — published free by ANSSI (grid) | **The only one of the three that must be purchased.** ISO/IEC standards are sold by ISO and its national members; the two ANSSI documents are not |
| **Internal implementation effort** | **Lowest** — 42 measures, two levels (standard / reinforced), no management system to run (grid) | **Medium, and indeterminate for us** — 20 objectives, but objectives 16–20 apply only to essential entities: Logistique's effort therefore depends on a qualification arbitration not yet made (applicability) | **Highest** — the 93 Annex A controls *plus* the clause 4–10 management system, which is a recurring operating cost, not a one-off project (grid) |
| **Tooling** | Its own tracking tool, free — but standalone, outside the group instance (grid) | **No library in the group instance**: the tool's build predates the framework's March 2026 publication, so entry would be manual and its cost is unquantified (import) | **Zero marginal cost** — imports natively, and the import is already done: 123 requirements created (import) |
| **Third-party audit** | Not possible — the tracking tool yields a self-declaration only (grid) | Not possible — no certification exists (grid) | **Certification audit, surveillance audits, three-yearly re-certification.** Not priced at this stage — see §III.2 for the drivers it will be priced against |
| **Recurring cost** | Near zero | Active watch only | Management-system upkeep plus the audit cycle |
| **Committed in year one** | None | None | **None** — see below |

### Why "free" is not the same as "cheap"

Two of the three options cost nothing to obtain, and that is the entirety of their cost advantage. The hygiene guide's zero buys a self-declaration. ReCyF's zero buys a working document that cannot be certified and that says nothing about one subsidiary in four (grid, mappings). ISO is the only option that costs money, and it is the only one that buys the deliverable the ~30 client local authorities and the pharmaceutical client's announced security questionnaire are actually asking for (grid).

The arbitration the Committee is being asked to make is therefore not *cheapest versus most expensive*. It is: **what does the spend buy that the saving does not?** Put in the terms of the sensitivity test in §II.5, if third-party evidence is judged accessory, the saving wins and the ranking flips — and that judgement belongs to the Committee, explicitly.

### Why year one commits nothing new, and why that is a consequence rather than a promise

The decision requested has three parts: adopt the framework, open the initial assessment, mandate the Group CISO on scope. Each of the three has a cost of zero in new external spend, and for a structural reason:

- **The assessment is already created and attached to the `MERIDIAN-LOGISTIQUE` scope**, blank. Opening it costs nothing (import).
- **Collecting evidence against the 123 requirements is internal effort** by the subsidiary CISO and DSI teams that already exist, charged against the *trust foundation* axis that already holds 40% of the multi-year security budget (dossier S1).
- **The certification audit is the only genuinely new external spend, and it cannot be contracted before the scope is settled** — which is precisely what the mandate covers. The zero is therefore produced by the sequencing, not asserted against it.

One consequence must be stated so it is not double-counted later: **remediation cost is not certification cost.** The IT/OT segmentation that any industrial ISO scope presupposes is already funded at the 24-month milestone under the *OT/IT resilience* axis, which holds 35% of the same envelope, alongside the 15% reallocation from existing envelopes pegged to the obsolescence KRI (dossier S1). The framework decision **opens no fourth budget axis** and must not be charged with work already financed.

## II.4 One criterion is a condition, not a score

A weighted average compensates — that is its function — and some criteria do not compensate. We therefore placed **coverage of the perimeter above the calculation**, as a veto rule:

> *Any framework that cannot simultaneously cover Santé's sectoral obligations (HDS), Logistique's industrial perimeter (PLCs, WMS, cold chain) and a subsidiary outside NIS 2 scope (Éducation) is set aside, whatever its weighted score.*

Applied to the three candidates, this changes one thing and changes it before the arithmetic: **ReCyF cannot be the group's backbone**, because it has nothing to say about an entity that is not a NIS 2 entity. It is not its score of 195 that sets it aside; it is a condition it does not meet. The distinction matters for the Committee — we do not discard ReCyF as *poor*, we discard it as *backbone*, and we retain it as an actively monitored framework (§III.4).

## II.5 Sensitivity: where the ranking flips

An analysis that does not test its own reversal is a staging, not an analysis. ReCyF leads ISO on exactly one criterion, so two tests suffice (grid):

| Test | Manipulation | Result | Reading |
|---|---|---|---|
| Weight transfer | Binding nature 30 → **39**, maturity 15 → **6** | ISO **212**, ReCyF **213** → flip | Requires moving 9 points out of 100 — nearly a third of the weight of the already-heaviest criterion — *and* reducing text stability to almost nothing. That is not a fine adjustment, it is a change of doctrine |
| Criterion removal | Drop "evidence enforceable towards third parties" (20) | ISO **170**, ReCyF **175** → flip | This test names what actually protects the recommendation: the client local authorities and the pharmaceutical questionnaire. If the Committee judges enforceable evidence accessory, it should choose differently — and say so explicitly |

**The recommendation is robust without being unassailable.** It does not hang on a decimal — no flip occurs for one or two weighting points — but it rests on two contextual judgements the Committee must validate openly: that evidence towards third parties counts, and that the stability of the text counts.

## II.6 Recommendation

**We recommend adopting ISO/IEC 27001:2022 as the backbone of MERIDIAN group security, across all four subsidiaries.** Three arguments designate it, and a fourth makes it immediate:

1. **It is the only option covering the entire group perimeter** (grid). Coverage was treated as a condition, not a score (§II.4). ReCyF fails that condition — not through weakness, but through purpose.
2. **It is the only option producing evidence a third party can act on** (grid), on a scope written down in black and white. Neither the client local authorities nor the pharmaceutical questionnaire is satisfied by a self-declaration.
3. **Part of the effort will be reused, not redone** (mappings) — with a boundary stated inside the argument rather than a page later; see §II.7.
4. **The decision is already tooled** (import). The framework is imported into the group instance and the initial assessment is created and attached to the MERIDIAN scope, blank. A favourable opinion requires no technical prerequisite.

## II.7 What the mappings actually transfer

A mapping table sets a source framework's requirements against a target's, line by line, to reuse what is done and see what remains. We examined three requirements in detail. **All three verdicts are `intersect`; none is `equivalence`** — as in the whole 180-line NIST CSF → ISO set shipped with the governance tool, where no line declares two requirements equivalent (mappings).

| Source requirement | ISO/IEC 27001:2022 target | Relation | What the source demands that the target does not |
|---|---|---|---|
| NIS 2 `1.1-EI/EE` — list activities, services, owners, supporting systems | Clause 4 (context) + `A.5.9` | intersect | Listing activities **outside** the applicability criteria. In one sentence: **ISO lets you choose your scope; NIS 2 forbids you to choose it** |
| ReCyF objective 2 — digital security governance framework | Clauses 5, 6, 9 + `A.5.1`, `A.5.2` | intersect (strong) | Nothing material — but the reuse is bounded: **one objective out of twenty, on the certified scope only** |
| Hygiene guide, measure 4 — sensitive assets and network diagram | `A.5.9`, `A.5.12` | intersect | The guide's "simplified diagram" is *less* demanding than the NIS 2 inventory: complying with the guide does not finish the NIS 2 requirement |

The doctrine that follows is one line, and we state it before the Committee infers a stronger one: **there is no general presumption of compliance.** ReCyF accepts a certified ISO management system as an acceptable means of demonstrating **its governance objective alone — one objective out of twenty — and only on the scope covered by the certificate**. Beyond that, a maintained mapping table transfers nothing; it lets us attribute each piece of ISO evidence to the obligation it serves, and above all shows what remains to be produced.

## II.8 The best objection to our recommendation, and our answer

The serious objection is not cost. It is that **the authority will inspect us against ReCyF, not against ISO**, and that a badly chosen backbone makes the work happen twice.

We accept the objection and answer it in three parts. ReCyF is a working document that cannot today be made the backbone of a 7,550-employee group. It says nothing about one subsidiary in four. And the distance between the two frameworks is handled by mapping, not by a second programme (mappings). We therefore hold ReCyF under **active monitoring**, ready to become the NIS 2 demonstration framework once its objectives are fixed by decree — at which point the backbone will not have to change.

---

# THEME III — WHAT THE DECISION COMMITS, WHAT IT DOES NOT COVER, AND WHAT IS ASKED

## III.1 The decision is already tooled

Before recommending a framework we verified its identity — not its merit, its identity: the ordinary and expensive failure is to work six months against an old edition, an unofficial translation or a truncated document found on a third-party site.

| Field | Value |
|---|---|
| Exact name and publisher | **ISO/IEC 27001:2022**, published jointly by ISO and IEC |
| Edition and date | **3rd edition, 25 October 2022** |
| Amendment in force | **Amd 1:2024** |
| Official French title | *Systèmes de management de la sécurité de l'information — Exigences* |
| Status for MERIDIAN | **Voluntary**, and it will remain voluntary after promulgation. What changes then is that certification may count as an acceptable means of compliance for the French framework's governance objective, on the certified scope only — that changes its *value*, not its *status* |

The import is then a matter of fact, not of intention (import). In instance `translog-b`:

- **123 evaluable requirements** created — the clauses 4 to 10 of the standard body plus the Annex A controls;
- **93 Annex A controls**, distributed **37 organisational / 8 people / 14 physical / 34 technological**;
- a compliance assessment named `MERIDIAN - ISO/IEC 27001:2022 - initial assessment`, attached to the `MERIDIAN-LOGISTIQUE` scope, **blank — which is its normal state today**.

**Reconciliation, so the figures can be checked rather than believed**: 123 evaluable requirements = the clauses 4 to 10 of the standard body + the 93 Annex A controls; and 93 = 37 + 8 + 14 + 34. Any other total means either an incomplete import or a different library, and both are corrected in two minutes now — or in two days on the day of the audit.

Two provenance notes, because these objects are what the group will be measured on rather than this prose. First, the instance dates and attributes every object it holds: that is what makes an export evidence rather than an assertion. Second, **the tool itself has a vintage.** ReCyF does not appear in the instance's library, and that is normal: the deployed build predates the framework's publication. A software publisher freezes the world at each release; the authority publishes at its own rhythm.

Three requirement–evidence pairs are already identifiable from work the group has done: clause 4 (context) against the session-2 mapping of business and supporting assets; clause 5.3 (roles and authorities) against the RACI matrix and the scoping note of session 1; `A.5.9` (inventory of information and associated assets) against the prioritised inventory and the assets entered in the instance (dossier S1, dossier S2). They will be the first three exhibits of the audit. *The group's consolidated top-five critical assets, arrived at in plenary, is cited here by reference: it is not part of our own written file, which instructed Logistique, and the five lines will be checked against the plenary record before final submission.*

**One sentence to keep the tooling honest: importing is not complying.** The instance now holds the *list* of requirements, not their satisfaction. Our compliance percentage has not moved by a point because the standard entered the tool. The import installs the yardstick; measurement starts afterwards.

## III.2 The cost position: what is committed, what is deferred, and against what

§II.3 set out what each option costs. This section states what the group actually commits by saying yes, and — the harder half — what it deliberately does not price today and why that is a discipline rather than an omission.

### What is committed now

**Nothing new.** The three parts of the decision — adopt, open the assessment, mandate the scope — consume existing internal effort against budget axes already apportioned: the *trust foundation* axis at 40% of the multi-year security budget carries the evidence collection, and the *OT/IT resilience* axis at 35% already carries the segmentation work at its 24-month milestone (dossier S1). The Direction Générale's requirement is met without an exception being asked for.

### What is deferred, and against what trigger

The certification costing is deferred, and its trigger is named: **it is produced once the deployment scope has been settled subsidiary by subsidiary**, which is the mandate this decision confers. Pricing it before that produces a false number, because a certification quotation is driven by variables the mandate is precisely there to fix:

| Cost driver | Why it cannot be fixed today | Who settles it |
|---|---|---|
| Number of certificates — one group scope or one per subsidiary | This is the object of the mandate itself | ComEx decision, Group CISO proposal |
| Number of sites in scope | E1–E6 for Logistique, 4 care establishments for Santé; audit day-count scales with sites | Group CISO with subsidiary CISOs |
| Headcount in scope | Between 650 and 7,550 depending on the answer above | Follows from the scope decision |
| Whether the industrial perimeter is included | Not honestly declarable before the Logistique network diagram exists and IT/OT is segmented — the 24-month milestone (dossier S1) | Trajectory, not this decision |
| Remediation already financed | Must **not** be re-charged to the certification: it sits in an approved axis | Group CISO, at costing |

### What we cannot price at all today, and who owns the missing input

The regulatory exposure is the one figure we are unable to complete, and we prefer to name the gap than to fill it with an estimate. Fines are capped as a percentage of **worldwide turnover** — 2% for an essential entity, 1.4% for an important one — and **the subsidiaries' turnover and balance-sheet figures have never been communicated to the Group CISO** (applicability). The assessment is made entity by entity, not at consolidated group level, so it is Logistique's 2,800-employee entity that would be measured, not the group's 7,550.

Two things follow, and both are actionable rather than rhetorical. **The floor is knowable even though the percentage is not**: the caps carry floors of roughly €10M for an essential entity and €7M for an important one, so an order of magnitude exists today without any figure from the holding. And **the missing input has a named owner**: the turnover and balance-sheet data must be requested from the **holding's Chief Financial Officer**, and they will in any case be required in the registration file submitted to the national authority (applicability). We record that request here as an action arising from this note.

### What it costs not to decide, or to decide wrongly

- **Not deciding**: the pharmaceutical client's announced security questionnaire arrives against a contract already carrying €12,000/day stoppage penalties and annual cold-chain audits, and ~30 client local authorities condition their relationship on guarantees (grid, dossier S2). The cost of having no answer is commercial and immediate, and it does not wait for a law.
- **Deciding wrongly**: adopting a working document as backbone means redoing the work when it changes, on a framework that in any case says nothing about one subsidiary in four (mappings).
- **The exposure the framework does not remove**: a WMS stoppage beyond six hours blocks 40% of the group's shipped volume, and backups have never once been restored since commissioning (dossier S2). No framework choice fixes that. It is named here so the Committee does not read a framework decision as a resilience decision.

## III.3 Limits and blind spots

A note with no declared limits is precisely what makes senior management suspicious. Six, of which two are our own.

1. **This choice delivers no regulatory compliance.** There is no general presumption of NIS 2 compliance through ISO; the only recognised transfer covers one objective out of twenty, on the certified scope only (mappings). GDPR, HDS and RGS continue to apply independently (applicability).
2. **Owned blind spot, and it is a serious one: ISO lets the organisation choose its management-system scope, where NIS 2 forbids choosing it.** A certificate obtained on the best-run subsidiary would have proved nothing about the other three. That is exactly why the decision requested covers all four subsidiaries and an explicitly settled, subsidiary-by-subsidiary scope.
3. **Second owned blind spot, technical: there is to this day no network diagram of Logistique**, and its IT and OT networks are interconnected without segmentation — with an integrator connected through a 4G box outside the supervised network and ~300 Wi-Fi handheld scanners. **No ISO scope including the industrial perimeter could be honestly declared before that work is done**, already booked at 24 months in our roadmap (dossier S1).
4. **The French text will evolve** until its decrees and orders. Its working version is under active monitoring and the mapping table will be revised at each publication.
5. **The cost of certification is not priced** at this stage, deliberately and against a named trigger: the costing follows the scope mandate, and its drivers, its missing input and the owner of that input are set out in §III.2. The present decision commits no new budget in year one.
6. **The recommendation is robust, not unassailable**: the grid flips if the Committee judges third-party evidence accessory (grid). That is a contextual judgement belonging to the Committee, and it must be made explicitly.

## III.4 What we monitor, and how the remainder is treated

The framework choice leaves a remainder. We treat it by three named means, none of which is a second programme:

| Remainder | Treatment | Owner |
|---|---|---|
| Future NIS 2 demonstration | **Active monitoring** of ReCyF and the transposition law; ReCyF becomes the demonstration framework once its objectives are set by decree | Group CISO |
| Reuse of ISO effort towards NIS 2 | **Mapping table maintained**, revised at each publication, so each piece of ISO evidence is attributed to the obligation it serves | Group CISO |
| Concrete risks that will not wait for a management system | **Immediate application of the hygiene guide** where urgency demands it — starting with Logistique's IT/OT segmentation | Subsidiary CISOs |
| Sectoral obligations (GDPR, HDS, RGS) | Unchanged, applied independently of this decision | Subsidiary CISOs / DPO |

## III.5 What happens the day after a yes

The framework decision is not a standalone event; it is the third stone of a trajectory already approved in principle. It slots in without moving anything:

- **Immediately** — the initial assessment is opened, and the four subsidiary CISOs are notified of the evidence-collection schedule. No new budget. In the same movement, the turnover and balance-sheet data are requested from the **holding's Chief Financial Officer**: they are the missing input of §III.2 and will in any case be required in the registration file for the national authority (applicability).
- **Session-4 horizon** — the imported framework becomes the **audit framework**: the group measures, requirement by requirement, the gap between what it claims and what it does. This business case, once accepted, is the first exhibit in that file: it is what states which yardstick we accept to be measured against, and on which scope.
- **12 months** — priority-1 gaps addressed (Santé biomedical segmentation under way, Logistique provider account separation completed), framework policy adapted by all four subsidiaries.
- **24 months** — Logistique IT/OT segmentation operational, Territoires logging centralised to the SOC. This is the milestone that makes an industrial ISO scope honestly declarable.
- **Session-8 horizon** — the Statement of Applicability, control by control, which has meaning only *after* the risk analysis. Today the Annex A block is a label on a screen, nothing more.

## III.6 Decision requested

> **The Executive Committee is invited to approve the adoption of ISO/IEC 27001:2022 as the security framework of the MERIDIAN group, across the four subsidiaries, and the launch of the initial assessment already created in the governance tool, mandating the Group CISO to settle the deployment scope subsidiary by subsidiary.**
>
> **Decision expected at Thursday's session.** First step on the morning after a favourable opinion: opening of the initial assessment and notification to the four subsidiary CISOs of the evidence-collection schedule — with no new budget.

---

## Annex — Traceability of claims

Every figure and every argument in this note comes from a piece of the instructed file. The marker at the end of a sentence names which one.

| Marker | Source | Claims it supports in this note |
|---|---|---|
| **(applicability)** | NIS 2 applicability analysis, subsidiary by subsidiary | Sector and size filters; the four characterisations; 900 employees / 45,000 accounts; GDPR, HDS, RGS in force; the 2% / 1.4% caps and their ~€10M / ~€7M floors; entity-by-entity assessment; the turnover data absent from the CISO's file and owed by the holding's CFO |
| **(grid)** | Weighted selection grid, veto rule and sensitivity tests | The five criteria and their weights; the 15 scores and totals 230 / 195 / 135; the two flip tests; ~30 client local authorities and the announced pharmaceutical questionnaire; the Direction Générale's "no new budget in the first year" requirement; each option's licence cost and implementation charge |
| **(mappings)** | Requirement mapping tables | The three `intersect` verdicts; the absence of any `equivalence` line in the 180-line reference set; the ReCyF bound of one objective out of twenty on the certified scope |
| **(import)** | Framework identity sheet and import into `translog-b` | Edition, date and amendment; 123 requirements; 93 Annex A controls in 37 / 8 / 14 / 34 and their reconciliation; the initial assessment attached to `MERIDIAN-LOGISTIQUE`; the absence of ReCyF from the instance library and the tool's build vintage |
| **(dossier S1)** | Session 1 — gap analysis, target governance, roadmap and budget | The structural gap at group level; the 12/24/36-month milestones; the IT/OT segmentation commitment; the three budget axes at 40 / 35 / 25% and the 15% reallocation pegged to the obsolescence KRI; the rule that every percentage carries its base |
| **(dossier S2)** | Session 2 — inventory, business assets, mapping | Éducation's eleven ungoverned services; Logistique's €12,000/day penalties, the six-hour / 40% shipped-volume dependency and the never-restored backups |

**A note on the figures the group will actually be marked on.** The compliance objects live in instance `translog-b`, where each is dated and attributed; that is what makes an export evidence rather than a claim. The three import readings quoted in §III.1 reconcile arithmetically (123 = clauses 4–10 + 93; 93 = 37 + 8 + 14 + 34) so a reader can check them rather than take them on trust, and they are to be confirmed on screen before submission. The group's consolidated top-five critical assets is cited by reference only: it was arrived at in plenary and is not part of our own written file, which instructed Logistique.

**Statements this note deliberately does not make.** That the choice is proven right — it makes the deliberation transparent and contestable, and §II.5 shows where a different doctrine would reverse it. That the framework is adopted — it is *recommended*; the decision belongs to the Committee, and this note is written so that "no" is a possible answer. That the group is ready to be certified — without a Logistique network diagram and IT/OT segmentation, no scope including the industrial perimeter could be honestly declared today. That we know what certification will cost — we know what it will be priced against, which is a different and more honest claim.
