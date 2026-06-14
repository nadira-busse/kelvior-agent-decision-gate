# Foundry IQ Source Set

This folder contains the focused Foundry IQ source set for the Kelvior Agent Decision Gate hackathon submission.

## Purpose

The source set provides grounded enterprise evidence for a Microsoft Foundry reasoning agent that evaluates AI-agent deployment readiness across five audit domains:

- Inventory
- Governance
- Security
- Policy
- Process

The MVP uses one physical Foundry IQ knowledge base for submission efficiency. Enterprise knowledge boundaries are preserved through document-level metadata, including:

- `kb_id`
- `mvp_source_set`
- `physical_upload_scope`
- `logical_kb_role`
- `primary_domains`
- `secondary_domains`
- `evidence_type`

## Upload Sources

The following documents are intended for the Foundry IQ upload set:

| File | Role |
| --- | --- |
| `00_evidence_source_manifest.md` | Source registry for document IDs, titles, evidence roles and Foundry IQ source mapping |
| `01_kelvior_enterprise_context_excerpt.md` | Enterprise context, systems, processes and logical knowledge architecture |
| `02_kelvior_ai_policy.md` | AI governance, oversight and production readiness requirements |
| `03_kelvior_data_governance_policy.md` | Data classification, source ownership and sensitive-data review requirements |
| `04_kelvior_security_policy.md` | Security review, access control, logging, monitoring and incident response requirements |
| `05_agent_approval_procedure.md` | Approval workflow, human oversight and re-audit requirements |
| `06_enterprise_risk_register_excerpt.md` | Risk evidence for finance automation, audit logging, data governance, production approval and security review gaps |
| `07_finance_invoice_assistant_evidence.md` | Agent-specific evidence for the Finance Invoice Assistant |
| `08_it_ticket_triage_evidence.md` | Agent-specific evidence for IT Ticket Triage |
| `09_learning_policy_coach_evidence.md` | Agent-specific evidence for Learning Policy Coach |
| `10_sales_proposal_agent_evidence.md` | Agent-specific evidence for Sales Proposal Agent |
| `11_hr_onboarding_helper_evidence.md` | Agent-specific evidence for HR Onboarding Helper |

## Not Uploaded to Foundry IQ

The following files are intentionally excluded from the Foundry IQ knowledge source:

- Foundry test results
- local Python validation results
- weighted scores
- expected verdicts
- actual Foundry verdicts
- portfolio matrix conclusions
- demo outputs
- root repository README

This prevents circular reasoning. The Foundry reasoning agent must derive readiness findings from evidence, not retrieve pre-written verdicts or test outcomes.

## Source Design

The agent-specific Foundry IQ evidence files are derived Markdown representations of YAML source-of-truth agent definitions.

The original YAML agent definitions remain in:

```text
agent_definitions/
```

The Foundry IQ evidence versions are stored in:

```text
foundry_iq_sources/
```

The Markdown evidence documents are optimized for retrieval and audit traceability. They include the operational facts needed for deployment readiness assessment, but intentionally exclude assessment outcomes.

The evidence documents do not include:

expected verdicts
actual verdicts
weighted scores
test results
demo results
Foundry-generated assessment outputs

This prevents circular reasoning. The reasoning agent must derive readiness findings from source evidence, not retrieve pre-written conclusions.

## Evidence Traceability

Each source document is mapped through 00_evidence_source_manifest.md.

The manifest defines the authoritative:

Document ID
Document title
Evidence role
Foundry IQ source document

The assessment output uses this mapping in Section 9 of each Agent Deployment Evidence Pack to avoid inferred document IDs, filename-based IDs or ambiguous evidence references.

## MVP Scope

The MVP Foundry IQ source set supports deployment readiness assessment for multiple representative AI-agent scenarios across different readiness outcomes.

The current source set includes:

- a high-risk finance automation BLOCK case
- an IT operations GO case
- a learning and policy support case
- a sales proposal governance case
- an HR restricted-data remediation case

This allows the Kelvior Agent Decision Gate to demonstrate consistent reasoning across different business units, systems, data classes, risk profiles and deployment readiness states.

The MVP uses a focused synthetic enterprise evidence set rather than a full enterprise knowledge base. This keeps the hackathon submission manageable while preserving the core governance, security, data, policy, process and audit logic.

## Synthetic Data Notice

All Kelvior Systems content is synthetic and created for educational, architectural, portfolio and hackathon demonstration purposes.

No confidential, customer, employee or real company information is included.