# sharealedger

The Sharealedger project is a collaborative, open source effort, to share information and discuss ideas about improving ledgers of all kinds. The Sharealedger GitHub organization holds multiple repositories, some of which are POC/prototyping in nature. Others in the future may contain elements shared with those who wish to share a ledger.

The project is governed by two licenses:
- For code, the project uses the Apache 2.0 license.
- For business content, slides, and other materials, the project uses Creative Commons 4.0 license.
  Note: materials in member-only repositories may carry individual copyright notices that supersede
  the CC 4.0 default. See the Membership section below.

Both licenses allow for commercial development of materials found in the project, with proper attribution.

More information about the purpose of the organization, the principles involved in its mission, and the collaborative efforts to date can be found at https://sharealedger.org

## Membership

Sharealedger membership is managed through the private `sharealedger-org/org-members` GitHub
repository. Access to that repository constitutes membership.

To request membership, file a
[Membership Request issue](https://github.com/sharealedger-org/community/issues/new/choose)
in this repository, or contact the CEO at kip.twitchell@sharealedger.org.

The membership policy — qualifications, access terms, copyright provisions, and member
register requirements — is established by Board resolution:
[`meetings/CorporateDocuments/2026-10-01_L.Membership_Access_Policy.md`](meetings/CorporateDocuments/2026-10-01_L.Membership_Access_Policy.md)

## Current Discussion

[Sharealedger and an Open ERP: Discussion Starter](https://github.com/sharealedger-org/spec-conceptual-model/blob/main/GenevaERS/ERP_DISCUSSION_STARTER.md)
explores whether Sharealedger's shared-ledger mission could support an open, configurable ERP
financial foundation. It is a starting point for community discussion, not an approved project plan
or architecture.

## Conceptual Model

[Sharealedger Conceptual Model](https://github.com/sharealedger-org/spec-conceptual-model)
is the separate home for perspective-independent business concepts, relationships, invariants,
and worked examples. It is distinct from implementation and measurement work in Ledger Lab.

---

## Repository Registry

One entry per repository. **Before creating a new repo**, add a row here and follow the
[creation policy](#repository-creation-policy) below.

| Repository | Prefix | Type | Status | Description |
|---|---|---|---|---|
| [community](https://github.com/sharealedger-org/community) | — | Governance | Active | Issues, membership, governance, meeting records |
| [spec-conceptual-model](https://github.com/sharealedger-org/spec-conceptual-model) | `spec-` | Specification | Active | Business ontology, framework, project specs |
| [ledger-lab](https://github.com/sharealedger-org/ledger-lab) | — | Research | Active | Scala VA pipeline, cost-curve measurement experiments |
| [ledgerlearning](https://github.com/sharealedger-org/ledgerlearning) | — | Content | Active | Public learning resources and white papers |
| [tool-git-ledger](https://github.com/sharealedger-org/tool-git-ledger) | `tool-` | Tool | Active | Git-based ledger utility |
| [org-members](https://github.com/sharealedger-org/org-members) | `org-` | Org-internal | Private | Member register, corpus, private correspondence |
| [org-admin](https://github.com/sharealedger-org/org-admin) | `org-` | Org-internal | Private | Board resolutions, financials, org administration |
| [org-books](https://github.com/sharealedger-org/org-books) | `org-` | Org-internal | Private | Sharealedger NFP bookkeeping data |
| [proto-hospice](https://github.com/sharealedger-org/proto-hospice) | `proto-` | Prototype | Planned | Hospice family caregiver shared ledger prototype |

---

## Repository Creation Policy

Before creating a new repository under `sharealedger-org`:

1. **Choose the right prefix.** Use `proto-` for time-limited prototypes, `spec-` for
   specifications and conceptual models, `tool-` for standalone tools, `org-` for
   internal org infrastructure. Leave the name unprefixed only for well-known core
   projects (`community`, `ledger-lab`, `ledgerlearning`).

2. **Register it first.** Add a row to the Registry table above in a PR or commit
   before creating the GitHub repo. The registry is the source of truth; the GitHub
   org page is not.

3. **Anchor it to a spec.** Every `proto-` repo must have a corresponding
   `projects/<name>/` entry in `spec-conceptual-model` as its specification home
   before any implementation code is committed.

4. **Plan for archival.** Prototype repos are time-limited. When the prototype's
   research questions are answered, the repo is archived (not deleted). Record the
   archival date and outcome in this registry.

5. **No industry taxonomy.** Repos are organized by type, not by industry vertical.
   Industry context belongs in the project spec inside `spec-conceptual-model`.
