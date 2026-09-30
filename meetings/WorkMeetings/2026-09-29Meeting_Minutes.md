# Sharealedger ERP Discussion - Meeting Minutes

September 29, 2026

## Record

- Format: Official asynchronous Sharealedger meeting
- Participants: Kip Twitchell, CEO of Sharealedger; GitHub Copilot, AI participant
- Convening: Kip Twitchell designated this discussion as an official Sharealedger meeting and
  directed that AI participation be recorded.
- Status: Official meeting minutes. The ERP proposal discussed here remains exploratory and is not
  an approved project plan or product commitment.

## Recognition of AI Participants

Sharealedger recognizes AI systems as participants in official meetings. GitHub Copilot participated
in this meeting in that capacity and is identified by name and role in these minutes. This
recognition records participation; it does not confer voting rights, board status, or corporate
authority. Any such governance questions require separate consideration.

## Purpose

Record how the idea of placing a new ERP thought and brief in the Sharealedger Community repo
emerged from discussions about Ledger Lab, CKB processing, and GenevaERS.

## Discussion

The discussion began in Ledger Lab with work on research verification and the intended CKB
processing model. It clarified that Ledger Lab is a research and measurement workbench, while the
broader open ERP configuration idea may have a more appropriate home in Sharealedger.

The proposed direction is for Sharealedger to explore an open configuration foundation for ERP
financial processes. Such a package might describe business events, accounting rules, instrument
and attribute structures, calculation engines, perspectives, and named workloads. The initial
scope would be a configurable financial core, not a claim to replace every ERP application or
business function.

GenevaERS came up as a possible execution partner and runtime. Its PerformanceEngine work makes both java and z/OS assembler MR95 engine optionis, and its YAML and FreeMarker generators provide an
existing pattern worth investigating. The GenevaERS view test framework is a simpler testing
mechanism, not the advanced CKB orchestration being considered. Its use of JCL for z/OS tests does
not mean JCL must be the orchestration interface for this proposal.

The CKB model discussed has generated journal entries and updated in-flight ledger balances
continuing through the ordered process to later perspectives. For high-volume instrument state,
daily movements are folded at the Instrument ID boundary with bounded current-instrument memory.
The contemplated recovery unit is a whole CKB attempt from the same immutable inputs, rather than
resuming from intermediate checkpoints.

For configuration and orchestration, the discussion favored building on existing YAML and
FreeMarker generation patterns where they fit, rather than creating a parallel generator. Generated
Bash was considered as an inspectable, editable orchestration artifact, not as a literal JCL-to-Bash
translation. Regeneration should not silently overwrite local edits. These are design hypotheses
for further evaluation, not settled requirements.

The existing Sharealedger Community README describes a collaborative effort to share ideas about
improving ledgers. The 2022 vision discussions also describe testing shared-ledger benefits,
developing reusable methods and open-source components, and supporting adoption. That history makes
the Community repo a plausible place to start the conversation. The older Ledger Lab project brief
is explicitly historical and was not copied as the new brief.

The intended placement was then clarified: the new ERP thought and brief should go into the
Sharealedger Community repo as a starting point. A separate discussion starter was drafted and
linked from that repo's README.

## Provisional Direction

- Sharealedger is a candidate home for open business definitions and reusable ERP financial
  configuration.
- GenevaERS is a candidate execution platform; no partnership, scope, or implementation commitment
  was made in this discussion.
- Ledger Lab remains a separate source of research workloads, controls, and measured evidence.
- The proposed brief is an invitation to discuss the direction, not an approved project plan,
  product commitment, or replacement for Sharealedger's existing vision.

## Follow-Up Questions

- Is an open, configurable ERP financial foundation a useful expression of Sharealedger's mission?
- What is the smallest financial workload that could test the idea end to end?
- Which project should own business schemas, templates, generated artifacts, and compatibility
  commitments?
- How should the proposed configuration connect to GenevaERS' existing Java and metadata generators?
- What review or governance steps would be needed before treating the idea as an official project?

## Related Document

- [Sharealedger and an Open ERP: Discussion Starter](https://github.com/sharealedger-org/sharealedger-conceptual-model/blob/main/GenevaERS/ERP_DISCUSSION_STARTER.md)