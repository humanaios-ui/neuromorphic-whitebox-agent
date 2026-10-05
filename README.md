# Neuromorphic White-Box AI Agent

**Status:** Bootstrap (Phase 0)  
**Governance:** Capability composition follows the exact discipline of [humanaios-ui/operations#716](https://github.com/humanaios-ui/operations/pull/716) (CPK-* packages, exact lineage, package-level screening).

## Thesis

A white-box neuromorphic AI agent whose internal dynamics (spikes, network state, developmental trajectory, decisions) are fully inspectable, lineage-traced, and composable.

Core properties (from the organoid → neuromorphic mapping):
1. Spiking Neural Networks (SNNs)
2. Event-driven / Actor-model systems
3. Graph-based connectivity
4. Observability & monitoring (MEA-style)
5. Developmental / evolutionary programming

All capabilities are exposed only through screened **CPK-* Capability Packages** that preserve exact demand → resource lineage.

## Canonical Progression (from PR #716)

```
DMD-* Demand Profile
  ↓
DMR-* semantic requirements
  ↓
BRQ-* brokerable requirements
  ↓
BSA-* suitability assessments
  ↓
RES-* resources (neuron models, learning rules, backends, monitors, developmental operators)
  ↓
CPK-* Capability Package
  ↓
package-level composition screen
  ↓
authorization remains separate
```

Key invariants enforced:
- `OPTIONAL_GAP != REQUIRED_GAP`
- `COVERAGE_COMPLETE != AUTHORIZATION`
- `SERVICE_SURFACE != TARGET_SCOPE != METHOD_PERMISSION != AUTHORIZATION`
- No label-only reconstruction of lineage
- Package screen catches composition risks invisible at single-resource level

## Repository Layout

```
neuromorphic-whitebox-agent/
├── README.md
├── LICENSE
├── docs/
│   ├── RESEARCH_PLAN.md
│   ├── CAPABILITY_PACKAGE.md
│   └── WHITEBOX_PRINCIPLES.md
├── schemas/
│   ├── demand-profile.v1.schema.json
│   └── capability-package.v1.schema.json
├── src/
│   ├── core/                 # SNN / actor / graph runtime
│   ├── composition/          # CPK engine (lineage, screening, hashing)
│   ├── observability/        # MEA-style probes & decision traces
│   ├── developmental/        # plasticity, neurogenesis, evolutionary ops
│   └── agent/                # high-level white-box agent interface
├── tests/
├── examples/
│   └── minimal_spiking_agent/
└── .github/workflows/
```

## Immediate Goals (Phase 0)

1. Port/adapt CPK schema + lineage validation + package screen from operations#716.
2. Define first Demand Profiles for a minimal “spike-and-explain” agent.
3. Implement integrity hashing and rejection of incomplete lineage.
4. Provide a trivial SNN resource that can be packaged into a CPK.

## License

Apache-2.0
