# Sharealedger ERP and Geneva View-Service Follow-Up

September 30, 2026

## Record

- Format: Asynchronous follow-up discussion recorded as a working meeting note.
- Participants: Kip Twitchell and GitHub Copilot.
- Status: Exploratory. No architecture, partnership, project, or product commitment was approved.

## Purpose

Capture follow-up ideas about an open ERP financial foundation, AI-mediated reporting requests, GenevaERS as a potential started-task view service, and temporal hierarchy changes.

## Discussion

The long-term concept is a started GenevaERS task that accepts declared view requests and streams source events to qualifying active views. An AI interaction layer could translate a user's question into a constrained request; Geneva would execute the request deterministically. The AI would not perform financial aggregation itself.

For historical requests, append-only input supports a snapshot high-water mark. A view can join an in-progress scan, consume the remaining committed records through its captured high-water mark, then wrap to the earlier records. The join-boundary record must be included exactly once. Partitions appended after the high-water mark belong to a later snapshot unless the request is explicitly a live subscription.

An ordered end-of-day marker could close extract-time buffers, emit outputs, and checkpoint progress. Late-arriving events need explicit treatment, such as reopening/reissuing an output generation or posting an adjustment in a later period. Replay, live subscription, and period-close behavior remain design hypotheses requiring runtime and scale evidence.

The discussion used the Switch/Recast/Reclass distinction from *History as Fact, Classification as Choice*. Effective-dated reference data can support Switch (classify at event time) and Recast (classify at a selected perspective date). Reclass is different: it requires balanced, traceable business events. Rebuilding a report projection must not silently change canonical accounting entries.

For a hierarchy update, startup replay could regenerate a historical report generation using a declared hierarchy version and event high-water mark, reconcile it, publish it, and then attach to live events. Prior generations should remain identifiable. This is report regeneration, not mutation of source history.

The short-term Ledger Lab exploration is narrower: investigate a user interaction layer in 99 that produces validated view requests, with record scanning and aggregation executed as an explicit, measured CKB/view process. Current legacy VA fixture success is not proof of generalized CKB capability. The prototype plan is recorded separately in Ledger Lab.

## Open Questions

- What exact request contract identifies source generation, partition set, high-water mark, hierarchy version, perspective semantics, predicates, measures, and output destination?
- Can a started task add views safely while a scan is in progress, including correct boundary handling, cancellation, backpressure, and bounded view state?
- How are view generations checkpointed and recovered after failure without gaps or duplicate records?
- What policy governs late and backdated transactions after an end-of-day output has been published?
- Which GenevaERS runtime capabilities already exist, and which require new work?
- What evidence and workload would distinguish replay cost from retained-state/index cost?

## Follow-Up

- Keep Sharealedger's ERP document at discussion-hypothesis status until community review.
- Prototype only a small, named request against a fixed Ledger Lab fixture before making claims about GenevaERS or production behavior.
- Keep Switch, Recast, and Reclass semantics explicit in any request or output generation.

## Repository Update

- Created the public [Sharealedger Conceptual Model repository](https://github.com/sharealedger-org/sharealedger-conceptual-model), seeded at `c21d3b3` and updated at `5ee9c1b`.
- Moved the ERP discussion starter to `GenevaERS/ERP_DISCUSSION_STARTER.md`; the community README and both September meeting notes link to its new location.
- Moved the authorized April 2020 MSU guest lecture deck to `presentations/`. Meeting minutes remain in the community repository.
- The new repository is conceptual and exploratory; its README distinguishes ontology, logical model, accounting projection, and physical realization.

## Related Documents

- [Sharealedger and an Open ERP: Discussion Starter](https://github.com/sharealedger-org/sharealedger-conceptual-model/blob/main/GenevaERS/ERP_DISCUSSION_STARTER.md)
- [Ledger Lab CKB View-Query Prototype Plan](../../../ledger-lab/99-interpretation/CKB_VIEW_QUERY_PROTOTYPE.md)
