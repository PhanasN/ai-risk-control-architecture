# Ownership and Accountability

A control framework only works if every control has a named owner. This document defines how to assign and test ownership across an AI system.

## The core question

For every decision an AI system makes, someone should be able to answer without hesitation: who owns this if it goes wrong?

If the honest answer is "nobody" or "it depends," the system has an accountability gap, regardless of how good the model is.

## Three types of ownership

1. **Decision ownership** - who approved the system to make this type of decision in the first place.
2. **Operational ownership** - who monitors the system day to day and responds to alerts.
3. **Escalation ownership** - who is contacted when the operational owner cannot resolve an issue alone.

These are often three different people or roles. Conflating them is a common source of confusion during incidents.

## RACI-style mapping

For each AI system or workflow, document:

| Role | Responsible | Accountable | Consulted | Informed |
|---|---|---|---|---|
| Model owner | Yes | | | |
| Risk/compliance | | Yes | Yes | |
| On-call engineer | Yes | | | Yes |
| Business owner | | | Yes | Yes |

Accountable should map to exactly one role per decision type. Multiple "accountable" entries usually mean nobody actually feels accountable.

## Testing ownership before an incident

Ownership mapping is only real if it has been tested. A simple test: pick a plausible failure scenario and ask the named owner directly whether they know they are responsible and what they would do in the first 15 minutes. If they do not know, the mapping exists on paper only.

## Relationship to the rest of this repository

Ownership feeds directly into escalation and incident response (04-escalation-and-incident-response.md). A control cannot trigger a meaningful response if the receiving owner was never confirmed.
