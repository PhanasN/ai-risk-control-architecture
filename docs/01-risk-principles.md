# Risk Principles

This document defines how risk is classified and reasoned about across an AI system, before any control or escalation design is discussed.

## Core principle

AI risk is not primarily a model-quality problem. A model can be statistically accurate and still produce unsafe or indefensible outcomes if the surrounding decision structure is unclear.

Risk should be evaluated at three levels:

1. **Model risk** - the likelihood the model output is wrong, biased, or degraded.
2. **Control risk** - the likelihood that a wrong output is not caught, escalated, or corrected in time.
3. **Dependency risk** - the likelihood that the system fails because of a single vendor, pipeline, or data source it cannot easily replace.

## Classification questions

For any AI system, ask:

- Who is accountable if this decision is wrong?
- What evidence exists to explain why the system acted?
- What is the blast radius if this fails silently for a week?
- Can this decision be reversed, and how quickly?
- Does this system depend on a single provider, model, or dataset that cannot be replaced quickly?

## Risk tiers

| Tier | Description | Example |
|---|---|---|
| Low | Reversible, low-impact, human-reviewed before action | Draft content suggestions |
| Medium | Limited automation, partial reversibility | Automated customer replies with override |
| High | Autonomous action, high impact, hard to reverse | Automated credit or risk decisions |

## Why this matters

A system without a clear risk tier cannot be given a proportionate control. Over-controlling a low-risk system wastes resources. Under-controlling a high-risk system creates exposure that is often invisible until an incident occurs.

The rest of this repository builds on this classification: control framework design, ownership, escalation, traceability, and MLOps control points all depend on knowing which tier a system sits in.
