---
title: The Research Gap
type: gap
role: gap_node
tags: [gap, HITL, CDT, DecisionIntelligence, XAI, OperationalGovernance]
---
	
## The gap in one sentence

No existing work integrates **structured human decision authority with override rights** inside a **cognitive digital twin with live operational state**, applied to **data-driven workflows under SLA pressure** with **XAI-backed confidence routing**.

---

## Why this gap matters

The gap sits at the intersection of four active research streams that have developed largely in parallel:

- **Decision Intelligence** — how organisations make better decisions using data and AI
- **Human-in-the-Loop AI** — how human judgment is preserved in automated systems
- **Cognitive Digital Twins** — how live system state is modelled and acted upon
- **XAI & Governance** — how AI systems are made explainable and accountable

Each stream has produced strong individual contributions. None has produced a system that operates at all four intersections simultaneously, in an operational workflow context, with empirical evaluation of human-AI decision outcomes.

---

## What is present — and what each leaves open

| Dimension covered | Paper | What it leaves open |
|---|---|---|
| HITL + XAI + CDT combined | [[zhang2024]] | Human is observer, not decision authority. No governance layer. |
| HITL–AI collaboration architecture | [[nicoletti2025]] | Human treated as one actor among equals, not as structured override authority |
| CDT AI landscape (SLR) | [[kreuzer2024]] | Confirms monitoring dominates — does not propose a solution |
| HITL ML state of the art | [[mosqueira2023]] | ML pipeline focus — no CDT integration or SLA-bound operational governance |
| HITL ML survey | [[wu2022]] | Same gap as Mosqueira — no CDT or operational workflow context |
| Automate vs collaborate framing | [[natarajan2024]] | Theoretical framework — no CDT implementation or empirical evaluation |
| Trust evaluation in AI decisions | [[vereschak2021]] | Evaluation methodology — not operationalised inside a CDT workflow |
| XAI effects on trust | [[leichtmann2023]] | Single task lab study — no CDT or operational workflow with SLA pressure |
| Human-centred XAI | [[liao2022]] | UX design focus — no CDT or operational decision governance |
| AI for decision making (survey) | [[duan2019]] | Identifies challenge but does not propose a CDT-based solution |
| Responsible AI governance (SLR) | [[batool2024]] | Governance requirements identified — no operational HITL-CDT implementation |
| Human-centred AI framework | [[shneiderman2020]] | Theoretical framework — no implemented system or operational evaluation |
| Data-driven maintenance decisions | [[bousdekis2021]] | Reviews methods — no HITL or CDT integration in the decision loop |

---

## The four dimensions and how they combine

```
HITL AI        ×   Cognitive DT    ×   Decision Intel.   ×   XAI & Governance
────────────────────────────────────────────────────────────────────────────────
Structured         Live system        SLA-aware               SHAP explainability
human override  +  state modelling +  routing            +    Accountability layer
Override rights    Event-driven       Confidence              Regulatory alignment
                   state transitions  thresholds              (EU AI Act)
```

Each column has literature. **The intersection of all four does not.**

---

## Incoming — papers that expose this gap

- EXPOSES_GAP [[zhang2024]] — closest to the intersection but lacks decision governance
- EXPOSES_GAP [[nicoletti2025]] — architecture present, human authority absent
- EXPOSES_GAP [[kreuzer2024]] — SLR confirms monitoring-only dominance
- EXPOSES_GAP [[mosqueira2023]] — HITL ML surveyed but no CDT operational context
- EXPOSES_GAP [[wu2022]] — HITL ML surveyed but no CDT operational context
- EXPOSES_GAP [[natarajan2024]] — automate vs collaborate framed but not implemented in CDT
- EXPOSES_GAP [[vereschak2021]] — trust evaluation methodology without CDT workflow
- EXPOSES_GAP [[leichtmann2023]] — XAI trust effects studied in lab, not operational CDT
- EXPOSES_GAP [[liao2022]] — human-centred XAI designed but not inside CDT governance
- EXPOSES_GAP [[duan2019]] — AI decision making surveyed, CDT solution absent
- EXPOSES_GAP [[batool2024]] — responsible AI governance reviewed, no HITL-CDT proposed
- EXPOSES_GAP [[shneiderman2020]] — HCAI framework theoretical, not implemented
- EXPOSES_GAP [[bousdekis2021]] — data-driven maintenance reviewed, no HITL-CDT loop

---

## Outgoing — what addresses this gap

- ADDRESSED_BY [[THESIS]]

---

## How to use this node in your thesis

This node should be the **final paragraph of Chapter 2**. The table above maps directly to a structured gap statement. The incoming edges represent your literature synthesis; the single outgoing edge to [[THESIS]] is your contribution claim.

In your thesis defence, show the Obsidian graph view with this node centred — the visual convergence of edges makes the gap argument structurally legible without a single word of prose.
