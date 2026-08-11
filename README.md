# 💸 SpendDNA  Your Wallet's Year-End Story

**"Spotify Wrapped," but for your bank statement.**

SpendDNA takes six months of messy, real-world UPI/bank transaction data and turns it into a clean,
screenshot-worthy analytics report — vendor extraction, spending categories, monthly trends,
time-of-day behavior, anomaly detection, and personality-style "spending archetypes" — built entirely
from scratch using only **Python, NumPy, and Pandas**. No regex. No ML libraries. No matplotlib.

> Built as part of **The Unlox Academy's** Week 2 Industry-Graded Minor Project.

---

## 📊 What it does

Given a raw transaction export (1,300+ rows, four different date formats, three different amount
formats, and vendor names buried inside cryptic UPI/POS prefixes), the notebook:

1. **Parses** the mess into a clean DataFrame — every date format, every currency format, standardized transaction types, duplicates dropped.
2. **Extracts real vendor names** from strings like `BUNDL Tech P L` → `Swiggy` (yes, that's Swiggy's actual parent company on a bank statement) using a hand-built keyword dictionary — no regex allowed.
3. **Tags every transaction** into 12+ spending categories (Food Delivery, Quick Commerce, Ecommerce, Transport, Investments, etc.)
4. **Builds an executive summary** — total spend, savings rate, top categories, top vendors.
5. **Tracks monthly trends** per category with a NumPy-powered growth calculation.
6. **Maps time-of-day spending patterns** — when do the late-night food orders actually happen?
7. **Flags anomalous transactions** using a from-scratch z-score calculation (no `scipy`).
8. **Detects spending "archetypes"** — Shopaholic, Investor, YOLO Spender, and more — each with a quantitative detection rule, plus one custom-invented archetype: **The Bengaluru Traffic Survivor**.

Everything is printed as one clean, formatted, ASCII-bar-charted report you'd actually want to
screenshot and share.
--

## 🛠️ Tech Stack

**Used:**
- Python fundamentals (loops, dicts, functions, f-strings, string methods)
- NumPy (arrays, mean, std, percentage calculations)
- Pandas (`read_csv`, `groupby`, `pivot_table`, `.dt`, `.str`, `transform`)

**Deliberately NOT used** (constraint discipline is the point of the project):
- ❌ `re` (regex) — all pattern matching is plain substring matching
- ❌ `matplotlib` / `seaborn` / `plotly` — visualization is text/ASCII-based
- ❌ `scikit-learn` / `scipy.stats` — z-scores computed by hand
- ❌ `pandas-profiling` / `sweetviz` / any auto-EDA tool
- ❌ Any AI/ML library, any external dataset

---

## 📁 Files

| File | Description |
|---|---|
| `SpendDNA_RishiBhuta.ipynb` | The full analysis notebook — 8 features, fully commented |
| `rahul_transactions.csv` | Synthetic 6-month transaction dataset (Jan–Jun 2024) used for grading |

---

## ▶️ How to Run

1. Clone this repo (or open the notebook directly in Google Colab).
2. Make sure `rahul_transactions.csv` is in the same folder as the notebook.
3. Run all cells top to bottom — no configuration needed.

```bash
git clone https://github.com/RishiBhuta/SpeedDNA.git
cd SpeedDNA
jupyter notebook SpendDNA_RishiBhuta.ipynb
```

---

## 🧬 About the Data

The dataset is synthetic — generated to replicate the real messiness of an Indian bank/UPI export
(mixed date formats, mixed currency notations, vendor names buried in UPI prefixes, duplicate rows,
P2P transfers) so the parsing and cleaning logic reflects genuine transaction-analytics work done at
fintechs like Cred, Slice, and Jupiter.

---

## 🙋 About Me

Built by **Rishi Bhuta** — Diploma in Computer Engineering student, exploring Data Analytics & ML
Engineering. Find more of my work on [GitHub](https://github.com/RishiBhuta).

*AI-assistance disclosure: parts of the code structure and vendor dictionary were built with help from
Claude (Anthropic); all logic was tested and verified against this dataset's actual output.*
