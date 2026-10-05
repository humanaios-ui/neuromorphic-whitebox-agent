# Research Plan: Neuromorphic Computing White-Box AI Agent

**Explicit incorporation of** [humanaios-ui/operations#716](https://github.com/humanaios-ui/operations/pull/716)

## 1. Core Thesis
Build a white-box neuromorphic AI agent whose internal dynamics (spikes, network state, developmental trajectory, decisions) are fully inspectable, lineage-traced, and composable.

The agent is an event-driven, graph-structured, developmental system (SNN + actor/message-passing + observability + evolutionary/developmental rules) whose capability composition follows the exact discipline introduced in PR #716.

## 2. Explicit Mapping of PR #716

PR #716 introduces CPK-* Capability Packages, exact lineage (DMR → BRQ → BSA → RES → CPK), package-level composition screening, service-surface taxonomy, and strict separation of coverage from authorization.

| PR #716 Concept | Neuromorphic White-Box Agent Mapping |
|-----------------|--------------------------------------|
| Demand Profile (DMD) | Agent capability needs (sensing, reasoning, acting, learning, explaining) |
| Semantic / Brokerable Req. | Specific functional requirements (e.g. “spike-based decision with full spike-history lineage”) |
| Resources (RES) | Neuron models, learning rules, backends (Lava, Brian2, NEST, Loihi sim), monitors, datasets, developmental operators |
| Capability Package (CPK) | A complete, screened composition of resources that realizes a white-box agent capability |
| Package composition screen | Safety + interpretability + observability checks that only appear when components are composed |
| Service Surface Taxonomy | Classification of interaction modes (simulation, hardware probe, passive monitoring, active control, etc.) |
| Lineage + integrity hash | Every spike train, weight update, developmental step, and agent decision carries reconstructable provenance |

This discipline is the **composition and governance layer** of the agent.

## 3. Phased Plan

**Phase 0 – Foundation**  
Port/adapt CPK schema, lineage validation, package screen, and service-surface taxonomy. Define first Demand Profiles. Enforce integrity hashing.

**Phase 1 – Core Neuromorphic Runtime**  
Event-driven SNN core, graph connectivity, basic observability (spike raster, burst detection, decision traces). Map every runtime component as a RES-* resource.

**Phase 2 – White-Box Composition Layer**  
Full CPK engine. Package-level screen for interpretability risks. Service-surface classification for deployment modes. Guarantee every decision carries reconstructable CPK provenance.

**Phase 3 – Developmental & Evolutionary Capabilities**  
Plasticity, metaplasticity, neurogenesis, evolutionary architecture search as first-class resources. Longitudinal maturation tracking.

**Phase 4 – Agent Interface & Evaluation**  
High-level white-box agent API that only exposes capabilities backed by valid CPKs. Interpretability-focused benchmarks.

**Phase 5 – Hardware Path & Scaling**  
Loihi 2 / Lava and SpiNNaker backends as mode-bound RES-* variants. Package screens that account for hardware constraints.

## 4. Success Metrics (White-Box Specific)
- 100 % of decisions carry intact DMR→…→CPK lineage
- Package screen rejects any composition that loses reconstructability or introduces hidden state
- Observability coverage ≥ 95 % of spikes, weight updates, and developmental events
- Ability to replay any agent trajectory from the recorded CPK + spike history alone
- Clear separation between “capability is covered” and “action is authorized”
