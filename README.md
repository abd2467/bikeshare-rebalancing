# Bike-share rebalancing: trucks vs rider incentives

> **Decision:** _to be filled in when the analysis is done._ With incentives reaching X% of riders, the operator can cut truck-km by Y% with the same Z empty-station minutes avoided.

**Status:** set up 2026-11-27; analysis not started.

**The question:** For the morning peak, what mix of truck routes and rider incentives keeps the most stations usable at the lowest cost?

## The problem
Bike-share stations run empty or full at rush hour, so operators move bikes with trucks. Rebalancing accounts for 30% to over 50% of operating costs (ITDP). New York's Citi Bike carried over 44 million rides in 2024, and a December 2025 state audit found the city doesn't independently check the operator's service data. Bike demand prediction has been done many times; the real operating choice is when trucks are worth it and when paying riders to move bikes (as Citi Bike's Bike Angels does) is.

## Approach
1. Pick about 100 stations; estimate each station's net flow of bikes in the 7 to 10am peak from trip history.
2. Set a target bike count per station with a simple demand model.
3. Solve a capacitated pickup-and-delivery truck routing problem in OR-Tools to reach targets overnight.
4. Simulate an incentive scheme across a range of rider response rates (no reliable published figure exists).
5. Compare trucks only, incentives only, and a mix.

## Repo layout
| Folder | Contents |
|---|---|
| `data/` | Raw data (not committed) and processed files |
| `notebooks/` | Numbered analysis notebooks |
| `src/` | Reusable scripts |
| `app/` | Streamlit dashboard |
| `reports/` | Decision memo and charts |
| `notes/` | Learning log, SQL log, setup guide, project map |

## Data
See [DATA_REGISTER.md](DATA_REGISTER.md). Raw data is not re-hosted here.

## How AI was used
See [AI_USE.md](AI_USE.md).

## Reproduce
```bash
git clone https://github.com/abd2467/bikeshare-rebalancing.git
cd bikeshare-rebalancing
python3 -m venv .venv
# Mac/Linux: source .venv/bin/activate    Windows: .venv\Scripts\activate
pip install -r requirements.txt
```
