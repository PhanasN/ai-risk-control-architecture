# Traceability and Evidence

A control is only defensible if it produces evidence that can be reviewed after the fact. This document defines what should be logged and how it should be structured so it holds up under audit, regulatory review, or board scrutiny.

## What traceability means

Traceability is the ability to answer, for any AI decision, the following without guessing:

- What input did the system receive?
- What version of the model or logic produced the output?
- What output was produced, and with what confidence?
- Did a human review or override the decision, and who?
- What downstream action was taken as a result?

If any of these cannot be answered after the fact, the system is not traceable, regardless of how well it performs.

## Minimum evidence set

For high-risk systems, log at minimum:

1. Timestamp and unique decision ID.
2. Model or system version identifier.
3. Input data reference (not necessarily raw sensitive data, but a reference or hash).
4. Output and confidence score.
5. Any control that fired, and the outcome of that control.
6. Human review status, if applicable.

## Common traceability failures

- Logs exist but are not searchable by decision ID, making incident review slow.
- Model versioning is not tied to the logs, so it is unclear which version produced a given output.
- Logs capture the output but not the input, making it impossible to reproduce or explain the decision later.
- Retention periods are shorter than the regulatory or contractual requirement.

## Why this matters more than it seems

In a dispute, audit, or regulatory inquiry, the question is rarely "was the model good." It is "can you show me what happened and why." Traceability is what converts a defensible design on paper into a defensible answer when someone actually asks.

## Relationship to the rest of this repository

Traceability is the evidence layer underneath the control framework (02-control-framework.md) and the escalation process (04-escalation-and-incident-response.md). Without it, both of those remain unverifiable claims.
