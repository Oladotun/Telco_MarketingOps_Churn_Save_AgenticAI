# Future Improvements

This prototype is intentionally lightweight. The items below describe what would make the system more credible as an enterprise reference architecture, without implying that the current notebook is production-ready.

## Data And Decisioning

- Replace synthetic subscriber records with governed CRM, billing, service, contract, usage, and care-interaction data.
- Add a calibrated churn-risk model with clear feature lineage, monitoring, and retraining controls.
- Separate churn likelihood from saveability, customer value, and offer responsiveness.
- Add richer risk-driver taxonomy for price sensitivity, service dissatisfaction, device need, network experience, and competitor pull.

## Offer Strategy And Controls

- Move offer catalog, eligibility rules, margin thresholds, and regulatory caps into versioned policy/configuration files.
- Add approval workflows for offer changes, margin-floor overrides, and exceptional save actions.
- Add contact-policy controls for consent, frequency caps, suppressed customers, vulnerable customers, and channel eligibility.
- Track customer-treatment fairness across segments, geographies, plans, and tenure bands.

## Structured Outputs

- Replace free-form JSON parsing with typed schemas and validation.
- Add retries for malformed model responses.
- Record parse failures as reviewable system events.
- Validate the selected offer key, rationale, and generated message before any downstream workflow can use them.

## Evaluation

- Expand beyond the seven synthetic subscriber archetypes.
- Add counterfactual test cases for low-risk customers, high-value margin conflicts, service-driven churn, in-contract subscribers, and missing-data scenarios.
- Track expected value, incremental save rate, offer cost, deadweight spend, margin leakage, complaint rate, and opt-out rate.
- Separate development examples from holdout evaluation cases.

## Operational Readiness

- Add API-key validation, timeouts, retries, and rate-limit handling.
- Add persistent logging for inputs, prompts, model versions, intermediate decisions, selected offers, generated messages, and human overrides.
- Package the workflow as a small service or internal retention workbench.
- Add monitoring for model drift, offer mix drift, approval-rate changes, and guardrail failures.

## Human Workflow

- Add a human-in-the-loop review interface for high-cost, high-risk, or exception cases.
- Route low-risk `NO_OFFER` decisions to monitoring rather than customer outreach.
- Route service-driven churn to care recovery workflows instead of pure discounting.
- Capture frontline rep feedback and customer outcomes for continuous improvement.

## Client-Facing Extensions

- Turn the notebook into a reference architecture diagram.
- Add a short demo video or walkthrough.
- Create a companion blog post explaining the strategy, implementation, and production considerations.
- Reuse the same pattern for broadband retention, streaming subscription save desks, device upgrade programs, and customer-care next-best-action workflows.
