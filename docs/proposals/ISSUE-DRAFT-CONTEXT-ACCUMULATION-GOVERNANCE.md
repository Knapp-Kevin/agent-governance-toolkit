# Issue Draft: Context Accumulation Governance for Delegated Agent Workflows

## Summary

Introduce a framework-neutral governance model that evaluates accumulated workflow context rather than evaluating actions solely in isolation.

Related ADR:

- ADR-CONTEXT-ACCUMULATION-GOVERNANCE.md

---

## Problem

AGT governs actions, tools, identity, policy decisions, and audit events.

A remaining governance gap exists when:

- Multiple individually permissible actions accumulate sensitive context.
- Derived intelligence becomes more sensitive than source data.
- Delegated agents inherit workflow state that is not represented in current authorization decisions.

Example:

PII + Financial + Behavioral Analytics

may create a highly sensitive customer profile even if each source was individually approved.

---

## Proposal

Introduce a Context Envelope model capable of:

- Tracking accumulated sensitivity.
- Tracking derived sensitivity.
- Propagating restrictions through delegation chains.
- Recording context transitions in audit logs.
- Supporting policy evaluation against projected context state.

---

## Potential Components

- ContextEnvelope
- ContextProjection
- ContextAggregationRule
- ContextConstraint
- ContextEnvelopeEvaluator

---

## Candidate Event Types

- CONTEXT_ENVELOPE_CREATED
- CONTEXT_ENVELOPE_UPDATED
- CONTEXT_AGGREGATION_ELEVATED
- CONTEXT_DELEGATED
- CONTEXT_REDACTED
- CONTEXT_DECLASSIFICATION_REQUESTED
- CONTEXT_DECLASSIFICATION_APPROVED
- DERIVED_ARTIFACT_LABELED

---

## Candidate Deliverables

Phase 1

- Envelope schema
- Audit integration
- Example policies
- Test fixtures

Phase 2

- Delegation propagation
- Context projection
- Aggregation rules

Phase 3

- Derived sensitivity support
- Envelope lineage tracking
- Compliance reporting integration

---

## Architecture Diagrams

Refer to ADR-CONTEXT-ACCUMULATION-GOVERNANCE.md for complete Mermaid diagrams covering:

- Workflow evaluation flow
- Context hierarchy
- Delegation propagation
- Authority intersection
- Governance sequence diagrams

---

## Open Questions

1. Agent OS ownership vs Agent Mesh ownership?
2. Envelope lifecycle management?
3. Policy-engine integration points?
4. Derived sensitivity standardization?
5. Declassification workflow design?

---

## Expected Outcome

AGT gains the ability to govern not only what an agent is doing, but what accumulated context enables the agent to know, infer, delegate, retain, or export.
