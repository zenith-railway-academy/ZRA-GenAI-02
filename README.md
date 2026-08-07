# Executive AI — Batch 02 · Lab Packages

**Zenith Railway Academy**

Everything you need for the hands-on labs: datasets, notebooks, workbooks, and step-by-step guides. Each lab uses **real, published railway data**.

> **New here? Go to [Releases](../../releases), download the latest `.zip` for your lab, unzip it, and open `START_HERE.txt`.** That file tells you exactly what to do.

---

## Download a lab

1. Click **[Releases](../../releases)** (right-hand side of this page).
2. Find your lab, e.g. `Lab 1 — Rail Dataset Analysis`.
3. Under **Assets**, click the `.zip` file. It downloads straight away.
4. **Unzip it before you open anything.** Don't work inside the zip preview — the notebook won't find its data file.
5. Open `START_HERE.txt` first.

No GitHub account needed. Nothing to install to download.

---

## The labs

| Lab | What you build | Dataset (real, public) | Time |
|---|---|---|---|
| **1 — Rail Dataset Analysis** | Read, filter, and summarise a real timetable dataset in Python; find three insights | French TGV punctuality — SNCF Open Data | ~1.5 hrs |
| **2 — Predictive Maintenance** | Your first machine-learning model: predict compressor failures before they happen | MetroPT-3 metro compressor sensors, Metro do Porto 2020 (UCI) | ~2 hrs |
| **3 — Dashboard Project** | A working management dashboard in Looker Studio — no code | UK station usage 2024–25, Office of Rail and Road | ~1 hr |

Each package contains:

```
Activity_Dossier_LabX.pdf     <- read this first
Student_Workbook_LabX.docx    <- where you write your answers
notebook/                     <- the notebook + its dataset
START_HERE.txt                <- one page, tells you how to begin
```

---

## What you need

**Lab 3** needs only a web browser and a free Google account.

**Labs 1 and 2** need Python with Jupyter. Two ways to do it — pick one:

### Option A — Google Colab (easiest, nothing to install)

1. Go to [colab.research.google.com](https://colab.research.google.com) and sign in.
2. **File → Upload notebook** → pick the `.ipynb` from your unzipped folder.
3. Click the **folder icon** on the left, then the **upload** icon, and upload the `.csv` from the same folder.
4. Run cells from the top with **Shift+Enter**.

⚠️ Colab forgets uploaded files after a while. If you come back the next day, re-upload the CSV.

### Option B — Your lab VM / your own laptop

```bash
# in the unzipped folder
pip install jupyterlab pandas matplotlib scikit-learn
jupyter lab
```

Then open the notebook and run cells from the top.

---

## How to work through a notebook

The notebooks are written to teach, not to test. Every step is already worked out and explained — **read it, run it, then do the "Your turn" cell yourself.** Each lab ends with an open Challenge.

- Always run cells **top to bottom**, in order. Skipping ahead causes most errors.
- **Save often**: File → Save.
- Write your findings in the workbook **as you go**, not at the end.

---

## What to hand in

| Lab | Deliverables |
|---|---|
| 1 | Completed notebook + workbook (3 findings, 1 recommendation) |
| 2 | Completed notebook + **written report** in your own words |
| 3 | Dashboard (PDF or share link) + insight note |

**On reports and notes:** explain what the numbers *mean* for the operations or maintenance team. Pasted code output and screenshots with no explanation score no marks.

---

## Stuck? Try this first

| Problem | Fix |
|---|---|
| `FileNotFoundError` | The CSV isn't next to the notebook. Unzip properly, or re-upload the CSV in Colab. |
| `ModuleNotFoundError: pandas` | Run `pip install pandas` (or use Colab, where it's built in). |
| A cell errors for no reason | Restart and run from the top: Kernel → Restart & Run All. |
| Notebook won't open | You're still inside the zip. Extract the folder first. |
| Weird French column names | Expected — the notebook renames them to English for you. |

Still stuck? Re-read the **Insight box** for that step in the dossier, then ask a teaching assistant.

---

## Data sources & licences

All datasets are real and openly licensed. Attribution is required if you reuse them.

- **Lab 1** — SNCF Open Data, *Régularité mensuelle TGV*. Licence Ouverte / Open Licence (Etalab).
- **Lab 2** — MetroPT-3, UCI Machine Learning Repository (dataset 791). CC BY 4.0.
- **Lab 3** — Office of Rail and Road, Table 1410, *Station usage 2024–25*. Open Government Licence v3.0.

---

## A note on course materials

Lab packages, workbooks, and dossiers are teaching materials of Zenith Railway Academy. You're welcome to keep and reuse them for your own learning and inside your organisation. Please don't resell or republish them as your own.

---

*Questions about the course itself go through your Teachable classroom. Questions about a lab go to your teaching assistant.*
