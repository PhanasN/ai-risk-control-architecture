# Escalation and Incident Response

A detective control is only useful if it reaches the right person fast enough to act. This document defines how escalation paths and incident response should be structured for AI systems.

## Escalation path structure

Every high-risk AI workflow should have a documented escalation path with three levels:

1. **Level 1 - Operational owner.** First responder, handles known issues within a defined playbook.
2. **Level 2 - Technical escalation.** Engaged when the issue is outside the playbook or requires a system change.
3. **Level 3 - Governance escalation.** Engaged when the issue has legal, regulatory, customer-facing, or reputational impact.

Each level should have a maximum response time. If Level 1 cannot resolve within that window, escalation to Level 2 should be automatic, not optional.

## Incident response sequence

1. **Detect** - a control fires or a person notices an anomaly.
2. **Contain** - stop the immediate harm; this may mean a kill switch, a rollback, or pausing automated decisions.
3. **Assess** - determine scope: how many decisions were affected, since when, and how severe.
4. **Notify** - inform the owners defined in 03-ownership-and-accountability.md, and external parties if required.
5. **Correct** - fix the underlying cause, not just the symptom.
6. **Document** - record what happened, using the incident-escalation-record template in this repository.

## What good escalation looks like

A good escalation path answers three questions before an incident happens, not during one:

- Who is on-call, and how are they reached at 2 a.m.?
- What is the maximum acceptable time before a Level 1 issue becomes a Level 2 issue?
- Who has authority to pause or disable the system entirely, and how long does that decision take?

## Why this matters

Most reputational damage from AI incidents does not come from the initial error. It comes from a slow, unclear, or contradictory response after the error was already known internally. A tested escalation path is what separates a contained incident from a compounding one.
