# Lab 3 — Dashboard Project · dataset & KPI key

## Dataset: `uk_station_usage_2024_25.csv`
Real, open data — **UK rail station usage, April 2024–March 2025** (Office of Rail and Road,
Table 1410). One row = one station in Great Britain. Cleaned to a tidy CSV (commas stripped,
"[z]" → 0, clear column names).

**Licence:** Open Government Licence v3.0 — free to use, including commercially, with attribution.
**Source:** ORR Data Portal, Estimates of station usage.

### Columns
| Column | Meaning |
|---|---|
| `station_name` | Station name |
| `region` | Region (London, South East, Scotland, Wales, …) — 11 regions |
| `operator` | Station facility owner / operator — 31 operators |
| `tlc` | Three-letter station code (e.g. LST) |
| `entries_exits_total` | **Headline KPI** — total entries + exits (all ticket types) |
| `entries_exits_full` | Entries + exits on full-price tickets |
| `entries_exits_reduced` | Entries + exits on reduced-price tickets |
| `entries_exits_season` | Entries + exits on season tickets |
| `interchanges` | Passengers changing trains at the station |
| `rank` | National busyness rank (1 = busiest) |

## KPI answer key (for grading)
- **Total entries + exits:** 3,064,611,304 (≈ 3.06 billion)
- **Stations:** 2,586 · **Regions:** 11 · **Operators:** 31
- **Busiest station:** London Liverpool Street (98.0 M)
- **Top 5 stations:** Liverpool Street (98.0M), Waterloo (70.4M), Paddington (69.9M), Tottenham Court Road (68.1M), London Bridge (54.7M)
- **Usage by region (millions):** London 1,647 · South East 361 · North West 223 · East of England 209 · Scotland 167 · West Midlands 138
- **Top operators (millions):** Network Rail 691 · London Underground 308 · Elizabeth line 210 · South Western Railway 208 · London Overground 206
- **Ticket mix:** Reduced ≈ 1.73 bn · Full ≈ 0.92 bn · Season ≈ 0.42 bn

## `reference_dashboard.png`
A mock of what a finished one-screen KPI dashboard should look like (3 scorecards +
region bar + ticket-mix pie + top-operators bar + top-10 table). This is the target;
students build the real thing click-by-click in the BI tool.
