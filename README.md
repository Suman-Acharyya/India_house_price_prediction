# 🏠 India House Price Prediction (ML Project)

![Python](https://img.shields.io/badge/Python-3.14-blue)
![uv](https://img.shields.io/badge/package_manager-uv-purple)
![Status](https://img.shields.io/badge/status-in_progress-yellow)
![License](https://img.shields.io/badge/license-Academic-lightgrey)

A research-backed, end-to-end Machine Learning project that predicts house prices across India, tests whether models generalize across different cities, and explains *why* each price was predicted using SHAP — built as a final-year academic project.

---

## 📌 Project Overview

Most existing house price prediction projects are trained and tested on a single Indian city and give a price with no explanation of *why*. This project aims to fix both problems by:

1. Training on data from **58 cities across India** (metro, tier-2, tier-3)
2. **Testing whether a model trained on some cities still works on others** (generalization test)
3. Using **SHAP (explainable AI)** to show which features drove each predicted price
4. Deploying the final model as a simple, usable web app

---

## 📊 Dataset

- **File:** [`data/raw/india_house_prices_synthetic.csv`](data/raw/india_house_prices_synthetic.csv)
- **Full documentation:** [`reports/India_House_Prices_Dataset_README.pdf`](reports/India_House_Prices_Dataset_README.pdf) — includes column dictionary, methodology, and disclosures
- 260,000 property listings, 57 columns, 58 cities
- **Important:** this is a synthetic dataset modeled on realistic Indian housing market patterns (not scraped real listings) — see the PDF above for full disclosure

---

## 🎯 Project Objectives

1. Build an ML model to predict house prices from property, amenity, and location features
2. Compare multiple algorithms (Linear Regression, Random Forest, XGBoost/Gradient Boosting)
3. Test generalization across different cities/city tiers
4. Explain predictions using SHAP
5. Deploy as a simple Streamlit web app

---

## 🗂️ Project Structure

```
india-house-price-prediction/
├── data/
│ ├── raw/ # original dataset (untouched)
│ └── processed/ # cleaned data (added in later steps)
├── notebooks/ # Jupyter notebooks for EDA & experiments
├── src/ # reusable Python scripts (cleaning, training, etc.)
├── models/ # saved trained model files
├── app/ # Streamlit app (added in deployment phase)
├── reports/ # dataset README, charts, final report
├── pyproject.toml # project dependencies (managed by uv)
└── README.md 
```


---

## 🛠️ Tech Stack

- **Language:** Python 3.14
- **Package manager:** [uv](https://github.com/astral-sh/uv)
- **Data & ML:** pandas, numpy, scikit-learn, matplotlib, seaborn
- **Explainability:** SHAP (added later)
- **Deployment:** Streamlit (added later)

---

## 🚀 How to Run This Project

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/india-house-price-prediction.git
cd india-house-price-prediction

# Set up environment with uv
uv venv
.venv\Scripts\activate        # Windows
uv sync                       # installs all dependencies from pyproject.toml

# Launch Jupyter to explore notebooks
uv run jupyter notebook
```

---

## 🗺️ Project Roadmap / Progress

- [x] Problem statement & objectives finalized
- [x] Dataset created & documented
- [ ] Exploratory Data Analysis
- [ ] Data cleaning & preprocessing
- [ ] Feature engineering
- [ ] Baseline model (Linear Regression)
- [ ] Model comparison (Random Forest, XGBoost, etc.)
- [ ] Hyperparameter tuning
- [ ] Multi-city generalization testing
- [ ] SHAP explainability
- [ ] Model saving
- [ ] Streamlit app
- [ ] Deployment
- [ ] Final report & documentation

*(This checklist will be updated as each step is completed.)*

---

## 📄 License

This project is for academic/educational purposes.