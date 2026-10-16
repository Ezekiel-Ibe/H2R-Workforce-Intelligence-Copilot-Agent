---
title: "HR-PTO-002 Workforce-Intelligence Copilot - Stage 5 Model"
stage: "Stage 5 - Model"
version: "0.1"
status: "Review-ready with controlled gaps"
classification: "KPMG Confidential"
language: "en-GB"
---

# Document Control

| Field | Value | Evidence |
| --- | --- | --- |
| Capability | Optimised Business Partnering | [SRC-08, section 6.3] |
| Business agent | HR-PTO-002 Workforce-Intelligence Copilot | [SRC-08, section 6.3] |
| Value stream | Measure to Reward | [SRC-08, section 3] |
| Stage objective | Model all required data within workflow steps and between workflow steps, classify availability, log gaps, and record ownership/lineage. | [SRC-01, Stage 5 Objective; SRC-01, Actions 1-10] |
| In-scope workflow steps | W-001 to W-008 | [SRC-04, Workflow Decomposition Catalogue] |
| Output file | HR-PTO-002_Workforce_Intelligence_Copilot_Stage5_Model_v0.1.md | This document |
| Prepared date | 2026-10-16 | This document |
| Prepared by | GitHub Copilot | This document |

# Contents

1. Stage 5 - Model  
2. Common Principles  
3. Key Success Factors  
4. Common Pitfalls  
5. Appendix A - Agent Directory  
6. Appendix B - ABBA/Reused Agent Assets Referenced by Workflow  
7. Appendix C - Workflow Step Data Model  
8. Appendix D - Entities Consumed by Agents  
9. Appendix E - Data Classification Summary  
10. Appendix F - Data Gap Log Summary  
11. Appendix G - Between-Step Handover Map  
12. Appendix H - Assumptions, Constraints and Open Questions  
13. Appendix I - Referenced Artefacts  
14. Appendix J - Stage 5B Handover Note

# Stage 5 - Model

## 3.1 Objective

Identify and model all data required by each workflow step, control point, and handover for Workforce-Intelligence Copilot, at both within-step and between-step levels, with explicit availability classification and lineage ownership. [SRC-01, Stage 5 Objective]

## 3.2 Model at Two Levels

### Within each workflow step

Data exchanged between agents, controls, and human participants:

- Agent and orchestration context exchange (for example W-001 to W-003).
- Deterministic compute payload and control outcomes (W-004).
- Evidence and human decision artefacts (W-005 to W-007).
- Audit and closure evidence persistence (W-008).

[SRC-01, Model at two levels; SRC-04, Workflow Decomposition Catalogue]

### Between workflow steps

Data handed from one workflow step to the next through formal handovers H-001 to H-007 with shared business keys and state attributes. [SRC-04, Handover and Interaction Register]

## 3.3 Data Classification

Classification categories used exactly as required:

- Enterprise model: already present in enterprise canonical model.
- Other source: exists in approved non-enterprise canonical source.
- Not available: currently missing from known sources.
- Agent created: generated during the workflow.
- Human provided: supplied directly by a human participant.

[SRC-01, Data classification]

## 3.4 Inputs

| Input | Usage in Stage 5 | Evidence |
| --- | --- | --- |
| Workflow steps and handovers | Defines per-step and inter-step data requirements | [SRC-04, Workflow Decomposition Catalogue; SRC-04, Handover Register] |
| Agent inventory and controls | Determines data producers, consumers, and control evidence | [SRC-04, Appendices A and B] |
| Overall AI Framework | Provides orchestration and boundaries for data flow | [SRC-04, Overall AI Framework] |
| Enterprise data model baseline | Supports canonical entity reuse and classification | [SRC-06, sections Business object families/Shared enterprise spine] |
| fabric-layer enterprise model reference | Provides layer conventions, naming, and governed mappings | [SRC-07, enterprise-data-model/config/enterprise_model.yml; SRC-07, docs/modelling-standard.md] |
| ABBA reference | Supports reuse and schema pattern reuse | [SRC-04, Appendix C] |

## 3.5 Actions (1-10) and Result

| Action | Workforce-Intelligence modelling result | Evidence |
| --- | --- | --- |
| 1. Identify input data for each agent/control | Inputs mapped for A-001 to A-008 and C-001 to C-008. | [SRC-04, Workflow Decomposition Catalogue] |
| 2. Identify data created or updated | Agent-created entities identified (for example pay_equity_result, evidence_pack). | [SRC-08, Tool catalogue; SRC-04, W-004/W-005] |
| 3. Identify data consumed by controls | Control-consumed data mapped at readiness and closure checks. | [SRC-04, D-001, D-004] |
| 4. Identify data passed to other agents | Within-step exchanges documented in Appendix C. | [SRC-04, H-001 to H-006] |
| 5. Identify data handed to next step | Handover map with shared keys produced in Appendix G. | [SRC-04, H-001 to H-007] |
| 6. Define entity, attributes, relationships | Entity and relationship catalogue defined in Appendices D and C. | [SRC-06, Relationship overview; SRC-07, modelling-standard] |
| 7. Classify data availability | Every data item classified in Appendix E. | [SRC-01, Data classification] |
| 8. Log missing data | Gaps logged as G-01 to G-08. | Appendix F |
| 9. Add missing data to model | Missing items represented as provisional entities/attributes with TBC status and ownership actions. | Appendix D; Appendix F |
| 10. Record source and ownership | Source system and owner fields included per entity/attribute where evidenced, otherwise TBC. | [SRC-06, governance and traceability; SRC-07, business glossary ownership status] |

## 3.6 Outputs

This deliverable provides:

- Data model per workflow step (Appendix C).
- Entity and attribute definitions (Appendix D).
- Relationship definitions (Appendix C relationship register).
- Data classification summary (Appendix E).
- Data gap log with integrated modelling response (Appendix F).
- Source and ownership mapping (Appendix D and C).
- Within-step and between-step data flows (Appendix C and G).

[SRC-01, Outputs]

## 3.7 Practitioner Guidance

Applied guidance in this deliverable:

- Data trace maintained from source to control to consumer.
- Entity and attribute definitions provided at practical modelling depth.
- Existence is not assumed; each item is classified.
- Missing data is logged and represented in model form.
- ABBA and enterprise references used for reuse patterns and naming consistency.
- Lineage and ownership retained explicitly.

[SRC-01, Practitioner guidance]

## 3.8 Controls and Evidence

| Control evidence requirement | Implementation in this deliverable | Evidence |
| --- | --- | --- |
| Evidence of data trace | Handover and flow registers with source and consumer columns | Appendix C and G |
| Data classification recorded | Per-item classification summary | Appendix E |
| Missing data logged and added | G-01 to G-08 with model additions/proposals | Appendix F |
| Data lineage documented | Source, record lineage and ingestion metadata requirements listed | [SRC-06, governance and traceability]; [SRC-07, sql/10_silver/001_foundation.sql] |
| Source and ownership recorded | Ownership fields included with TBC where not evidenced | Appendix D; Appendix H |

## 3.9 Exit Criteria

| Exit criterion | Status | Evidence |
| --- | --- | --- |
| Every agent has data requirements modelled | Pass | Appendix C |
| Every control has data requirements modelled | Pass | Appendix C; D-001 and D-004 data items |
| Every handover has data requirements modelled | Pass | Appendix G |
| Availability classification complete | Pass | Appendix E |
| Gaps logged and added to model | Pass | Appendix F |
| Ownership and source fully confirmed | Pending | [SRC-04, TBC ownership fields]; Appendix H |

Exit status: Partially met with controlled gaps on unresolved ownership and selected source-system confirmations.

## 3.10 Deliverable

A complete Stage 5 data model for Workforce-Intelligence Copilot, ready for Stage 5B consolidation and end-to-end validation. [SRC-01, Deliverable]

## 3.11 Key Tools

- Enterprise data model and data-object overview. [SRC-06]
- fabric-layer enterprise-data-model reference assets (model, standards, mapping, quality). [SRC-07]
- ABBA reuse assets. [SRC-04, Appendix C]
- Stage 4 handover artefacts. [SRC-04]

# Common Principles

- Model data both within and between workflow steps.
- Classify every data item.
- Log and model missing data.
- Preserve lineage, ownership, and definitions.

[SRC-01, Common principles]

# Key Success Factors

- Complete data trace from source to consumer/storage.
- Consistent entity/attribute definitions.
- Early identification and management of missing data.
- Clear handovers and control evidence.

[SRC-01, Key success factors]

# Common Pitfalls

- Missing handover payload attributes.
- Inconsistent entity names across steps.
- Assuming source availability.
- Skipping end-to-end readiness checks.

[SRC-01, Common pitfalls]

# Appendix A - Agent Directory

| Agent ID | Agent Name | Type(s) | Core data role | Evidence |
| --- | --- | --- | --- | --- |
| A-001 | Trigger and Context Capture Agent | Task, Experience | Captures leader question/reward trigger and case context. | [SRC-04, Appendix A] |
| A-002 | Workforce Evidence Assembly Agent | Task, Insight | Assembles required planning, analytics, policy, and cost data. | [SRC-04, Appendix A] |
| A-003 | Input Readiness and Comparison Control Agent | Control, Task | Validates completeness, provenance, and comparison-group controls. | [SRC-04, Appendix A] |
| A-004 | Pay Equity Computation Agent | Task, Insight | Produces deterministic pay_equity outputs and threshold flags. | [SRC-08, section 3; SRC-04, Appendix A] |
| A-005 | Evidence Pack Assembly Agent | Insight, Task | Produces cited evidence_pack payload. | [SRC-08, section 3; SRC-04, Appendix A] |
| A-006 | Workforce Intelligence Orchestrator Agent | Orchestration, Control | Coordinates routing and inter-step data handovers. | [SRC-04, Appendix A] |
| A-007 | Human Review and Decision Experience Agent | Experience, Orchestration | Captures human review decisions/refinements/escalations. | [SRC-04, Appendix A] |
| A-008 | Rationale and Approval Trail Control Agent | Control, Task | Persists rationale, approval trail, closure evidence. | [SRC-04, Appendix A] |

# Appendix B - ABBA/Reused Agent Assets Referenced by Workflow

| ABBA Asset ID | Asset Name | Relevance in Stage 5 data model | Reuse status | Evidence |
| --- | --- | --- | --- | --- |
| VA-1168 | Rewards strategy orchestrator | Orchestration payload pattern for reward workflows | Adapted | [SRC-04, Appendix C] |
| VA-1173 | Compensation workflow manager | Review/approval handover pattern | Adapted | [SRC-04, Appendix C] |
| VA-1141 | Rewards compliance monitor | Control evidence and policy-check pattern | Adapted | [SRC-04, Appendix C] |
| VA-1246 | Payroll data validator | Input validation attribute checks | Adapted | [SRC-04, Appendix C] |
| VA-1253 | Payroll experience agent | Human-facing review interaction pattern | New design in target capability | [SRC-04, Appendix C] |

# Appendix C - Workflow Step Data Model

## C.1 Per-step data model register

| Step ID | Producer(s) | Consumer(s) | Inputs consumed | Data created/updated | Control-consumed data | Within-step exchange | Next-step handover | Shared key(s) | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| W-001 | Human participant, A-001 | A-002, A-006 | leader_question_context, reward_review_trigger | workforce_decision_case (created) | case_context_completeness_flag | trigger_context_payload | H-001 | case_id | [SRC-04, W-001; SRC-04, H-001] |
| W-002 | A-002 | A-003 | workforce_plan, scenario, people_analytics, labour_cost, policy_guidance | governed_evidence_bundle (created), source_data_snapshot (updated) | provenance_trace | evidence_bundle_payload | H-002 | case_id, source_snapshot_id | [SRC-04, W-002; SRC-04, H-002] |
| W-003 | A-003 | A-004, human reviewer | governed_evidence_bundle, comparison_group_definition | readiness_status, comparator_validation_result | completeness_checks, comparator_controls | readiness_assessment_payload | H-003 | case_id, comparator_set_id | [SRC-04, W-003; SRC-04, D-001] |
| W-004 | A-004 | A-005 or A-008 | validated_comparator_data, threshold_config | pay_equity_result (created), threshold_breach_flag (created) | deterministic_formula_outcome | pay_equity_payload | H-004 or H-007 | case_id, pay_equity_result_id | [SRC-04, W-004; SRC-08, section 3] |
| W-005 | A-005 | A-007 | pay_equity_result, policy_context, decision_context | evidence_pack (created), rationale_draft (created) | citation_completeness_flag | evidence_pack_payload | H-005 | case_id, evidence_pack_id | [SRC-04, W-005; SRC-08, section 3] |
| W-006 | A-007 | Human reviewer(s), A-007 | evidence_pack | review_session_state (updated) | review_boundary_rule | review_request_payload | H-006 | case_id, evidence_pack_id | [SRC-04, W-006; SRC-04, HIP-002] |
| W-007 | Human reviewer(s), A-007 | A-008 | evidence_pack, review_session_state | human_decision_record (created), escalation_instruction (optional) | approval_boundary | decision_outcome_payload | H-006 | case_id, decision_id | [SRC-04, W-007; SRC-04, D-003] |
| W-008 | A-008 | case storage endpoint | human_decision_record or no_breach_outcome | approval_trail_record (created), case_status (updated), learning_capture (updated) | closure_completeness_check | finalisation_payload | H-007 | case_id, approval_record_id | [SRC-04, W-008; SRC-08, section 4.4] |

## C.2 Relationship register

| Relationship ID | Parent entity | Child entity | Cardinality | Linking field(s) | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| R-001 | workforce_decision_case | governed_evidence_bundle | 1:N | case_id | Proposed | [SRC-04, H-001/H-002] |
| R-002 | governed_evidence_bundle | readiness_status | 1:1 | source_snapshot_id | Proposed | [SRC-04, W-003] |
| R-003 | workforce_decision_case | pay_equity_result | 1:N | case_id | Proposed | [SRC-04, W-004] |
| R-004 | pay_equity_result | evidence_pack | 1:N | pay_equity_result_id | Proposed | [SRC-04, W-005] |
| R-005 | evidence_pack | human_decision_record | 1:N | evidence_pack_id | Proposed | [SRC-04, W-006/W-007] |
| R-006 | workforce_decision_case | approval_trail_record | 1:N | case_id | Proposed | [SRC-04, W-008; SRC-08, section 4.4] |
| R-007 | silver.worker | pay_equity_result | 1:N | worker_id | Pending - source key confirmation required | [SRC-06, active object inventory; SRC-07, sql/10_silver/070_workforce.sql] |

# Appendix D - Entities Consumed by Agents

| Entity ID | Entity name | Layer/class | Key attributes (sample) | Availability classification | Source lineage | Owner | Primary consumers | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| E-001 | silver.worker | Enterprise canonical (Silver) | worker_id, worker_number, party_id, record_source_system, record_source_id | Enterprise model | Enterprise model reference implementation | TBC - source required | A-002, A-004 | [SRC-07, sql/10_silver/070_workforce.sql; SRC-07, sql/10_silver/001_foundation.sql] |
| E-002 | compensation_record | Enterprise business object | worker_id, pay_element, amount, effective_date | Other source (canonical object referenced, physical mapping not supplied in workspace) | Enterprise business object family | TBC - source required | A-002, A-004 | [SRC-06, business object families] |
| E-003 | comparison_group_definition | Governance object | comparator_set_id, role_rule, level_rule, tenure_rule, approval_status | Not available | Required by risk control, formal source not yet supplied | Reward + HRBP (TBC) | A-003, human reviewer | [SRC-08, Risks; SRC-04, E-002] |
| E-004 | workforce_decision_case | Agent workflow object | case_id, trigger_type, decision_context, created_timestamp | Agent created | W-001 capture process | A-001 owner (TBC) | A-002 to A-008 | [SRC-04, W-001] |
| E-005 | governed_evidence_bundle | Agent workflow object | case_id, source_snapshot_id, source_references, data_quality_status | Agent created | W-002 assembly | A-002 owner (TBC) | A-003, A-004 | [SRC-04, W-002] |
| E-006 | readiness_status | Control object | case_id, completeness_status, comparator_status, control_timestamp | Agent created | W-003 validation | A-003 owner (TBC) | A-004, human reviewer | [SRC-04, W-003] |
| E-007 | pay_equity_result | Deterministic output object | pay_equity_result_id, case_id, comparison_group_id, pay_gap_pct, threshold_flag | Agent created | W-004 deterministic function | A-004 owner (TBC) | A-005, A-008 | [SRC-08, pay_equity tool; SRC-04, W-004] |
| E-008 | evidence_pack | Advisory evidence object | evidence_pack_id, case_id, gap_summary, rationale_text, citation_set | Agent created | W-005 assembly | A-005 owner (TBC) | A-007, human reviewer | [SRC-08, evidence_pack tool; SRC-04, W-005] |
| E-009 | human_decision_record | Human decision object | decision_id, case_id, decision_type, approver_identity, decision_timestamp | Human provided | W-007 decision capture | Reward + HRBP / business leader (TBC split) | A-008 | [SRC-04, W-007; SRC-08, section 4.4] |
| E-010 | approval_trail_record | Audit/governance object | approval_record_id, case_id, rationale, approver_identity, writeback_ref | Agent created | W-008 closure process | A-008 owner (TBC) | Governance/audit consumers | [SRC-08, section 4.4; SRC-04, W-008] |
| E-011 | policy_guidance_document | Policy source object | policy_id, policy_version, jurisdiction, effective_from | Other source | Policy repository (not evidenced in workspace) | Control owner (TBC) | A-002, A-005, human reviewers | [SRC-08, Inputs; SRC-04, W-002] |
| E-012 | leader_question_context | Input interaction object | requester_role, question_text, urgency, expected_decision | Human provided | W-001 intake | Human participant | A-001, A-007 | [SRC-08, Inputs; SRC-04, W-001] |

# Appendix E - Data Classification Summary

| Data item | Classification | Rationale | Evidence |
| --- | --- | --- | --- |
| silver.worker.worker_id | Enterprise model | Present in canonical silver layer implementation | [SRC-07, sql/10_silver/070_workforce.sql] |
| silver.worker.record_source_system | Enterprise model | Standard lineage fields in enterprise model | [SRC-07, sql/10_silver/001_foundation.sql] |
| compensation_record.amount | Other source | Mentioned in enterprise object overview but no local physical mapping supplied | [SRC-06, active object inventory] |
| comparison_group_definition.role_rule | Not available | Needed by risk control but explicit structured source absent | [SRC-08, Risks; SRC-04, E-002] |
| workforce_decision_case.case_id | Agent created | Created at workflow intake | [SRC-04, W-001] |
| pay_equity_result.pay_gap_pct | Agent created | Derived by deterministic pay_equity function | [SRC-08, section 3] |
| evidence_pack.rationale_text | Agent created | Produced during evidence-pack assembly | [SRC-08, section 3; SRC-04, W-005] |
| human_decision_record.approver_identity | Human provided | Captured from human decision step | [SRC-04, W-007; SRC-08, section 4.4] |
| approval_trail_record.writeback_ref | Agent created | Created in closure/audit trail recording | [SRC-08, section 4.4; SRC-04, W-008] |

# Appendix F - Data Gap Log Summary

| Gap ID | Gap description | Impacted step(s) | Resolution category | Proposed action | Owner | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- |
| G-01 | Structured comparison_group_definition source not evidenced | W-003, W-004 | Candidate for future model admission | Define comparator governance entity and steward approval | Reward + HRBP (TBC) | Open | [SRC-08, Risks; SRC-04, E-002] |
| G-02 | Ownership split between Reward + HRBP and business leaders unresolved for decision artefacts | W-007, W-008 | Governance decision required | Confirm RACI for decision_id and approver_identity ownership | Capability owner (TBC) | Open | [SRC-04, OQ-001] |
| G-03 | Source system for policy_guidance_document not evidenced in repository | W-002, W-005 | Other source registration | Register source system and ingestion metadata fields | Control owner (TBC) | Open | [SRC-04, H-002; SRC-08, Inputs] |
| G-04 | Persisted destination for approval_trail_record not confirmed | W-008 | Storage design follow-up | Confirm system-of-record endpoint and retention profile | Tech owner (TBC) | Open | [SRC-04, H-007; SRC-04, CON-003] |
| G-05 | Data steward fields are mostly TBC across key entities | W-002 to W-008 | Stewardship assignment | Complete owner/steward register in Stage 5B review | Data governance lead (TBC) | Open | [SRC-06, governance status; SRC-07, business-glossary.csv] |
| G-06 | Attribute-level lineage for labour_cost inputs not provided | W-002 | Mapping enrichment | Populate source mapping register entries | Data engineering owner (TBC) | Open | [SRC-08, Inputs; SRC-07, docs/source-mapping-register.csv] |
| G-07 | Confidence/sensitivity rule attributes not formally defined | W-004 to W-007 | Control model extension | Define risk_sensitivity_flag attributes and thresholds | Reward + HRBP (TBC) | Open | [SRC-04, OQ-003] |
| G-08 | Enterprise-model alignment for compensation/payroll entities not validated in local workspace | W-002, W-004 | Enterprise alignment validation | Reconcile with enterprise_model.yml and governance docs | Enterprise data architect (TBC) | Open | [SRC-07, config/enterprise_model.yml; SRC-06, hire-to-retire objects] |

# Appendix G - Between-Step Handover Map

| Handover ID | Source step | Target step | Shared key(s) | Data/state exchanged | Evidence |
| --- | --- | --- | --- | --- | --- |
| H-001 | W-001 | W-002 | case_id | trigger context payload | [SRC-04, H-001] |
| H-002 | W-002 | W-003 | case_id, source_snapshot_id | governed evidence bundle | [SRC-04, H-002] |
| H-003 | W-003 | W-004 | case_id, comparator_set_id | readiness pass and comparator controls | [SRC-04, H-003] |
| H-004 | W-004 | W-005 | case_id, pay_equity_result_id | threshold-breach pay-equity result | [SRC-04, H-004] |
| H-005 | W-005 | W-006 | case_id, evidence_pack_id | cited evidence pack | [SRC-04, H-005] |
| H-006 | W-006/W-007 | W-008 | case_id, decision_id | human decision outcome payload | [SRC-04, H-006] |
| H-007 | W-008 | End-state store | case_id, approval_record_id | closure and audit trail payload | [SRC-04, H-007] |

# Appendix H - Assumptions, Constraints and Open Questions

| ACO ID | Type | Statement | Impacted sections | Owner | Status | Evidence |
| --- | --- | --- | --- | --- | --- | --- |
| ACO-01 | Constraint | Ownership/stewardship fields remain partially unresolved. | D, F, H | Data governance lead (TBC) | Open | [SRC-04, CON-001; SRC-04, OQ-001] |
| ACO-02 | Constraint | Autonomy approval remains proposed L1-L3, not confirmed. | C, D, F | Capability owner | Open | [SRC-08, section 6.3; SRC-04, CON-002] |
| ACO-03 | Open question | Which system persists approval_trail_record with retention policy controls? | D, F, G | Tech owner | Open | [SRC-04, CON-003; SRC-04, H-007] |
| ACO-04 | Missing information | Comparison-group governance object definition not provided as structured source. | C, D, E, F | Reward + HRBP | Open | [SRC-08, Risks] |
| ACO-05 | Assumption | fabric-layer standards can be used as enterprise reference guidance for naming/layering. | D, E | Enterprise architect | Open validation | [SRC-07, config/enterprise_model.yml; SRC-07, docs/modelling-standard.md] |
| ACO-06 | Security note | External repository excerpts used as evidence snapshots; full repository validation not executed in workspace. | I, J | Delivery lead | Open | [SRC-07, github excerpts] |

# Appendix I - Referenced Artefacts

| Source ID | Artefact | Usage |
| --- | --- | --- |
| SRC-01 | Delivery-Control/Stage_5.md | Authoritative Stage 5 methodology and deliverable expectations |
| SRC-02 | Source Documents/stage-5-document-generation.instructions.md | Stage 5 document structure and rules |
| SRC-03 | Source Documents/stage-5-SKILL.md | Stage 5 generation controls and validation checks |
| SRC-04 | Stage 4 Output/Workforce_Intelligence_Copilot_Stage_4_Classify.md | Workflow, agent, control, handover, and decision baseline |
| SRC-05 | Stage 3 Output/Workforce_Intelluigence_Copilot_Stage3_Decompose.md | Decomposition context and controlled gaps |
| SRC-06 | Delivery-Control/Enterprise_Business_Data_Objects_Overview.docx | Enterprise object families, relationships, governance and traceability patterns |
| SRC-07 | https://github.com/Neill-KPMG/fabric-layer/tree/main/enterprise-data-model | Layering standards, model governance, entity examples, quality and mapping registers |
| SRC-08 | Source Documents/HR_Capability_and_Full_Agent_Catalogue_v1.md | Capability-specific deterministic logic and governance boundary |

# Appendix J - Stage 5B Handover Note

| Handover item | Value |
| --- | --- |
| Workflow steps modelled | 8 (W-001 to W-008) |
| Entities catalogued | 12 (E-001 to E-012) |
| Relationships catalogued | 7 (R-001 to R-007) |
| Gaps logged | 8 (G-01 to G-08) |
| Classification completed | Yes, all listed data items classified |
| Open ownership questions | Yes (ACO-01, ACO-03, G-02, G-05) |
| Stage 5 exit status | Partially met with controlled gaps |
| Stage 5B focus recommendations | Validate source-to-target mappings, close ownership/stewardship, confirm persistence destinations, and execute end-to-end check/approval gate |
