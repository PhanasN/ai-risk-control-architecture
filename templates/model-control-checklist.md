# Model Control Checklist

Use this checklist before promoting a model to production, and again at each scheduled review. Map each item to the MLOps stages in 06-mlops-control-points.md.

## Data

- [ ] Training data source and collection period documented
- [ ] Data quality checks passed (completeness, duplicates, schema)
- [ ] Known biases or gaps in the data documented
- [ ] Data lineage recorded from raw source to feature

## Training and validation

- [ ] Training run recorded with hyperparameters and code version
- [ ] Model evaluated against held-out test data, not just training data
- [ ] Performance compared against the current production model
- [ ] Fairness/robustness checks run where relevant to the use case
- [ ] Evaluation metric matches the business problem (not accuracy alone for imbalanced outcomes)

## Deployment readiness

- [ ] Rollback procedure defined and tested
- [ ] Canary or staged rollout plan in place
- [ ] Confidence or risk thresholds defined for routing to human review
- [ ] Model version tagged and tied to logging/traceability system

## Ownership and sign-off

- [ ] Decision owner has approved promotion to production
- [ ] Operational owner identified and briefed
- [ ] Escalation path confirmed and tested

## Post-deployment

- [ ] Monitoring dashboard live for drift and error rate
- [ ] Alert thresholds configured and tied to an owner
- [ ] Retraining or retirement criteria defined
- [ ] Next scheduled review date set

## Notes

Use this section to record exceptions, known limitations, or conditions attached to this approval.
