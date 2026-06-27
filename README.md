# RTL-to-GDS QoR Optimization Framework

Human-in-the-loop physical design optimization framework for RTL-to-GDS QoR analysis using Cadence Genus/Innovus, Python report parsers, convergence policies, and LLM-agent recommendations.

## Live Dashboard
**[View Dashboard →](https://varshasayee-20.github.io/ppa-dashboard/)**

## What this demonstrates

- RTL-to-GDS QoR tracking across 16 iterative design runs on a neural network accelerator tile
- Timing (setup/hold WNS), DRC, connectivity, area, power, and convergence score per run
- Agent-managed proposals (Claude + Codex) vs manual runs — tracked and compared
- Baseline-relative PPA target windows with pass/fail gates
- Python report parsers extracting metrics from Innovus post-route reports
- Convergence policy with stall detection and cost-aware search guidance
- Interactive HTML dashboard linking QoR metrics across all runs

## Technology stack

| Layer | Tools |
|---|---|
| Synthesis | Cadence Genus |
| Place & Route | Cadence Innovus |
| Static Timing | Cadence Tempus |
| PDK | GPDK 90nm |
| Automation | Python 3, C-shell |
| Agent loop | Claude + Codex via JSON proposal files |
| Dashboard | Static HTML generated from `ppa_compare_refreshed.json` |

## Flow overview

```
RTL → Genus synthesis → Innovus floorplan → CTS → Route → Post-route repair → Signoff
                                 ↑                                      ↓
                         Agent proposals  ←←←←  PPA report parser + convergence policy
```

Each iteration, the agent reads timing/DRC/area/power reports, proposes a repair Tcl or next-run config, and the result is logged back into the comparison JSON.

## Note

This repository is an engineering portfolio artifact. Source reports, PDK files, and tool-generated collateral are not included. Run names and metrics are from actual Innovus runs.
