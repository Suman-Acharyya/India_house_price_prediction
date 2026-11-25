<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:1e3a8a,100:7c3aed&height=150&section=header&text=Project%20Plan%20and%20Structure&fontSize=38&fontColor=ffffff&desc=India%20House%20Price%20Prediction&descSize=16&descAlignY=68" alt="Project Plan and Structure banner" width="100%"/>

![Status](https://img.shields.io/badge/status-in%20progress-f59e0b?style=for-the-badge)
![Progress](https://img.shields.io/badge/progress-1%2F16%20steps-0d9488?style=for-the-badge)
![Phases](https://img.shields.io/badge/phases-5-4f46e5?style=for-the-badge)
![Git](https://img.shields.io/badge/git-branch%20per%20phase-f05032?style=for-the-badge&logo=git&logoColor=white)

[Summary](#-project-summary) · [Tech Stack](#-tech-stack) · [Folder Structure](#-folder-structure) · [Git Workflow](#-git-workflow) · [Roadmap](#-roadmap) · [Design Decisions](#-key-design-decisions) · [Related Docs](#-related-documents)

</div>

---

This document explains **what we are building, with which tools, how the files are organized, and in what order the work happens**. It is the planning companion to the main [README](../../README.md).

---

## 🔎 Project Summary

The project tackles two gaps found in the literature (see [research-literature-review.md](research-literature-review.md)).

<table align="center" width="100%">
  <tr>
    <th align="center" width="50%">🧠 Gap 1: Explainability</th>
    <th align="center" width="50%">🌍 Gap 2: Generalization</th>
  </tr>
  <tr>
    <td align="center">Most house price models predict well but cannot say <b>why</b>. We use <b>SHAP</b> and a <b>Streamlit</b> app to show what drives each prediction.</td>
    <td align="center">Most studies test on cities they already trained on. We test on <b>unseen cities</b> with a city-holdout split and compare it with a random split.</td>
  </tr>
</table>

> [!NOTE]
> The dataset is **synthetic** (260,000 rows, 57 columns, 60 cities, 31 states/UTs, 2022–2025). In any report, describe it as *"a synthetic dataset modeled on real-world housing market patterns"*, never as scraped listings. Details are in [`data/raw/README.md`](../../data/raw/README.md).

---

## 🧰 Tech Stack

<table align="center" width="100%">
  <tr>
    <th align="center">Tool</th>
    <th align="center">Purpose</th>
    <th align="center">Why this one</th>
  </tr>
  <tr><td align="center"><b>Python</b></td><td align="center">Main language</td><td align="center">Standard for data science; version pinned in <code>.python-version</code></td></tr>
  <tr><td align="center"><b>uv</b></td><td align="center">Environment and dependencies</td><td align="center">Fast, reproducible installs from <code>pyproject.toml</code> and <code>uv.lock</code></td></tr>
  <tr><td align="center"><b>pandas</b></td><td align="center">Data loading and cleaning</td><td align="center">Handles a 260,000-row table easily</td></tr>
  <tr><td align="center"><b>NumPy</b></td><td align="center">Numeric operations</td><td align="center">Foundation for pandas and scikit-learn</td></tr>
  <tr><td align="center"><b>matplotlib / seaborn</b></td><td align="center">Charts</td><td align="center">Clear EDA and report figures</td></tr>
  <tr><td align="center"><b>scikit-learn</b></td><td align="center">Splits, models, metrics, tuning</td><td align="center">Consistent API for all baseline models</td></tr>
  <tr><td align="center"><b>XGBoost</b></td><td align="center">Gradient boosting model</td><td align="center">Strong on tabular data</td></tr>
  <tr><td align="center"><b>SHAP</b></td><td align="center">Explaining predictions</td><td align="center">Works well with tree-based models</td></tr>
  <tr><td align="center"><b>Streamlit</b></td><td align="center">Interactive app</td><td align="center">Turns a model into a web app with little code</td></tr>
  <tr><td align="center"><b>Jupyter</b></td><td align="center">Notebooks</td><td align="center">Good for step-by-step exploration</td></tr>
  <tr><td align="center"><b>Git + Git LFS</b></td><td align="center">Version control and large files</td><td align="center">Tracks code and keeps the ~78.5 MB CSV manageable</td></tr>
  <tr><td align="center"><b>VS Code</b></td><td align="center">Editor</td><td align="center">Notebooks, terminal and Git in one place</td></tr>
</table>

---

## 📁 Folder Structure

```text
india-house-price-prediction/
├── 📂 data/
│   ├── 📂 raw/                  # original dataset (never modified)
│   │   ├── 📄 india_house_prices_synthetic.csv
│   │   └── 📄 README.md         # dataset documentation
│   └── 📂 processed/            # cleaned and engineered data
├── 📂 notebooks/                # EDA, cleaning, modeling, SHAP
├── 📂 src/                      # reusable code
├── 📂 models/                   # saved model and explainer
├── 📂 app/                      # Streamlit app
├── 📂 reports/
│   ├── 📂 charts/               # figures for the report
│   └── 📂 docs/
│       ├── 📄 project-plan-and-structure.md
│       └── 📄 research-literature-review.md
├── 📄 .python-version
├── 📄 pyproject.toml
├── 📄 uv.lock
├── 📄 requirements.txt
└── 📄 README.md
```

> [!IMPORTANT]
> `data/raw/` is **never modified**. All cleaning and feature work writes to `data/processed/`, so the original data can always be recovered.

---

## 🌿 Git Workflow

We use **one branch per phase**. When a phase is finished, merge it through a Pull Request **immediately**, then start the next branch from an updated `main`.

<table align="center" width="100%">
  <tr>
    <th align="center" width="8%">Step</th>
    <th align="center" width="42%">What you do</th>
    <th align="center" width="50%">Commands</th>
  </tr>
  <tr>
    <td align="center"><b>1</b></td>
    <td align="center">Create a branch for the phase</td>
    <td align="center"><code>git checkout -b phase-name</code></td>
  </tr>
  <tr>
    <td align="center"><b>2</b></td>
    <td align="center">Work, then save and push</td>
    <td align="center"><code>git add .</code><br/><code>git commit -m "message"</code><br/><code>git push -u origin phase-name</code></td>
  </tr>
  <tr>
    <td align="center"><b>3</b></td>
    <td align="center">Open a Pull Request on GitHub, merge it, then update local <code>main</code></td>
    <td align="center"><code>git checkout main</code><br/><code>git pull origin main</code></td>
  </tr>
  <tr>
    <td align="center"><b>4</b></td>
    <td align="center">Start the next phase</td>
    <td align="center"><code>git checkout -b next-phase-name</code></td>
  </tr>
</table>

---

## 🧭 Roadmap

![Overall](https://img.shields.io/badge/OVERALL-6%25-0d9488?style=flat-square)
![Done](https://img.shields.io/badge/DONE-1-16a34a?style=flat-square)
![In progress](https://img.shields.io/badge/IN%20PROGRESS-1-f59e0b?style=flat-square)
![To do](https://img.shields.io/badge/TO%20DO-14-94a3b8?style=flat-square)

```text
▓░░░░░░░░░░░░░░░░░░░  1 of 16 steps complete
```

<table align="center" width="100%">
  <tr>
    <th align="center">Phase</th>
    <th align="center">Focus</th>
    <th align="center">Steps</th>
    <th align="center">Progress</th>
  </tr>
  <tr><td align="center"><b>1</b></td><td align="center">Foundation</td><td align="center">1</td><td align="center">1 / 1 ✅</td></tr>
  <tr><td align="center"><b>2</b></td><td align="center">Exploration and Cleaning</td><td align="center">2–5</td><td align="center">0 / 4 🚧</td></tr>
  <tr><td align="center"><b>3</b></td><td align="center">Modeling</td><td align="center">6–10</td><td align="center">0 / 5 ⬜</td></tr>
  <tr><td align="center"><b>4</b></td><td align="center">Explainability</td><td align="center">11–12</td><td align="center">0 / 2 ⬜</td></tr>
  <tr><td align="center"><b>5</b></td><td align="center">Deployment</td><td align="center">13–16</td><td align="center">0 / 4 ⬜</td></tr>
</table>

### Phase 1: Foundation

| # | Step | What you do | Why | Status |
|:-:|------|-------------|-----|:------:|
| 1 | Environment & dataset setup | Install Python with uv, pin the version in `.python-version`, sync dependencies from `pyproject.toml`, and generate the synthetic dataset (260,000 rows, 60 cities) | Anyone can reproduce the setup, and the data this whole project depends on exists | ✅ |

### Phase 2: Exploration and Cleaning

| # | Step | What you do | Why | Status |
|:-:|------|-------------|-----|:------:|
| 2 | EDA | Inspect distributions, missing values and correlations for both targets | Understand the data before changing it | 🚧 |
| 3 | Data cleaning | Fix types, check duplicates and outliers, handle the intentional blanks | Models need consistent input | ⬜ |
| 4 | Deeper EDA by city and tier | Compare prices and features across cities and tiers | Shows how hard generalization to new cities may be | ⬜ |
| 5 | Feature engineering | Encode categories, transform skewed values, drop `property_id`, keep both targets out of the features | Prepares model-ready data without leakage | ⬜ |

### Phase 3: Modeling

| # | Step | What you do | Why | Status |
|:-:|------|-------------|-----|:------:|
| 6 | Train-test split | Build Path A (random 80/20) and Path B (city-holdout across all three tiers) | The two splits are the core of the experiment | ⬜ |
| 7 | Baseline Linear Regression | Fit Linear Regression on both splits | A simple reference point | ⬜ |
| 8 | Compare algorithms | Fit Random Forest and XGBoost / Gradient Boosting on both splits | Shows whether complex models generalize better | ⬜ |
| 9 | Hyperparameter tuning | Tune with `GridSearchCV` or `RandomizedSearchCV` | Gets the best from each algorithm | ⬜ |
| 10 | Final evaluation | Score all models on both splits (MAE, RMSE, R²) and compute the generalization gap | Answers the first research question | ⬜ |

### Phase 4: Explainability

| # | Step | What you do | Why | Status |
|:-:|------|-------------|-----|:------:|
| 11 | Multi-city generalization analysis | Break down errors by city and tier | Shows where the model fails on unseen cities | ⬜ |
| 12 | SHAP | Create global and per-prediction explanations | Answers the second research question | ⬜ |

### Phase 5: Deployment

| # | Step | What you do | Why | Status |
|:-:|------|-------------|-----|:------:|
| 13 | Save model | Save the model and explainer with `joblib` | The app can load them without retraining | ⬜ |
| 14 | Build Streamlit app | Create inputs, price output and a SHAP explanation view | Makes the results usable | ⬜ |
| 15 | Deploy app | Publish the app online | Lets others try it | ⬜ |
| 16 | Test complete app | Test the whole flow from input to explanation | Catches problems before the final report | ⬜ |

---

## 💡 Key Design Decisions

<table align="center" width="100%">
  <tr>
    <th align="center" width="5%">#</th>
    <th align="center" width="25%">Decision</th>
    <th align="center" width="70%">Reason</th>
  </tr>
  <tr><td align="center">1</td><td align="center"><b>Tree-based models</b></td><td align="center">Confirmed multicollinearity among property features makes plain linear models unreliable; tree-based models handle it better.</td></tr>
  <tr><td align="center">2</td><td align="center"><b>Log-transformation of prices</b></td><td align="center">Prices are right-skewed; a log transform stabilizes training and reduces the effect of extreme values.</td></tr>
  <tr><td align="center">3</td><td align="center"><b>SHAP for explanations</b></td><td align="center">Relationships between features and price were non-linear, and SHAP explains such models both globally and per prediction.</td></tr>
  <tr><td align="center">4</td><td align="center"><b>Ordinal for <code>flood_risk_zone</code>, one-hot for the others</b></td><td align="center">Flood risk has a natural order; other categories do not.</td></tr>
  <tr><td align="center">5</td><td align="center"><b>Dedicated city-holdout test set</b></td><td align="center">Held-out cities across all three tiers give an honest test of generalization to unseen cities.</td></tr>
</table>

---

## 📚 Related Documents

| Document | Description |
|----------|-------------|
| [Main README](../../README.md) | Project overview, setup and roadmap |
| [Dataset README](../../data/raw/README.md) | Column dictionary and dataset notes |
| [Literature review](research-literature-review.md) | Six academic papers behind the project |

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:1e3a8a,100:7c3aed&height=100&section=footer" alt="footer wave" width="100%"/>

</div>