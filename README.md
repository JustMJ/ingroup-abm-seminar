# Agent-Based Modeling for Group and Team Research

Materials for the INGRoup Method Seminar, October 13, 2026, presented by Justin M. Jones, Ph.D. (National Counterterrorism Innovation, Technology, and Education Center, University of Nebraska at Omaha).

## Contents

| Path | What it is |
|---|---|
| `ABM_INGroup_deck.pptx` | Slide deck for the session, with speaker notes |
| `models/` | NetLogo models used in the live demonstrations |
| `models/experiments/` | BehaviorSpace experiment definitions, one per figure, with the seeds used |
| `sweep/` | Parameter sweep definition for the information-spread example, with a summary of the results |

## Running the models

1. Install [NetLogo](https://ccl.northwestern.edu/netlogo/) (free). The models were built with version 7.0.4; later 7.x versions should open them.
2. Open any `.nlogox` file in `models/`, then press Setup and Go.

## Models

| File | Description | Source |
|---|---|---|
| `Segregation_NCITE.nlogox` | Residential segregation | Wilensky (1997), after Schelling (1971); display colors changed, rules unchanged |
| `Team_Assembly_NCITE.nlogox` | Team formation and network structure | Bakshy & Wilensky (2007), after Guimerà et al. (2005); label change only |
| `bounded_confidence.nlogox` | Opinion dynamics with a confidence threshold | Deffuant et al. (2000) |
| `team_knowledge_emergence.nlogox` | Team knowledge emergence | Reimplementation following Grand et al. (2016) |
| `construction_stage1.nlogox` to `construction_stage4.nlogox` | One model built in four stages (pairwise averaging) | Deffuant et al. (2000) without a threshold; DeGroot (1974) |
| `fictional_information_spread.nlogox` | A fictional teaching study of information spread across communication structures | Leavitt (1951); simple contagion |

`fictional_information_spread` uses invented parameters and is meant only to demonstrate how a parameter sweep works. Its results are not empirical findings.

## Reproducing the information-spread sweep

Headless command (72,000 runs; seeds are the run numbers):

```
netlogo-headless.sh --model models/fictional_information_spread.nlogox --setup-file sweep/spread_sweep.xml --experiment sweep --table spread.csv
```

`sweep/spread_sweep_results_summary.csv` and `sweep/spread_sweep_plot.png` hold the results shown in the deck.

## Notes

- The two library models (Segregation and Team Assembly) come from the NetLogo Models Library and keep their original authors' credit and license (CC BY-NC-SA 3.0). Please cite the sources above when using them.
- The models were tested with scripted headless runs. Open each in the NetLogo interface once before relying on it.

## Contact

Justin M. Jones, Ph.D. · jjones188@unomaha.edu
