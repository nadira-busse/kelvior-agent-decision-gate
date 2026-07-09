---
document_id: KEL-SRC-MANIFEST-001
title: Kelvior Foundry IQ Evidence Source Manifest
version: "1.0"
source_type: source_manifest
mvp_source_set: Kelvior Agent Decision Gate Foundry IQ Source Set
physical_upload_scope: single_foundry_iq_knowledge_base
evidence_type: source_manifest
project: Kelvior Agent Decision Gate
data_status: synthetic
confidentiality: public_demo_safe
last_updated: 2026-06-12
---

# Kelvior Foundry IQ Evidence Source Manifest

Document ID: KEL-SRC-MANIFEST-001

Document title: Kelvior Foundry IQ Evidence Source Manifest

Foundry IQ source document: 00_evidence_source_manifest.md

Evidence role: Authoritative source manifest for document identity, source filenames and evidence roles in the Kelvior Agent Decision Gate Foundry IQ source set.

Evidence source: KEL-SRC-MANIFEST-001 — 00_evidence_source_manifest.md

---

## 1. Purpose

This manifest defines the authoritative mapping between Foundry IQ source documents, document IDs, document titles and evidence roles for the Kelvior Agent Decision Gate source set.

It supports audit traceability, source attribution and document identity consistency across retrieval, reasoning and evidence-pack generation.

This manifest is the MVP retrieval-visible source identity registry for the Foundry IQ knowledge base. In a production implementation, the same mapping would be enforced through chunk-level metadata fields in the Azure AI Search or Foundry IQ ingestion pipeline.

Evidence source: KEL-SRC-MANIFEST-001 — 00_evidence_source_manifest.md

---

## 2. Source Document Registry

| Foundry IQ source document               | Document ID        | Document title                           | Evidence role                                                                                                                         |
| ---------------------------------------- | ------------------ | ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| 01_kelvior_enterprise_context_excerpt.md | KEL-ENT-CTX-001    | Kelvior Enterprise Context Excerpt       | Enterprise context defining business units, departments, processes, systems, Foundry IQ knowledge architecture and MCP connectors     |
| 02_kelvior_ai_policy.md                  | KEL-DAI-AIPOL-001  | Kelvior AI Policy                        | AI governance policy evidence for deployment readiness assessments                                                                    |
| 03_kelvior_data_governance_policy.md     | KEL-DAI-DGOV-001   | Kelvior Data Governance Policy           | Data governance policy evidence for classification, permitted use, review requirements, data stewardship and restricted data handling |
| 04_kelvior_security_policy.md            | KEL-SEC-SECPOL-001 | Kelvior Security Policy                  | Security policy evidence for access control, least privilege, audit logging, monitoring, incident response and MCP-connected agents   |
| 05_agent_approval_procedure.md           | KEL-DAI-APPROC-001 | Kelvior Agent Approval Procedure         | Approval procedure evidence for pilot, conditional production, full production, re-audit gates and required sign-offs                 |
| 06_enterprise_risk_register_excerpt.md   | KEL-RISK-EXC-001   | Kelvior Enterprise Risk Register Excerpt | Risk register evidence for mapping readiness findings to explicit Kelvior risk IDs                                                    |
| 07_finance_invoice_assistant_evidence.md | KEL-AGT-FIN-001    | Finance Invoice Assistant Evidence       | Agent-specific evidence for Finance Invoice Assistant readiness assessment                                                            |
| 08_it_ticket_triage_evidence.md          | KEL-AGT-ITO-001    | IT Ticket Triage Agent Evidence          | Agent-specific evidence for IT Ticket Triage readiness assessment                                                                     |
| 09_learning_policy_coach_evidence.md     | KEL-AGT-ACD-001    | Learning Policy Coach Evidence           | Agent-specific evidence for Learning Policy Coach readiness assessment                                                                |
| 10_sales_proposal_agent_evidence.md      | KEL-AGT-SAL-001    | Sales Proposal Agent Evidence            | Agent-specific evidence for Sales Proposal Agent readiness assessment                                                                 |
| 11_hr_onboarding_helper_evidence.md      | KEL-AGT-HRO-001    | HR Onboarding Helper Evidence            | Agent-specific evidence for HR Onboarding Helper readiness assessment                                                                 |

Evidence source: KEL-SRC-MANIFEST-001 — 00_evidence_source_manifest.md

---

## 3. Source Attribution Rule

For evidence-pack generation, document identity must be taken from one of the following sources, in order of preference:

1. explicit `document_id` or `Document ID` in the retrieved evidence document;
2. the authoritative mapping in this source manifest;
3. document metadata supplied by the retrieval or indexing layer.

If a retrieved Foundry IQ source document appears in Section 9, the Document ID must match the mapping in this manifest.

A Foundry IQ source filename is not a Document ID.

Knowledge Base IDs such as KB-DAI, KB-CORP, KB-HR, KB-FIN, KB-IT, KB-OPS, KB-SUP and KB-PROD are not Document IDs.

Evidence source: KEL-SRC-MANIFEST-001 — 00_evidence_source_manifest.md

---

## 4. Explicit Invalid Document IDs

The following values are not valid Document IDs for the Kelvior Agent Decision Gate Foundry IQ source set:

| Invalid value                            | Reason                             | Correct value                 |
| ---------------------------------------- | ---------------------------------- | ----------------------------- |
| 01_kelvior_enterprise_context_excerpt.md | Filename, not Document ID          | KEL-ENT-CTX-001               |
| 02_kelvior_ai_policy.md                  | Filename, not Document ID          | KEL-DAI-AIPOL-001             |
| 03_kelvior_data_governance_policy.md     | Filename, not Document ID          | KEL-DAI-DGOV-001              |
| 04_kelvior_security_policy.md            | Filename, not Document ID          | KEL-SEC-SECPOL-001            |
| 05_agent_approval_procedure.md           | Filename, not Document ID          | KEL-DAI-APPROC-001            |
| 06_enterprise_risk_register_excerpt.md   | Filename, not Document ID          | KEL-RISK-EXC-001              |
| KEL-RISK-REG-001                         | Not used in this source set        | KEL-RISK-EXC-001              |
| KB-DAI                                   | Knowledge Base ID, not Document ID | Use mapped source document ID |
| KB-CORP                                  | Knowledge Base ID, not Document ID | Use mapped source document ID |
| KB-HR                                    | Knowledge Base ID, not Document ID | Use mapped source document ID |
| KB-FIN                                   | Knowledge Base ID, not Document ID | Use mapped source document ID |
| KB-IT                                    | Knowledge Base ID, not Document ID | Use mapped source document ID |
| KB-OPS                                   | Knowledge Base ID, not Document ID | Use mapped source document ID |
| KB-SUP                                   | Knowledge Base ID, not Document ID | Use mapped source document ID |
| KB-PROD                                  | Knowledge Base ID, not Document ID | Use mapped source document ID |

Evidence source: KEL-SRC-MANIFEST-001 — 00_evidence_source_manifest.md

---

## 5. Production Implementation Note

In this MVP, the source manifest provides retrieval-visible document identity mapping.

In a production implementation, this mapping would be enforced through chunk-level metadata fields in the Azure AI Search or Foundry IQ ingestion pipeline, including:

- document_id
- source_document
- document_title
- evidence_role
- version
- source_set
- classification
- confidentiality
- logical_knowledge_base
- retrieval_scope

Production ingestion should preserve document identity at chunk level so citations, Section 9 evidence references and audit outputs do not depend on model inference or filename reconstruction.

Evidence source: KEL-SRC-MANIFEST-001 — 00_evidence_source_manifest.md
