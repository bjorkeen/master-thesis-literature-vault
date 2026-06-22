---
title: A Unified Approach to Interpreting Model Predictions (SHAP)
authors: Lundberg S.M. / Lee S.-I.
year: 2017
tags:
  - XAI
  - SHAP
  - FeatureAttribution
role: xai_method
---

## What it is
Introduces SHAP — a unified framework for model-agnostic feature attribution based on Shapley values from cooperative game theory.

## Why it matters for the thesis
The direct methodological basis for the explainability layer. Every /explain/{incident_id} call uses SHAP. Without this paper the XAI component lacks theoretical grounding.

## What it leaves open
Algorithm paper — does not address human decision behaviour or operational contexts.

## Where it appears
Chapter 4 Implementation. SHAP method justification.

## Connections
- ENABLES [[arrieta2020]]
