# Foundry IQ Source Set

This folder contains the focused Foundry IQ source set for **Kelvior Agent Decision Gate**.

The files in this folder are retrieval-ready evidence sources for the Microsoft Foundry reasoning agent. They are not demo outputs, expected verdicts or generated Evidence Packs.

The purpose of this source set is to give the reasoning agent synthetic Kelvior enterprise evidence to retrieve before it evaluates whether an AI agent is ready for deployment.

---

## Purpose

Kelvior Agent Decision Gate evaluates AI-agent deployment readiness across five audit domains:

- Inventory
- Governance
- Security
- Policy
- Process

The Foundry IQ source set provides the evidence the agent needs for that assessment.

The source documents include governance, security, data, policy, process, risk and agent-specific evidence. The reasoning agent uses this evidence to produce an **Agent Deployment Evidence Pack** with one of four verdicts:

- `GO`
- `CONDITIONAL GO`
- `REMEDIATE`
- `BLOCK`

The verdict should be derived from evidence.

It should not be retrieved from a pre-written answer.

---

## Foundry IQ setup

The MVP uses one physical Foundry IQ knowledge base.

That choice keeps the MVP manageable. Logical evidence roles are represented through retrieval-visible document fields and source-document separation, but they are not enforced as production access boundaries in this MVP.

The evidence documents include retrieval-visible fields such as:

- `kb_id`
- `mvp_source_set`
- `physical_upload_scope`
- `logical_kb_role`
- `primary_domains`
- `secondary_domains`
- `evidence_type`

In a production implementation, these boundaries should be enforced more strongly through scoped retrieval permissions, metadata filters, access control and audit logging.

---

## Upload sources

The following documents are intended for the Foundry IQ upload set:

| File                                       | Role                                                                                                                |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------- |
| `00_evidence_source_manifest.md`           | Traceability registry for canonical document IDs, titles, evidence roles and Foundry IQ source mapping.                             |
| `01_kelvior_enterprise_context_excerpt.md` | Enterprise context, systems, processes and logical knowledge architecture.                                          |
| `02_kelvior_ai_policy.md`                  | AI governance, oversight and production-readiness requirements.                                                     |
| `03_kelvior_data_governance_policy.md`     | Data classification, source ownership and sensitive-data review requirements.                                       |
| `04_kelvior_security_policy.md`            | Security review, access control, logging, monitoring and incident-response requirements.                            |
| `05_agent_approval_procedure.md`           | Approval workflow, human oversight and re-audit requirements.                                                       |
| `06_enterprise_risk_register_excerpt.md`   | Risk evidence for finance automation, audit logging, data governance, production approval and security review gaps. |
| `07_finance_invoice_assistant_evidence.md` | Agent-specific evidence for the Finance Invoice Assistant.                                                          |
| `08_it_ticket_triage_evidence.md`          | Agent-specific evidence for IT Ticket Triage.                                                                       |
| `09_learning_policy_coach_evidence.md`     | Agent-specific evidence for Learning Policy Coach.                                                                  |
| `10_sales_proposal_agent_evidence.md`      | Agent-specific evidence for Sales Proposal Agent.                                                                   |
| `11_hr_onboarding_helper_evidence.md`      | Agent-specific evidence for HR Onboarding Helper.                                                                   |

---

## Not uploaded to Foundry IQ

The following files are intentionally excluded from the Foundry IQ knowledge source:

- Foundry test results
- local Python validation results
- weighted scores
- expected verdicts
- actual Foundry verdicts
- portfolio matrix conclusions
- demo outputs
- generated Evidence Packs
- root repository README

This prevents circular reasoning.

The reasoning agent must assess readiness from source evidence, not from retrieved test outcomes or pre-written conclusions.

---

## Source design

The agent-specific Foundry IQ evidence files are derived Markdown representations of the YAML source-controlled agent definitions.

The original YAML agent definitions remain in:

```text
agent_definitions/
```

The Foundry IQ evidence versions are stored in:

```text
foundry_iq_sources/
```

This split is intentional.

The YAML files support source control and repository traceability.

The Markdown files support retrieval in Foundry IQ.

The Markdown evidence documents include the operational facts needed for deployment-readiness assessment, but intentionally exclude assessment outcomes.

They intentionally exclude all expected or generated assessment outcomes listed above.

This keeps the retrieval layer clean.

The reasoning agent has to derive findings from evidence instead of retrieving the answer.

---

## Evidence traceability

Each source document is mapped through:

```text
00_evidence_source_manifest.md
```

The manifest defines the authoritative:

- document ID
- document title
- evidence role
- Foundry IQ source document

The reasoning-agent instruction requires Section 9 of each Agent Deployment Evidence Pack to reference sources using this mapping.

This helps prevent:

- invented document IDs
- filename-based source IDs
- ambiguous evidence references
- unsupported source claims

For the MVP, this traceability is handled through retrieval-visible Markdown.

In production, this should be strengthened with ingestion metadata, scoped access, evidence versioning and audit logs.

---

## MVP scope

The MVP Foundry IQ source set supports deployment-readiness assessment for multiple representative AI-agent scenarios.

The current source set includes evidence for:

- finance invoice automation
- IT ticket triage
- learning and policy support
- sales proposal drafting
- HR onboarding support with restricted-data considerations

The scenarios are designed to test whether the Decision Gate can reason across different:

- business units
- systems
- data classes
- risk profiles
- deployment states
- governance-control maturity levels

The source set is intentionally focused.

It is not a full enterprise knowledge base.

That boundary matters because the MVP is meant to demonstrate the evidence, retrieval and reasoning pattern before claiming production readiness.

---

## Why expected verdicts are excluded

Expected verdicts are useful for testing, but they do not belong in the Foundry IQ source set.

If expected verdicts are uploaded as retrievable evidence, the reasoning agent may learn the answer instead of performing the assessment.

That would weaken the project.

The Decision Gate should follow this chain:

```text
source evidence → finding → risk → verdict → remediation plan → re-audit
```

Not this chain:

```text
retrieved expected verdict → repeated conclusion
```

The first chain is evidence-grounded reasoning.

The second chain is circular reasoning.

---

## Relation to sample outputs

Generated sample outputs are stored outside this folder:

```text
outputs/
```

Those files show what the Decision Gate produced during testing.

They are useful for portfolio review and regression comparison.

They are not part of the Foundry IQ source set.

The source set should stay clean so the agent can be tested against evidence rather than against its own previous conclusions.

---

## Production hardening path

A production implementation would need stronger controls around source ingestion, evidence identity, retrieval scope and access control.

Required hardening would include:

- Microsoft Purview sensitivity labels
- Azure RBAC
- managed identities
- scoped retrieval permissions
- Azure AI Search / Foundry IQ metadata filters
- evidence freshness checks
- source versioning
- ingestion validation logs
- audit trail and run history
- policy-driven access control
- change management
- security review

The MVP uses Markdown evidence documents because they are practical for a focused portfolio implementation.

A production version should enforce evidence identity, access scope and retrieval boundaries through platform controls, not only through document structure.

---

## Synthetic data notice

Kelvior Systems is a fictional enterprise simulation environment.

All Kelvior Systems content is synthetic and created for educational, architectural, portfolio and demonstration purposes.

No real confidential customer, employee, vendor or company information is included.
