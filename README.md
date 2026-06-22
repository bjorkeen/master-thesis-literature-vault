# Thesis Literature Knowledge Graph

> **Human-in-the-Loop Decision Intelligence for Data-Driven Operations: A Cognitive Digital Twin Approach**
> Gkanatsa Antonia · esd25004 · MSc Enterprise Software Systems Development
> University of Macedonia · Supervisor: Prof. K. Vergidis · Industry Mentor: George Georgalidis (Deloitte)

---

## What this is

A structured knowledge graph of the 59 sources comprising the thesis literature review, built in [Obsidian](https://obsidian.md). Inspired by Andrej Karpathy's LLM wiki approach — every source is a node, every connection is a typed relationship, and the research gap is a structural node rather than a narrative claim.

The graph makes the research gap **visually legible**: thirteen papers converge on a central GAP node via `EXPOSES_GAP` edges, and one outgoing edge leads to the THESIS artifact. The argument is visible in the graph structure itself, without reading a single sentence of prose.

---

## Repository structure

```
thesis-literature-vault/
├── README.md               ← this file
├── GAP.md                  ← the research gap node (not a paper)
├── THESIS.md               ← the thesis artifact node
└── sources/                ← 59 source notes, one per paper
    ├── zhang2024.md
    ├── nicoletti2025.md
    ├── kreuzer2024.md
    └── ...
```

---

## Node types and colours

| Colour | Filter | Meaning |
|---|---|---|
| 🔴 Red | `type:gap` | The research gap — structural hole in the literature |
| 🟢 Green | `type:artifact` | The thesis artifact — HITL-CDT prototype |
| 🟠 Orange | `tag:#gap_exposing` | Papers that directly expose the gap |
| 🔵 Blue | `role:methodological_backbone` | DSR methodology foundation |
| ⚫ Dark grey | — | Supporting literature (domain, XAI theory, trust, CDT, DI) |

---

## Relationship vocabulary

Six typed, directional edge types encode the role each connection plays in the thesis argument:

| Relationship | Meaning |
|---|---|
| `ENABLES` | A provides the foundation that makes B possible |
| `EXTENDS` | A builds on B and adds something new |
| `EXPOSES_GAP` | A reveals a limitation or missing piece → points to GAP node |
| `ADDRESSES` | A proposes a solution to the gap → THESIS points to GAP |
| `INFORMS` | A contributes context or evidence without being directly extended |
| `CONTRASTS` | A highlights tension or a limitation relative to B |

---

## The thirteen gap-exposing papers

These are the orange nodes — each covers part of the problem space but leaves the core intersection unaddressed:

| Paper | What it covers | What it leaves open |
|---|---|---|
| Zhang et al. (2024) | HITL + XAI + CDT combined | Human is observer, not decision authority |
| Nicoletti & Appolloni (2025) | Human–AI collaboration architecture | Human treated as actor, not governance authority |
| Kreuzer et al. (2024) | AI in digital twins (SLR) | Confirms monitoring dominates — no solution proposed |
| Mosqueira-Rey et al. (2023) | HITL ML state of the art | No CDT integration or SLA-bound governance |
| Wu et al. (2022) | HITL ML survey | No CDT or operational workflow context |
| Natarajan et al. (2024) | Automate vs collaborate framing | Theoretical — no CDT implementation |
| Vereschak et al. (2021) | Trust evaluation methodology | Not operationalised in a CDT workflow |
| Leichtmann et al. (2023) | XAI effects on trust | Lab setting — not operational CDT with SLA pressure |
| Liao & Varshney (2022) | Human-centred XAI design | No CDT or operational decision governance |
| Duan et al. (2019) | AI for decision making (survey) | Identifies challenge — no CDT-based solution |
| Batool et al. (2024) | Responsible AI governance (SLR) | Governance requirements — no HITL-CDT implementation |
| Shneiderman (2020) | Human-centred AI framework | Theoretical — not implemented or operationally evaluated |
| Bousdekis et al. (2021) | Data-driven maintenance decisions | No HITL or CDT integration in the decision loop |

---

## The research gap

No existing work integrates all four simultaneously:

```
Structured human decision authority with override rights
        +
Cognitive digital twin with live operational state
        +
Data-driven workflow under SLA pressure with XAI-backed confidence routing
        +
Empirical evaluation of human-AI decision outcomes in an operational context
```

Each dimension has literature. The intersection does not — until this thesis.

---

## Source note structure

Every file in `sources/` follows the same schema, inspired by Karpathy's wiki approach:

```markdown
---
title: ...
authors: ...
year: ...
tags: [domain tags] + gap_exposing (if applicable)
role: role_in_thesis
---

## What it is
One paragraph — what the paper actually claims or proposes.

## Why it matters for the thesis
Direct connection to the thesis argument, hypotheses, or design decisions.

## What it leaves open
The specific limitation that contributes to the research gap.

## Where it appears
Which chapter and what specific claim this source supports.

## Connections
- RELATIONSHIP_TYPE [[target_id]]
```

---

## How to use this vault

**Setup**
1. Clone or download this repository
2. Open the folder as a vault in Obsidian (File → Open folder as vault)
3. Open Graph View (`Cmd/Ctrl + G`)

**Colour groups** — add these in Graph View → Filters → Groups (in this order):

```
tag:#gap_exposing          → orange
type:gap                   → red
type:artifact              → green
role:methodological_backbone → blue
```

**Display settings**
- Enable Arrows (Display → Arrows → on)
- Increase Repel force to ~8–10 (Forces → Repel force)
- Increase Centre force to ~0.3 (Forces → Centre force)

**Navigation**
- Click any node to open its note
- Each note links to the papers it connects to via `[[wikilinks]]`
- GAP.md contains the full gap argument table with all 13 exposing papers
- THESIS.md contains the full system architecture, hypotheses, and chapter map

---

## How it was built

1. **Relationship vocabulary defined** — six typed edge types based on the conceptual roles sources play in the thesis argument
2. **Structured CSV generated** — 59 sources verified against the actual thesis bibliography, with metadata, domain tags, role, typed connections, and three synthesis fields per source
3. **Vault generated** — Claude Code converted the CSV into individual `.md` files with YAML frontmatter and `[[wikilinks]]`
4. **Special nodes written manually** — `GAP.md` and `THESIS.md` represent concepts rather than papers and were authored by hand
5. **Graph validated iteratively** — colour groups and edge directions verified against the thesis argument and actual reference list

---

## Thesis prototype

The HITL-CDT prototype evaluated in this thesis is at:
[github.com/bjorkeen/master-thesis-prototype](https://github.com/bjorkeen/master-thesis-prototype)

---

## References

The full reference list (59 sources) with citation details is in the thesis document. Each source note in this vault includes the full title, authors, and year in its YAML frontmatter.

---

*MSc Thesis · University of Macedonia · Department of Applied Informatics · 2025–2026*
