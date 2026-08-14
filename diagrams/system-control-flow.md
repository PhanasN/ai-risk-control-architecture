# System Control Flow

A text-based diagram of how a request should move through an AI system with controls attached at each stage. Use this as a reference when mapping a specific system's actual flow against this baseline.

```
REQUEST
   |
   v
INPUT VALIDATION  --(fails)-->  REJECT / QUARANTINE
   |
   v
AUTHORIZATION CHECK  --(fails)-->  BLOCK + LOG
   |
   v
MODEL / LOGIC EXECUTION
   |
   v
CONFIDENCE / RISK CHECK  --(low confidence)-->  ROUTE TO HUMAN REVIEW
   |
   v
DECISION
   |
   v
LOGGING (input ref, version, output, confidence, control outcome)
   |
   v
ACTION TAKEN
   |
   v
MONITORING (drift, error rate, anomaly detection)
   |
   +--(threshold breached)--> ESCALATION (see 04-escalation-and-incident-response.md)
```

## How to use this diagram

1. Walk an actual system through this flow and mark which stages exist today and which are missing.
2. For each existing stage, confirm it has a named owner (see 03-ownership-and-accountability.md).
3. For each missing stage, classify the gap using the risk tier of the system (see 01-risk-principles.md) to decide how urgently it needs to be closed.

## Common gaps found using this exercise

- Authorization checks exist for external users but not for internal service-to-service calls.
- Confidence thresholds exist but nothing happens when they are breached; the output is used regardless.
- Monitoring exists but is not connected to an escalation path, so breaches are visible only if someone happens to look at a dashboard.
