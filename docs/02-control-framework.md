# Control Framework

A control is a mechanism that catches, limits, or corrects a risky outcome before it causes lasting harm. This document defines the control layers that should exist around any AI system, mapped to the risk tiers in risk-principles.md.

## Control layers

1. **Preventive controls** - stop a bad action before it happens. Examples: input validation, permission checks, confidence thresholds that block low-confidence actions.
2. **Detective controls** - identify that something went wrong. Examples: monitoring, drift detection, anomaly alerts, logging of decisions and inputs.
3. **Corrective controls** - fix or contain the damage after detection. Examples: rollback procedures, kill switches, human override paths.

## Mapping controls to risk tier

| Risk tier | Minimum control expectation |
|---|---|
| Low | Logging and periodic review |
| Medium | Preventive checks plus monitoring, human override available |
| High | All three layers active, human-in-the-loop before irreversible actions |

## Designing a control, not just naming one

A control is not real until three questions can be answered:

- **Trigger** - what condition activates this control?
- **Owner** - who is notified or who acts when it triggers?
- **Response time** - how quickly must action be taken once triggered?

A control without an owner is a policy statement, not a control.

## Common failure pattern

The most common governance failure is not the absence of a control. It is a control that exists in documentation but was never wired into the actual workflow, so it never fires in practice. Controls should be tested the same way code is tested: does the trigger actually fire, does the right person actually get notified, and does the response actually happen within the expected time.

## Relationship to the rest of this repository

This framework depends on clear ownership (see 03-ownership-and-accountability.md) and produces the evidence trail described in 05-traceability-and-evidence.md. Without both, a control framework looks complete on paper but cannot be verified during an incident or audit.
