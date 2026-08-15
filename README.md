# RTL-to-GDS QoR Optimization Framework

Human-in-the-loop physical-design optimization framework integrating Cadence
Genus, Innovus, and Tempus with Python report parsers, convergence policies,
and Claude/Codex recommendations.

## Dashboards

- **[Current dashboard (v2)](https://varshasayee-20.github.io/ppa-dashboard/):**
  implementation QoR, nominal-PVT Tempus signoff, executed ECO lineage,
  source-linked metrics, and agent telemetry.
- **[Archived dashboard (v1)](https://varshasayee-20.github.io/ppa-dashboard/v1/):**
  original implementation-focused dashboard retained for comparison.

## What This Demonstrates

- RTL-to-GDS QoR tracking across implementation and Tempus ECO iterations.
- Setup/hold WNS and TNS, DRC, connectivity, area, power, and convergence.
- Explicit separation of the clean baseline, implementation-QoR reference,
  active ECO lineage, and Tempus-verified signoff winner.
- Claude and Codex proposals tracked through auditable JSON and Tcl artifacts.
- Publication-safe HTML report previews with source provenance.

## Technology Stack

| Layer | Tools |
|---|---|
| Synthesis | Cadence Genus |
| Place and route | Cadence Innovus |
| Static timing | Cadence Tempus |
| PDK | GPDK 90nm |
| Automation | Python 3, C shell |
| Agent loop | Claude and Codex |
| Dashboard | Static HTML generated from provenance-bearing v2 parser JSON |

## Flow

```text
RTL -> Genus -> Innovus -> Tempus -> Python parsers -> agent proposal
                    ^                                  |
                    +------ reviewed ECO Tcl ----------+
```

This repository is a portfolio artifact. RTL, netlists, SPEF, checkpoints,
PDK files, proprietary libraries, and raw Cadence outputs are not published.
