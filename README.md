# Executive AI — Batch 02 · Lab Materials

**Zenith Railway Academy**

---

## 📌 What this page is for

Your labs **do not run here.** They run on your lab VM at **[zralabs.com](https://zralabs.com)**, where the notebooks and datasets are already installed and waiting for you.

This page exists for one main reason:

> **The lab VMs reset.** Anything you save on the VM disappears. So your workbooks and report templates live here instead, permanently, where you can download them any time.

Use this page to get:

- 📄 **Your workbook / report / insight note** — the document you fill in and hand in
- 📦 **The full lab package** — only if you want to run a lab on your own laptop instead of the VM
- 🗂️ **Lab 3 materials** — Lab 3 isn't on the VM at all (see below)

---

## 🚀 How a lab actually works

### Labs 1 and 2 — on the lab VM

1. **Download your workbook from [Releases](../../releases)** on this page — do this first, and keep it on *your own computer*, not the VM.
2. Go to **[zralabs.com](https://zralabs.com)** and sign in with your own login.
3. Open your assigned lab and **spin up the VM** — takes a couple of minutes.
4. Everything is already there: Python, JupyterLab, the notebook, and the dataset. Nothing to install, nothing to upload.
5. Work through the notebook, running cells from the top with **Shift+Enter**.
6. **Take screenshots** of your work as you go — you'll need them.
7. Type your observations, outcomes and conclusions into the workbook on your own computer.

### Lab 3 — on Looker Studio, not the VM

Lab 3 is a no-code dashboard lab and **does not use the lab VM**. You'll build it in Google Looker Studio in your browser.

1. Download the **Lab 3 package** from [Releases](../../releases) — it has the dataset, the build guide, and your insight note.
2. Go to [lookerstudio.google.com](https://lookerstudio.google.com), sign in with a free Google account.
3. Follow the Activity Dossier step by step.

---

## ⚠️ Before you close the VM

The VM **resets**. When it does, everything on it is gone.

Save these to your own computer before you finish a session:

- ✅ Your completed notebook — download the `.ipynb` from the VM (**File → Download**)
- ✅ Your screenshots
- ✅ Anything else you generated

Your workbook was never on the VM in the first place — that's the whole point of this page.

---

## 📥 Downloading from this page

1. Click **[Releases](../../releases)** on the right.
2. Find your lab.
3. Under **Assets**, click the file you need. It downloads straight away.

No GitHub account needed.

Each release has both:

- the **workbook / report / insight note** on its own — this is what most of you need
- the **full package zip** — dossier, notebook and dataset, for running locally

---

## 📚 The labs

| Lab | Where you do it | What you build | Data |
|---|---|---|---|
| **1 — Rail Dataset Analysis** | Lab VM | Read, filter and summarise a real timetable dataset in Python; find three insights | French TGV punctuality (SNCF Open Data) |
| **2 — Predictive Maintenance** | Lab VM | Your first ML model: predict compressor failures before they happen | MetroPT-3 metro sensors, Metro do Porto 2020 (UCI) |
| **3 — Dashboard Project** | Looker Studio (browser) | A management dashboard, no code | UK station usage 2024–25 (Office of Rail and Road) |

---

## 📤 What to hand in

| Lab | Deliverables |
|---|---|
| **1** | Completed workbook (3 findings + 1 recommendation) · your `.ipynb` notebook · screenshots of your work |
| **2** | **Written report in your own words** · your `.ipynb` notebook · screenshots of your work |
| **3** | Dashboard (PDF export or share link) · completed insight note |

**On the written work:** explain what the numbers *mean* — for the operations team, for the maintenance team, for the operator. Pasted code output and bare screenshots with no explanation score no marks.

---

## 💻 Running a lab on your own laptop (optional)

You don't need to do this — the VM is easier and already set up. But if you want to:

1. Download the **full package zip** from [Releases](../../releases).
2. **Unzip it properly.** Don't work inside the zip preview, or the notebook won't find its dataset.
3. In the unzipped `notebook` folder:

   ```bash
   pip install jupyterlab pandas matplotlib scikit-learn
   jupyter lab
   ```

4. Open the `.ipynb` and run cells from the top.

Google Colab also works, but you'll have to re-upload the dataset every session, so it's the fiddliest of the three routes.

---

## 🛟 Stuck?

| Problem | What's going on |
|---|---|
| VM won't start | Give it a couple of minutes to spin up. Still nothing — raise a ticket (see below). |
| My work vanished from the VM | The VM reset. Always download your notebook and screenshots before finishing a session. |
| `FileNotFoundError` on my laptop | The CSV isn't next to the notebook. Unzip the package properly. Doesn't happen on the VM. |
| `ModuleNotFoundError` on my laptop | You're not on the VM. Either use the VM, or `pip install` the missing library. |
| A cell errors for no reason | Restart and run from the top: **Kernel → Restart & Run All**. |
| Which workbook is mine? | One per lab — check the lab number in the filename. |

---

## 🎫 Getting help — raise a ticket

If you're still stuck after re-reading the **Insight box** for that step in the Activity Dossier:

> **Open a support ticket on [zralabs.com](https://zralabs.com).**

Every request for help — lab content, a notebook error, a VM that won't start, login trouble — goes through a ticket. Please don't use email or the Teachable classroom for this; tickets get seen and tracked, messages elsewhere don't.

**Your ticket must include:**

1. **Which lab** you're on, and **which step** (e.g. "Lab 2, Step 5 — Your turn cell")
2. **A clear description** of what you did, what you expected, and what actually happened
3. **Screenshots** — the full screen including the error message, not a crop of just the red text

Tickets without a description and screenshots will be sent back for more information, which just slows you down.

---

## 📊 Data sources & licences

All datasets are real and openly licensed. Attribution is required if you reuse them.

- **Lab 1** — SNCF Open Data, *Régularité mensuelle TGV*. Licence Ouverte / Open Licence (Etalab). Column names are French; the notebook renames them to English for you.
- **Lab 2** — MetroPT-3, UCI Machine Learning Repository dataset 791. CC BY 4.0. The genuine air-leak failures of 18 April and 29–30 May 2020 are left in the data.
- **Lab 3** — Office of Rail and Road, Table 1410, *Station usage 2024–25*. Open Government Licence v3.0.

---

## ℹ️ A note on course materials

These are teaching materials of Zenith Railway Academy. You're welcome to keep and reuse them for your own learning and inside your organisation. Please don't resell or republish them as your own.

---

*Need help with anything — a lab, a notebook, the VM, your login? Open a ticket on [zralabs.com](https://zralabs.com) with a description and screenshots.*
