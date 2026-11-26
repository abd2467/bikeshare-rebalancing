# Project map

## The question
For the morning peak, what mix of truck routes and rider incentives keeps the most stations usable at the lowest cost?

## How the pieces connect

```mermaid
flowchart LR
    A[Citi Bike trips<br/>one or two months] --> B[Net flow per station<br/>7-10am peak]
    B --> C[Target bikes<br/>per station]
    C --> D[Truck routing<br/>OR-Tools PDP]
    C --> E[Incentive simulation<br/>response rate swept]
    D --> F[Trucks vs incentives vs mix]
    E --> F
    F --> G[Dashboard + memo]
```

## Folder map

```
bikeshare-rebalancing/
├── README.md              Decision and headline at the top (last day)
├── AGENTS.md, CLAUDE.md   Rules for the coding agent
├── DATA_REGISTER.md       Add download dates on day 1
├── AI_USE.md              Log AI use every day
├── requirements.txt       Pin versions on day 1
├── data/raw/              Downloaded source files (never committed)
├── data/processed/        Cleaned files and small result files
├── notebooks/
│   ├── 01_trips_net_flow.ipynb
│   ├── 02_station_targets.ipynb
│   ├── 03_truck_routing.ipynb
│   ├── 04_incentive_sim.ipynb
├── src/                   Reusable scripts
├── app/                   Streamlit dashboard
├── reports/               Two-page decision memo, charts
└── notes/                 Learning log, SQL log, this map
```

## Plan (2 days in the master plan)

| Day | Question answered | Output |
|---|---|---|
| 1 | Where and when do stations run empty or full? | Trips loaded and checked; net flows and targets; first truck routes |
| 2 | When do incentives beat trucks? | Routing finalised, incentive simulation swept, comparison, dashboard, memo |

## The working loop for every step
Concept (Claude explains) → Spec (I write the agent prompt, Claude reviews) → Generate (agent codes on a branch) → Verify (I check numbers) → Review (pull request; CodeRabbit comments; I decide which to act on) → Explain back → Document → Merge.
