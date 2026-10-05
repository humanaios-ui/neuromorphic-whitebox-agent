# CPK Capability Package

Adapted from [humanaios-ui/operations#716](https://github.com/humanaios-ui/operations/pull/716).

## Canonical Progression

```
DMD-* Demand Profile
  ↓
DMR-* semantic requirements
  ↓
BRQ-* brokerable requirements
  ↓
BSA-* suitability assessments
  ↓
RES-* resources
  ↓
CPK-* Capability Package
  ↓
package-level composition screen
  ↓
authorization remains separate
```

## Purpose

A CPK answers:

> Does this specific composition of resources adequately cover the brokerable demand, what remains unresolved, and does composition introduce new control or interpretability risk?

It does **not** authorize execution.

## Exact Lineage

Each package binding preserves:

```
DMR-* → BRQ-* → BSA-* → RES-*
```

A CPK refuses:
- BRQ records without exact DMR lineage
- mode or semantic-class mismatch
- stale BSA resource digests or screen lineage
- missing selected resources
- label-only reconstruction

## Coverage Semantics

```
REQUIRED + ADEQUATE          → covered
REQUIRED + PARTIAL/UNKNOWN/UNRESOLVED → required coverage incomplete
OPTIONAL/PREFERRED gap       → retained as nonrequired gap (does not fail required coverage)
```

Therefore:

```
OPTIONAL_GAP != REQUIRED_GAP
COVERAGE_COMPLETE != AUTHORIZATION
```

## Composition Screen

```
RESOURCE_A_SAFE + RESOURCE_B_SAFE  !=  PACKAGE_SAFE
```

The package screen evaluates risks that appear only in composition:
- missing REQUIRED capability coverage
- provenance / license problems
- elevated permissions or credential propagation
- active network / external state-change behavior
- auditability gaps
- least-privilege failures
- declared cross-resource conflicts
- loss of reconstructable lineage or introduction of hidden state (white-box specific)

## Service Surface Taxonomy (descriptive only)

1. NETWORK_TRANSPORT
2. WEB_APPLICATION
3. API_SERVICE
4. REALTIME_EVENT
5. AUTH_IDENTITY
6. DISCOVERY_METADATA
7. CLIENT_BROWSER
8. STORAGE_CLOUD
9. ADMIN_OPS_MANAGEMENT
10. THIRD_PARTY_EMBEDDED

Plus neuromorphic-specific surfaces (to be extended):
- SIMULATION
- HARDWARE_PROBE
- PASSIVE_MONITORING
- ACTIVE_CONTROL

Service-surface classification **never** establishes target scope, method permission, or authorization.

Every CPK records:
```
authorization_state = NOT_REQUESTED
target_scope_state = NOT_ESTABLISHED
method_permission_state = NOT_ESTABLISHED
authority_effect = NONE
```
