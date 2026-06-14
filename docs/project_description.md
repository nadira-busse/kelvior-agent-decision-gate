# Project Description — Kelvior Agent Decision Gate

## Project name

Kelvior Agent Decision Gate

## Challenge track

Microsoft Agents League Hackathon — Reasoning Agents Track

## Short description

Kelvior Agent Decision Gate is a Microsoft Foundry reasoning agent that evaluates whether enterprise AI agents are ready for deployment.

The agent uses Foundry IQ-grounded Kelvior governance, security, policy, process and risk evidence to produce a structured 14-section Agent Deployment Evidence Pack with one of four verdicts:

- `GO`
- `CONDITIONAL GO`
- `REMEDIATE`
- `BLOCK`

The project demonstrates how enterprise AI-agent governance can be handled through evidence-grounded reasoning instead of informal manual review.

---

## Problem solved

Enterprise AI agents can be created faster than governance, security and risk teams can review them.

This creates practical deployment risks:

- unclear business ownership
- missing data governance review
- missing security review
- uncontrolled system or MCP connector access
- missing audit logging
- weak human approval gates
- unclear escalation paths
- no structured evidence trail for deployment decisions
- agents being used outside their approved purpose or data scope

Kelvior Agent Decision Gate solves this by acting as a pre-deployment reasoning gate.

It does not deploy agents automatically. It produces an evidence-based assessment that supports human governance review and deployment decision-making.

---

## What the solution does

The Decision Gate evaluates AI-agent readiness across five audit domains:

| Domain     | Weight | Purpose                                                                                                                                       |
| ---------- | -----: | --------------------------------------------------------------------------------------------------------------------------------------------- |
| Inventory  |    15% | Checks whether the agent identity, owners, business unit, process, systems, MCP connectors, allowed actions and deployment scope are defined. |
| Governance |    25% | Checks ownership, accountability, approval status, human approval gates, monitoring, audit logging and review controls.                       |
| Security   |    25% | Checks security review, access control, least privilege, controlled actions, incident response, logging and monitoring.                       |
| Policy     |    20% | Checks alignment with Kelvior AI policy, data governance policy, security policy and approval procedure.                                      |
| Process    |    15% | Checks business-process alignment, operational boundaries, exception handling, escalation paths and human-in-the-loop controls.               |

The agent then applies:

- mandatory blocking rules
- weighted readiness scoring
- score caps for limited or conditional deployments
- risk assessment
- source-grounded evidence references
- misuse-prevention checks
- human approval checklist
- remediation planning
- re-audit recommendations

---

## Core features

### 1. Microsoft Foundry reasoning agent

The core of the project is one Microsoft Foundry reasoning agent: **Kelvior Agent Decision Gate**.

The agent performs multi-step deployment readiness assessment using retrieved evidence, scoring logic, mandatory blocking rules and risk reasoning.

### 2. Foundry IQ evidence grounding

Foundry IQ is used as the knowledge grounding layer.

The project uses Foundry IQ to ground the reasoning agent in multiple synthetic Kelvior enterprise evidence sources, including enterprise context, AI policy, data governance policy, security policy, approval procedure, enterprise risk register and agent-specific evidence documents.

For the MVP, these enterprise sources are represented as retrieval-optimized Markdown documents. In a production implementation, the same pattern could connect to governed enterprise repositories such as SharePoint, policy libraries, risk systems, HR systems, CRM systems or indexed document stores with scoped retrieval permissions.

The agent retrieves Kelvior governance and agent evidence before generating a full assessment. This keeps the output tied to project-specific source evidence instead of relying on generic model knowledge.

### 3. Evidence Source Manifest

The source set includes an Evidence Source Manifest that maps Foundry IQ source documents to canonical document IDs, titles and evidence roles.

This improves traceability and reduces the risk of invented or inconsistent document references.

### 4. 14-section Agent Deployment Evidence Pack

Each full assessment produces a structured Evidence Pack with exactly 14 sections:

1. Agent summary
2. Business context
3. Systems and MCP connectors
4. Data classification
5. Audit domain scores
6. Weighted readiness score
7. Mandatory blocking rule evaluation
8. Findings by domain
9. Evidence references
10. Risk assessment
11. Deployment verdict
12. Required remediation plan
13. Human approval checklist
14. Re-audit recommendation

### 5. Guardrails and safety logic

The Decision Gate includes guardrails for:

- mandatory BLOCK conditions
- missing governance controls
- missing data governance review
- missing security review
- disabled audit logging
- missing human approval gates
- uncontrolled write or controlled actions
- missing escalation or incident response paths
- invented risk IDs
- invented document IDs
- misuse outside approved scope, process, data or allowed actions

### 6. Ingestion Security and Ethics Layer

The architecture includes an Ingestion Security and Ethics Layer before retrieval and reasoning.

In the MVP, this is represented as an architecture layer and lightweight validation concept. It covers sensitivity labels, allowed data scope validation, input sanitization and misuse-prevention checks.

Production enforcement would require Microsoft Purview sensitivity labels, Azure RBAC, managed identities, scoped retrieval permissions and policy-driven access control.

---

## Demo scenarios

The project includes five validated Kelvior AI-agent assessment scenarios.

| Agent                     | Verdict          | Purpose                                                                                                                                 |
| ------------------------- | ---------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| Finance Invoice Assistant | `BLOCK`          | Demonstrates blocking behavior for a financial workflow with mandatory governance, security, data, approval and process control gaps.   |
| IT Ticket Triage          | `GO`             | Demonstrates approval of a controlled, read-only, recommendation-only IT agent with complete governance evidence.                       |
| HR Onboarding Helper      | `REMEDIATE`      | Demonstrates remediation behavior for a high-risk HR agent in pre-production with restricted HR data and missing foundational controls. |
| Learning Policy Coach     | `CONDITIONAL GO` | Demonstrates conditional approval for an internal learning-support agent with controlled rollout requirements.                          |
| Sales Proposal Agent      | `CONDITIONAL GO` | Demonstrates commercial misuse prevention for sales proposal drafting, discounts, binding offers and human approval requirements.       |

The primary demo focuses on:

* Finance Invoice Assistant → `BLOCK`
* IT Ticket Triage → `GO`
* HR Onboarding Helper → `REMEDIATE`

This contrast shows that the system does not simply block all agents. It evaluates evidence, controls, deployment scope and operational readiness before assigning a verdict.

---

## Technologies used

- Microsoft Foundry
- Foundry IQ
- Azure AI Search-backed retrieval tool/resource provisioned through Foundry IQ
- Multiple synthetic Kelvior enterprise evidence sources
- YAML agent definitions
- Retrieval-optimized Markdown evidence documents
- Evidence Source Manifest
- Mermaid architecture diagrams
- GitHub

---

## Architecture summary

The solution follows this flow:

```text
Agent definitions + governance evidence
→ Ingestion Security and Ethics Layer
→ Foundry IQ Knowledge Base
→ Evidence retrieval layer
→ Microsoft Foundry Reasoning Agent
→ Agent Deployment Evidence Pack
→ Human governance review / deployment decision support
```

The key design decision is that audit domains, score caps, blocking rules, risk assessment and evidence traceability are internal reasoning controls of the Microsoft Foundry agent.

They are not separate external audit services.

---

## Repository structure

```text
agent_definitions/
  YAML source definitions for each evaluated agent

agent_instructions/
  Microsoft Foundry reasoning agent instruction

foundry_iq_sources/
  Retrieval-optimized Markdown evidence source set for Foundry IQ

outputs/
  Sample Agent Deployment Evidence Packs generated by the Decision Gate

docs/
  Architecture overview, architecture diagram and project description
```

---

## Why this matters

Enterprise AI-agent deployment needs more than a working prompt or prototype.

A deployment decision needs evidence:

- Who owns the agent?
- What process does it support?
- What systems and connectors does it use?
- What data can it access?
- Are security and data reviews complete?
- Are human approval gates in place?
- Are risks triggered, mitigated or not applicable?
- Is the agent being used only within its approved scope?
- Is the agent operating within legal and ethical boundaries for its deployment context?

Kelvior Agent Decision Gate turns those questions into a repeatable reasoning workflow.

The result is a structured decision-support artifact that governance, security, data, risk and business stakeholders can review before deployment or rollout expansion.

---

## MVP boundary and production path

This hackathon MVP demonstrates the reasoning, grounding, traceability and governance pattern for enterprise AI-agent deployment readiness assessment.

It is not a full production enforcement system.

The current implementation focuses on:

- evidence-grounded reasoning through Foundry IQ
- structured deployment-readiness assessment
- mandatory blocking rules
- weighted readiness scoring and score caps
- source traceability through the Evidence Source Manifest
- ethics and misuse-prevention checks
- human governance review and deployment decision support

The MVP does not implement:

- live production enforcement
- real-time Microsoft Purview policy enforcement
- custom Azure AI Search indexing pipelines
- production metadata-filtered retrieval permissions
- live MCP action enforcement
- automated approval workflows
- enterprise audit trail storage
- live CRM, ERP, HR or ITSM system actions
- production-grade ethics policy enforcement

A production version would add:

- Microsoft Purview sensitivity labels
- Azure RBAC
- managed identities
- scoped retrieval permissions
- Azure AI Search / Foundry IQ metadata filters
- policy-as-code validation
- approval workflow integration
- audit trail and run history
- stronger ingestion validation
- automated evidence freshness checks

The MVP proves the decision pattern first: governed evidence enters the retrieval layer, the Microsoft Foundry reasoning agent evaluates deployment readiness, and the output supports human governance review.

---

## Synthetic enterprise environment

Kelvior Systems is a fictional enterprise simulation environment.

All business units, departments, systems, employees, customers, vendors, policies, processes, evidence documents and assessment outputs are synthetic.

No real confidential, customer, employee or vendor data is included.
