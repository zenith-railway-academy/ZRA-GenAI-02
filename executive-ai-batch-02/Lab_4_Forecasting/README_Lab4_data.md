# Lab 4 data — `lirr_daily_ridership.csv`

## What it is

Daily ridership counts for three rail services of the New York Metropolitan
Transportation Authority (MTA), one row per calendar day.

| Column | Meaning |
|---|---|
| `date` | The calendar day. Every day from 2023-01-01 to 2026-08-31 is present — **no gaps**. |
| `lirr_riders` | **Long Island Rail Road** — estimated riders that day. *This is the series you forecast.* |
| `mnr_riders` | **Metro-North Railroad** — a second commuter railroad. Used for cross-checking odd days, and for the optional extension. |
| `subway_riders` | **New York City Subway** — used for cross-checking odd days. |

**1,339 rows** — 3 years and 8 months. Average LIRR ridership over the period:
~205,900 riders/day. A typical Wednesday carries about 247,000; a typical Sunday
about 108,000 (measured on the lab's training period, 2023-01-01 → 2026-05-31).

## Where it comes from

- **Publisher:** Metropolitan Transportation Authority (MTA)
- **Portal:** New York State open data portal, <https://data.ny.gov>
- **Dataset:** *MTA Daily Ridership and Traffic: Beginning 2020* (id `sayj-mze2`)
- **Retrieved:** 9 September 2026
- **Terms:** [OPEN-NY Terms of Use](https://data.ny.gov/dataset/OPEN-NY-Terms-Of-Use/77gx-ii52) —
  among the least restrictive open-data terms in use. Free to download and reuse
  in public or private projects, with **no attribution requirement, no
  share-alike, and no pre-approval**; the only condition is that your use is
  lawful. We credit the MTA anyway, because that is good practice.

## What we changed

Almost nothing, on purpose.

1. Reshaped the published long format (`Date, Mode, Count`) into one column per mode.
2. Kept only the three rail modes and cut the range to 2023-01-01 → 2026-08-31.
   The published series starts 2020-03-01, but the first years are dominated by the
   pandemic collapse and recovery — a structural break that would swamp everything
   else in a first forecasting lab.

**The values themselves are exactly as published.** In particular we have *not*
cleaned the four days where the LIRR feed reports **zero** riders:

| Date | `lirr_riders` | `mnr_riders` | `subway_riders` |
|---|---|---|---|
| 2026-02-23 | 0 | 16,152 | 830,660 |
| 2026-05-16 | 0 | 151,901 | 3,267,749 |
| 2026-05-17 | 0 | 115,691 | 2,494,895 |
| 2026-05-18 | 0 | 238,270 | 4,118,450 |

These are not all the same kind of day, and the other two columns are what tell
you so. On **16–18 May** Metro-North and the subway ran *above* their normal
levels for those weekdays (119–129%), so the network was busy and this is a gap
in the LIRR feed. **23 February** is different: Metro-North was at about 8.5% and
the subway at about 24% of a normal Monday, so the whole network was disrupted
that day. The LIRR figure is still impossible — a railway that runs does not
carry literally nobody — so it still needs repairing, but that repair is a guess
rather than a recovered fact. Diagnosing the difference, and repairing both, is
**Step 2 of the lab**.

## Caveats worth quoting in your report

- The MTA states that these are **next-day estimates**, published quickly, and that
  they "may differ from official ridership totals published elsewhere by MTA."
  That is normal for operational data — and worth saying out loud in an analysis.
- 2026-01-25 shows only 30,577 LIRR riders. Metro-North and the subway are also far
  below normal that day, so all three fell together. It reads as a genuine
  near-shutdown rather than a feed fault, but the dataset alone does not tell you why.
- 2026-06-18 is the busiest day in the whole 1,339-day extract (369,482 riders).
  We do not know what caused it. Neither do you — say so rather than inventing a reason.

## Reproducing this file

```bash
curl -L "https://data.ny.gov/api/views/sayj-mze2/rows.csv?accessType=DOWNLOAD" -o mta_daily.csv
```

Then pivot `Mode` to columns, keep `LIRR`, `MNR`, `Subway`, and slice
2023-01-01 → 2026-08-31.
