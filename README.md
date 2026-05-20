# Telco Marketing Ops Churn Save Agentic (Multi Agent) System

This project is a technology, media, and telecom agentic AI prototype for churn-save decisioning. It demonstrates how a policy-first multi-agent workflow can help a retention team choose a commercially defensible save action for at-risk subscribers.

The goal is not to replace retention strategy, billing systems, or campaign governance. The goal is to show how agentic AI can structure retention work, apply deterministic margin and eligibility controls, and generate a compliant customer or operations message for human review.

## What This Builds

The notebook implements a churn-save workflow:

```text
At-Risk Subscriber
  -> Eligibility + Margin Agent
  -> Offer Match Agent
  -> Message Agent
  -> Recommended Save Action
```

The workflow uses:

- Deterministic offer eligibility, margin-floor, and regulatory-cap checks
- LLM-based judgment for selecting the cheapest effective approved offer
- LLM-based drafting for compliant retention messages or internal monitoring notes
- LangGraph for workflow orchestration
- Synthetic at-risk subscriber profiles and an approved offer catalog
- A small evaluation step to test margin, over-discounting, and directional appropriateness

## Why This Exists

Telco retention teams face a persistent commercial challenge: save valuable subscribers without giving costly incentives to customers who would have stayed anyway. A useful AI system in this domain should be bounded, auditable, and designed around clear separation between policy controls and judgment calls.

This prototype explores that pattern. It puts deterministic finance, eligibility, and regulatory gates before the LLM can choose an offer, so the model can optimize within an approved action space without breaching margin or treatment rules.

## Repository Structure

```text
.
|-- README.md
|-- requirements.txt
|-- LICENSE
|-- tmt_telco_churn_save_agent.ipynb
`-- docs/
    |-- architecture.md
    `-- future_improvements.md
```

## How To Run

1. Create and activate a Python virtual environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Add a `.env` file with your OpenAI API key in this folder or a parent folder:

```bash
OPENAI_API_KEY=your_api_key_here
```

4. Open and run `tmt_telco_churn_save_agent.ipynb`.

## Current Limitations

- The subscriber data and offer catalog are synthetic and intentionally small.
- The notebook assumes a churn-risk score already exists for each subscriber.
- This is not connected to CRM, billing, campaign management, or care systems.
- The offer strategy is represented as prototype data and prompts, not production policy.
- LLM outputs are parsed from JSON text rather than enforced with a production schema.
- The evaluation is a prototype sanity check, not a statistically valid uplift or churn model evaluation.

## AI-Native Build Workflow

This project is part of a build-in-public agentic AI lab. Tools such as Codex, Claude Code, and Sapient Slingshot may be used selectively to support implementation, review, documentation, debugging, and iteration.

The architecture, domain framing, controls thinking, and final engineering decisions remain human-led.

## Disclaimer

This repository is for educational and demonstration purposes only. It is not legal, regulatory, pricing, marketing, or customer-treatment advice, and it should not be used as a production retention system without appropriate controls, testing, validation, governance, and expert review.
