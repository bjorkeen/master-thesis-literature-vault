---
title: "Human-in-the-Loop Decision Intelligence for Data-Driven Operations: A Cognitive Digital Twin Approach"
type: artifact
role: thesis_artifact
author: Gkanatsa Antonia
student_id: esd25004
supervisor: Prof. Konstantinos Vergidis
institution: University of Macedonia - MSc Enterprise Software Systems Development
tags: [artifact, HITL, CDT, XAI, DSR, DecisionIntelligence, DataQuality, prototype]
github: https://github.com/bjorkeen/master-thesis-prototype
---

## What it does

A fully operational Human-in-the-Loop Cognitive Digital Twin (HITL-CDT) for **data quality incident management**. The system classifies incoming incidents, routes them via confidence-based thresholds, provides SHAP-based explanations, and enables structured human override — all within a live twin that tracks operational state and SLA pressure in real time.

---

## System architecture

```
Frontend (React 19 / TypeScript / Tailwind CSS)
    ↓
Node.js API Gateway
    ↓
┌──────────────┬──────────────┬──────────────┐
│ ML Service   │ Twin Service │Decision Svc  │
│ :8001        │ :8002        │ :8003        │
│ RandomForest │ State model  │ Routing      │
│ SHAP layer   │ SLA tracking │ Thresholds   │
└──────────────┴──────────────┴──────────────┘
```

**ML model:** RandomForest (200 estimators), trained on 3,000 synthetic incidents (Beta(1.5, 5.0) distribution), ~68.3% accuracy — intentionally moderate to keep human oversight substantive.

**Routing engine:** Confidence-based with SLA-aware thresholds:
- T_auto = 0.85 → auto-resolve
- T_critical = 0.50 → critical escalation
- Multiplicative adjustment: thresholds tighten under queue pressure

**Explainability:** SHAP (TreeSHAP) via GET /explain/{incident_id} — see [[lundberg2017]] and [[lundberg2020]].

---

## Experiment protocol

100 incidents per participant → ~14% auto-resolved, ~70% escalated, ~16% critical (~86 requiring human review, ~20–30 min per participant).

Three conditions:
1. **AI-only** — system decides autonomously
2. **Human-only** — participant decides without ML support
3. **HITL** — participant decides with ML prediction + SHAP explanation

---

## Research hypotheses

| Hypothesis | Claim | Key references |
|---|---|---|
| H1 | HITL achieves higher decision effectiveness than AI-only in uncertain scenarios | [[jarrahi2018]], [[mosqueira2023]], [[natarajan2024]] |
| H2 | XAI outputs positively influence trust calibration and decision authority | [[vereschak2021]], [[leichtmann2023]], [[lundberg2017]] |
| H3 | HITL does not significantly increase operational latency vs AI-only | [[nicoletti2025]], [[parasuraman2000]] |

---

## How it addresses the gap

- ADDRESSES [[GAP]]

---

## Built on — direct architectural inheritance

- EXTENDS [[zhang2024]] — HITL + XAI + CDT combination
- EXTENDS [[nicoletti2025]] — human–AI collaboration architecture
- OPERATIONALISES [[vereschak2021]] — trust evaluation in AI-assisted decision making
- DOMAIN_GROUNDED_IN [[aalst2016]] — process mining substrate
- XAI_METHOD [[lundberg2017]] — SHAP feature attribution
- XAI_METHOD [[lundberg2020]] — TreeSHAP for RandomForest models

---

## Methodology

- METHOD [[hevner2004]] — Design Science Research (artifact + evaluation)
- METHOD [[peffers2007]] — DSR process model (six activities)
- EVALUATION [[venable2016]] — FEDS framework for DSR evaluation design

---

## Informed by — theory and design rationale

- [[parasuraman2000]] — automation level theory (justifies moderate ML accuracy)
- [[sheridan2002]] — supervisory control and human oversight framing
- [[jarrahi2018]] — human-AI complementarity (theoretical basis for H1)
- [[choung2023]] — trust in AI and technology acceptance (trust calibration both directions)
- [[shneiderman2020]] — HCAI framework (high automation + high human control)
- [[agrawal2018]] — prediction economics (threshold selection rationale)
- [[mosqueira2023]] — HITL ML patterns (routing design precedents)
- [[natarajan2024]] — automate vs collaborate framework (three-condition experiment design)
- [[liao2022]] — human-centred XAI (explanation display UI design)
- [[shin2021]] — explainability and causability effects on trust

---

## Domain grounding

- [[bousdekis2021]] — data-driven decision making for operational maintenance (domain parallel)
- [[wang1996]] — canonical data quality theory (incident typology grounding)
- [[brynjolfsson2016]] — rapid adoption of data-driven decision making (enterprise context)

---

## XAI design rationale

- [[lundberg2017]] — SHAP unified framework (chosen method)
- [[lundberg2020]] — TreeSHAP for tree ensembles (specific variant used)
- [[ribeiro2016]] — LIME (considered, not chosen)
- [[salih2024]] — SHAP vs LIME comparative perspective (justifies SHAP choice)
- [[arrieta2020]] — XAI taxonomy and responsible AI framing

---

## Design decisions and their justifications

| Decision | Justification |
|---|---|
| 68% ML accuracy (intentional) | Keeps human oversight substantive, not decorative — [[parasuraman2000]] Level 3–5 |
| Multiplicative threshold adjustment | Thresholds tighten under queue pressure — SLA-aware governance |
| SHAP over LIME | Theoretical consistency for tree models — [[lundberg2017]] vs [[ribeiro2016]], [[salih2024]] |
| 100 incidents (not 300) | 300 produces too few auto-resolutions due to SLA tightening — calibrated behavioural split |
| Twin reads SLA state dynamically | Not from hardcoded constants — key architectural principle |
| Safety-first routing for critical | AI-predicted critical always routes to human regardless of confidence |

---

## Chapter map

| Chapter | Content | Key nodes |
|---|---|---|
| 1 | Introduction | [[GAP]], [[brynjolfsson2016]], [[euai2024]] |
| 2 | Literature Review | All source nodes → [[GAP]] |
| 3 | Methodology | [[hevner2004]], [[peffers2007]], [[venable2016]], [[saunders2019]] |
| 4 | System Design | [[nicoletti2025]], [[zhang2024]], [[lundberg2017]], [[sheridan2002]] |
| 5 | Implementation | [[lundberg2020]], [[lundberg2017]], [[agrawal2018]], [[ribeiro2016]] |
| 6 | Evaluation / Results | [[vereschak2021]], [[natarajan2024]], [[choung2023]], [[hart1988]], [[jian2000]], [[hoffman2023]] |
| 7 | Discussion & Conclusion | [[jarrahi2018]], [[shneiderman2020]], [[batool2024]], [[euai2024]], [[GAP]] → THESIS (gap closed) |
