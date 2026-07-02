# AnchorOS

**Portable governance for preserving context, composing expertise, and developing cross-domain heuristics with AI.**

AnchorOS is a document-based governance framework for AI-assisted work. It turns hard-won context—concepts, methods, constraints, failure modes, and workflows—into versioned **capsules** that can be loaded again, shared, and combined for a particular project.

The framework governs by **anchoring rather than restricting**. Stable coordinates establish what must remain true, where knowledge came from, and which distortions to watch for. Within those anchors, an agent retains room to explore, translate between domains, and propose new connections.

AnchorOS is prompt-native: its capsules and command language are interpreted by a compatible AI agent rather than installed as a conventional operating system.

## Why AnchorOS

Long-running AI projects encounter three recurring problems:

1. **Context is ephemeral.** Important reasoning and working conventions disappear between sessions.
2. **Summaries flatten relationships.** Linear notes may preserve conclusions while losing the connections that made those conclusions useful.
3. **Expertise remains siloed.** Adding several domain prompts to one context does not ensure that their assumptions, tensions, or shared structures will be reconciled.

AnchorOS externalizes that context into portable artifacts and provides a governed way to reconstruct and combine it without carrying an entire conversation forward.

## The Core Concept: Vector Stewardship

At the conceptual center of AnchorOS is **Vector Stewardship**: preserving meaning as a set of reconstructable intersections rather than as a transcript or a list of isolated claims.

In AnchorOS, a semantic vector is a human-readable coordinate that can hold several active dimensions at once—for example, technical, ethical, psychological, historical, artistic, and operational dimensions. It is **not** a raw model embedding and does not require access to an AI system's internal vector data.

A stewardship vector records:

- a stable identifier and semantic node;
- the domain axes meeting at that node;
- the meaning or responsibility it carries;
- the transformations it enables;
- predictable distortions and failure modes;
- instructions for reconstructing it in a different context; and
- guidance for responsible use.

This structure is intended to preserve a **relational skeleton**. Exact wording may change, but the important relationships should survive translation across sessions, models, disciplines, and formats.

### Stewardship principles

- **Anchors, not cages.** Preserve invariants and boundaries while leaving room for creative synthesis.
- **Reconstruction over recollection.** Carry enough structure to rederive meaning instead of attempting to replay an entire session.
- **Stewardship over authority.** The agent helps map, compare, compress, and detect distortion; it is not the source or final authority of the knowledge.
- **Distortion-aware synthesis.** Every capsule can name failure modes, incompatible assumptions, and conditions under which a concept should not be applied.
- **Layered communication.** A capsule can provide immediate surface utility while reserving technical or sensitive depth for contexts where it is relevant and responsibly handled.
- **Portable composition.** Domain capsules remain independently useful and can be assembled into project-specific recipes.

An emergent heuristic is therefore not treated as truth merely because multiple concepts intersect. It is a traceable hypothesis produced by a specific combination of capsules, suitable for testing, critique, revision, or rejection.

## How the Governance Layer Works

AnchorOS separates stable system mechanics from optional domain knowledge:

- **Manifest** declares the required base set and its integrity hashes.
- **Bootstrap** validates completeness and controls initialization order.
- **Spec and Protocol** define capsule integrity, provenance, lifecycle, and command conventions.
- **Index** maps stable aliases to versioned capsule files.
- **Taxonomy and Lexicon** keep types and shared terms consistent.
- **Knowledge** carries durable session-wide heuristics.
- **Vector Stewardship** supplies the semantic reconstruction and synthesis model as required boot context.
- **Optional domain capsules** add portable expertise without expanding the mandatory core for every project.

```text
Required anchors
      +
Selected domain capsules
      ↓
Map intersections, assumptions, and tensions
      ↓
Propose traceable cross-domain heuristics
      ↓
Test, revise, and mint durable findings as capsules
```

The bootloader first establishes the governance primitives, then loads Vector Stewardship as the final required semantic layer. Required capsules establish the shared operating frame. Optional capsules can then be selected as a **recipe** for the problem at hand. The goal is not to force every domain into one vocabulary, but to preserve each domain's provenance while making useful correspondences and conflicts visible.

## Research Synergies

AnchorOS is designed for projects where no single discipline contains enough context to produce a responsible answer.

| Research problem | Capsule recipe | Potential synthesis |
| --- | --- | --- |
| Climate adaptation planning | hydrology + civil infrastructure + public health + local knowledge + ethics | Interventions evaluated against physical risk, implementation constraints, community impact, and distributional effects rather than rainfall projections alone. |
| Accessible learning systems | cognitive science + pedagogy + disability studies + interaction design + cultural context | Teaching strategies that connect learning evidence to accessible delivery and the lived context of learners. |
| AI-assisted policy analysis | law + economics + cybersecurity + public administration + affected-community knowledge | Policy options with explicit assumptions, threat models, operational costs, and second-order social effects. |
| Safety-critical product design | domain engineering + human factors + accessibility + security + incident response | A shared hazard model that includes technical failure, misuse, operator burden, and recovery procedures. |
| Resilient urban systems | transportation + energy + emergency management + public health + community planning | Response strategies that account for infrastructure dependencies, human behavior, continuity of care, and neighborhood-level constraints. |
| Cross-domain discovery | two or more independently maintained specialist capsules + an evaluation-method capsule | Candidate analogies and mechanisms whose provenance and distortion risks remain visible long enough to be evaluated by domain experts. |

These combinations are possible without AnchorOS, but they are difficult to reproduce when the connective reasoning lives only in one long conversation. The framework's contribution is portable continuity, explicit composition, and an audit trail for how a proposed synthesis was produced.

## Capsule Model

A capsule is a portable, versioned agent-configuration document with two layers:

1. **YAML header and handshake metadata:** identity, version, type, provenance, expected caller or sequence, dependencies, and integrity information.
2. **Markdown body:** concepts, constraints, heuristics, reconstruction guidance, examples, and operating procedures.

Capsules can describe governance, a workflow, an evaluation method, or knowledge from any domain. Versioned filenames, index entries, and SHA-256 hashes support integrity checks, upgrades, rollback, and reproducible recipes.

## Repository Layout

```text
AnchorOS/
├── ANCHOR_BaseInstall.manifest   # base-set declaration and command conventions
├── capsules/
│   ├── required/                 # required governance capsules
│   └── optional/                 # installable domain/support capsules
├── packages/                     # packaged base distribution
├── AOS/                          # historical and development artifacts
└── README.md
```

The required set includes `ANCHOR_VectorStewardship_v0.1.txt` alongside the bootloader, specification, protocol, index, taxonomy, lexicon, guide, and knowledge capsules. The historical `AOS/` directory preserves earlier versions and design context; the canonical public base lives under `capsules/` and in the base-install manifest.

## Getting Started

1. Clone this repository.
2. Review `ANCHOR_BaseInstall.manifest` and the files in `capsules/required/`.
3. Supply the manifest and required capsules to a compatible AI session in the declared sequence.
4. Verify filenames, versions, and SHA-256 hashes against the selected manifest.
5. After the set is complete, initialize with the prompt-level command:

```text
| anchor init
```

Other core command conventions include:

```text
| anchor capsule commit base
| anchor capsule commit all
| anchor capsule get <name>
| anchor snapshot
| anchor stop
| anchor help
```

These are agent-facing workflow commands, not shell commands or installed executables.

## Project Direction

AnchorOS is structured around a small required canon and an open-ended domain library. New capsules can be minted from any discipline, shared independently, and combined into reproducible recipes without changing the core governance model. Continued work focuses on automated validation, recipe exchange, conflict handling, and empirical evaluation of whether governed bootstrap context improves cross-session and cross-domain performance.

## Boundaries

AnchorOS does not grant an agent additional authority, override host-system policies, or make generated synthesis automatically correct. It is a governance and continuity framework. Sensitive conclusions still require appropriate domain review, and empirical claims still require evidence.

## License

See [LICENSE](LICENSE).
