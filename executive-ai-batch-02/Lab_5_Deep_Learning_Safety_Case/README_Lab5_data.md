# Lab 5 data — `metropt3_teaching.csv`

## What it is

Sensor readings from the **Air Production Unit (APU)** — the compressor that feeds the brakes
and air suspension — of a metro train operated by **Metro do Porto**, Portugal. One row is one
minute.

**This is the same file you used in Lab 2, completely unchanged.** That is deliberate. You
already know what the sensors mean and what the failures look like, so all of today's
attention can go on the model and on the decision about it.

| Column | Meaning |
|---|---|
| `timestamp` | The minute the readings were taken. **The record is not continuous** — see below. |
| `TP2`, `TP3`, `H1`, `DV_pressure`, `Reservoirs` | Pressure measurements at various points |
| `Oil_temperature` | Compressor oil temperature (°C) |
| `Motor_current` | Current drawn by the compressor motor (A) |
| `COMP`, `DV_eletric`, `Towers`, `MPG`, `LPS`, `Pressure_switch`, `Oil_level`, `Caudal_impulses` | Digital signals — valve and switch states, mostly 0 or 1 |
| `airleak_failure` | **1** during a real air-leak failure, **0** otherwise |

**144,437 rows**, 2020-02-01 00:00 to 2020-06-02 07:54. (The test slice runs a
day and a half into June — it ends 2020-06-02 07:54 — so "the test month" is really May plus
1–2 June.) Failure minutes: **1,825 = 1.26%**.

> ⚠️ **The network never sees `airleak_failure`.** That column exists only so *you* can score
> the monitor afterwards. Training on healthy minutes alone is the whole point of the method
> under assessment — see Step 3.

## The two failures

| Episode | When | Minutes | Used for |
|---|---|---|---|
| 1 | 18 April 2020 (most of the day) | 1,435 | Falls in the **training** period — and is then **removed**, because the network trains on normal minutes only |
| 2 | 29 May 2020 23:30 – 30 May 05:59 | 390 | The **test** episode. Everything you report is measured on this one event. |

**Two episodes, one unit, one fault type.** This is the single most important fact about the
dataset and the sentence your safety case has to be built around. It is not a flaw in the
lab — real fleet data looks like this, which is exactly why the safety argument matters.

## The gaps — read this before Step 1

The clock from the first row to the last contains **176,155 minutes**. The file has
**144,437**. About **31,700 minutes are missing**, spread across **187 separate gaps**.

They are not all the same kind of gap, and telling them apart is **Step 1 of the lab**. Some
of the missing time is the train being stabled with the compressor off — there is nothing to
record and nothing to repair, and inventing readings for a parked train would be inventing
data. Some of it is not. Working out the split, and what it means for a monitor trained only
on the minutes that survived, is your first task and your first entry in the safety case.

Do not assume; measure. The notebook's own commentary on this point is worth checking rather
than believing.

## Where it comes from

- **Publisher:** UCI Machine Learning Repository — *MetroPT-3 Dataset*, dataset id **791**
- **Originators:** Metro do Porto (Porto, Portugal), with the University of Porto
- **URL:** <https://archive.ics.uci.edu/dataset/791/metropt+3+dataset>
- **Licence:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
  — free to use, share and adapt, including commercially, **provided you give attribution**.
- **Attribution used in this package:** *MetroPT-3 dataset, Metro do Porto, 2020. UCI Machine
  Learning Repository (dataset 791). Licensed CC BY 4.0.*

## What we changed

The same preparation as Lab 2, and nothing since:

1. Down-sampled the original 1-second recordings to **one row per minute**.
2. Kept the 15 sensor columns plus a `airleak_failure` label derived from the failure periods
   documented with the original dataset.
3. Cut the range to 2020-02-01 → 2020-06-02.

**The readings themselves are as published.** The gaps were not filled, the outliers were not
removed, and nothing was smoothed. Anything odd you find in it is real.

## Caveats worth quoting in your safety case

- **One unit.** Every reading comes from a single train's compressor. Nothing here says
  anything about a second unit, let alone a fleet.
- **One fault type.** Every labelled failure minute in this file is an air leak. What that
  does or does not let you conclude about the supplier's claim is Challenge Part 2.
- **The "healthy" label is an assumption.** Minutes not marked as failures are *assumed*
  healthy. A slow degradation that nobody logged would be sitting in the training data being
  learned as normal.
- **The test period is not the training period.** Several sensors sit at noticeably different
  levels in the test month than in February–April. Step 3 asks you to find them and to resist
  the first explanation that comes to mind.
- **Running hours only.** Because of the overnight gaps, the model has never seen a cold start
  and has no idea what a healthy one looks like.

## Reproducing this file

The original is available from the UCI page above as a single large CSV of 1-second readings.
Down-sample to one-minute means, label the two documented air-leak periods
(18 Apr 2020, and 29–30 May 2020), and slice the date range given above.
