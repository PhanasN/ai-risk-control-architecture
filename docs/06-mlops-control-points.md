# MLOps Control Points

This document maps the general control framework onto the concrete stages of an MLOps pipeline, since this is where many of the abstract principles in this repository become specific engineering decisions.

## Pipeline stages and their control points

1. **Data ingestion** - validate schema, freshness, and source authenticity before data enters training or inference. Control: reject or quarantine malformed or stale data automatically.
2. **Feature engineering** - track feature lineage so any feature can be traced back to its raw source. Control: version feature definitions alongside model versions.
3. **Training** - record training data snapshot, hyperparameters, and evaluation metrics for every training run. Control: block promotion of a model that regresses on key metrics versus the current production model.
4. **Validation** - test against held-out data and, where relevant, fairness and robustness checks. Control: require sign-off before a model can be promoted to production, proportional to the risk tier.
5. **Deployment** - use staged rollout rather than full replacement. Control: canary or shadow deployment with automatic rollback on error-rate or drift thresholds.
6. **Monitoring** - track prediction drift, data drift, and performance decay continuously, not only at deployment time. Control: alert when drift crosses a defined threshold, tied to an owner from 03-ownership-and-accountability.md.
7. **Retraining and retirement** - define the conditions under which a model must be retrained or retired. Control: set a maximum model age or performance floor after which retraining is mandatory, not optional.

## Why MLOps needs this mapping

MLOps tooling makes it easy to automate a pipeline end to end. Automation without control points simply means that a bad decision propagates faster and further before anyone notices. Each stage above should have an explicit answer to: what could go wrong here, and what stops it from reaching production or a real decision.

## Relationship to the rest of this repository

This document is the applied layer. The risk tiers in 01-risk-principles.md determine how strict each control point needs to be, and the evidence produced at each stage feeds the traceability requirements in 05-traceability-and-evidence.md.
