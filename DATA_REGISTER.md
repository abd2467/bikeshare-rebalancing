# Data register

Every dataset used in this project, where it came from, and what the licence allows.

| Dataset | Source | Licence | Downloaded | Notes |
|---|---|---|---|---|
| Citi Bike trip histories | [citibikenyc.com/system-data](https://citibikenyc.com/system-data) | Lyft data licence: any lawful use, but no republishing the raw data as a dataset, no re-identification. Publish code and results only | _date_ | Monthly CSVs; choose one or two months. |
| Citi Bike live station feed (GBFS) | Linked from the system data page | As above | _date_ | Station locations and capacities. |
| Context figures | [ITDP operating costs](https://bikeshare.itdp.org/guide/financial-model/operating-costs/); [NYS Comptroller audit, Dec 2025](https://www.osc.ny.gov/state-agencies/audits/2025/12/24/new-york-city-bike-share-program-oversight-revenue-collection-and-monitoring) | Cited, not re-hosted | _date_ | Rebalancing 30-50%+ of opex; audit findings. |

**Policy:** raw files stay in `data/raw/` and are never committed. Published outputs are code, aggregates and charts.
