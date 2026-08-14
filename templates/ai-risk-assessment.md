# AI Risk Assessment Template

Use this template to assess a single AI system or workflow before launch, and re-run it whenever the system changes materially.

## 1. System overview

- System name:
- Business purpose:
- Decision(s) it makes or influences:
- Is the decision automated, human-reviewed, or human-in-the-loop:

## 2. Risk classification

See 01-risk-principles.md for definitions.

- Model risk (likelihood output is wrong/biased/degraded): Low / Medium / High
- Control risk (likelihood a wrong output goes uncaught): Low / Medium / High
- Dependency risk (reliance on a single vendor/model/dataset): Low / Medium / High
- Overall risk tier: Low / Medium / High

## 3. Impact if wrong

- Who is affected if this system makes a wrong decision?
- What is the financial, legal, or reputational impact?
- Is the decision reversible, and how quickly?

## 4. Controls in place

- Preventive controls:
- Detective controls:
- Corrective controls:
- Are these controls proportionate to the risk tier above? Yes / No, explain:

## 5. Ownership

- Decision owner:
- Operational owner:
- Escalation owner:
- Has ownership been confirmed directly with each person? Yes / No

## 6. Traceability

- Is every decision logged with input reference, model version, output, and confidence? Yes / No
- Can a specific past decision be reproduced and explained on request? Yes / No

## 7. Sign-off

- Assessed by:
- Date:
- Next review date:
- Approved by (for High risk tier systems):
