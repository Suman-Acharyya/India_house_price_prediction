<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:1e3a8a,100:7c3aed&height=150&section=header&text=Literature%20Review&fontSize=38&fontColor=ffffff&desc=Research%20foundation%20for%20India%20House%20Price%20Prediction&descSize=16&descAlignY=68" alt="Literature Review banner" width="100%"/>

![Papers](https://img.shields.io/badge/papers%20reviewed-6-4f46e5?style=for-the-badge)
![Years](https://img.shields.io/badge/published-2023--2025-0d9488?style=for-the-badge)
![Gaps](https://img.shields.io/badge/research%20gaps-2-db2777?style=for-the-badge)
![Focus](https://img.shields.io/badge/focus-explainability%20%2B%20generalization-f59e0b?style=for-the-badge)

[Purpose](#-purpose) · [Methodology](#-research-methodology) · [Papers](#-selected-papers) · [Comparison](#-comparison-table) · [Gaps](#-research-gaps-identified) · [Our Approach](#-how-this-project-addresses-both-gaps) · [Bibliography](#-bibliography-apa-format)

</div>

---

## 🎯 Purpose

This document records **the papers reviewed, why each was selected, what each contributes, and the research gaps** that justify this project's approach: **multi-city generalization testing** and **SHAP-based explainability**.

It is the academic companion to the main [README](../../README.md) and the [project plan](project-plan-and-structure.md).

---

## 🔬 Research Methodology

Papers were located through searches targeted at academic sources:

<table align="center" width="100%">
  <tr>
    <th align="center" width="25%">Sources searched</th>
    <th align="center" width="25%">Time window</th>
    <th align="center" width="50%">Selection priority</th>
  </tr>
  <tr>
    <td align="center">IEEE Xplore, Springer, MDPI, Emerald, arXiv, ResearchGate-indexed journals, conference proceedings</td>
    <td align="center"><b>2022–2025</b></td>
    <td align="center">Papers that can be verified through a real DOI or publisher link</td>
  </tr>
</table>

---

## 📚 Selected Papers

Six papers in three groups: explainability (1–3), India-specific studies (4–5) and algorithm comparison (6).

### 🧠 Paper 1: Explainability + XGBoost

<table align="center" width="100%">
  <tr><th align="left" width="22%">Title</th><td>eXplainable Machine Learning for Real Estate: XGBoost and Shapley Values in Price Prediction</td></tr>
  <tr><th align="left">Authors</th><td>Kee, T., &amp; Ho, W. K. O.</td></tr>
  <tr><th align="left">Year / Venue</th><td>2025 · Civil Engineering Journal, 11(5), 2116–2133</td></tr>
  <tr><th align="left">DOI</th><td><a href="https://doi.org/10.28991/CEJ-2025-011-05-022">10.28991/CEJ-2025-011-05-022</a></td></tr>
  <tr><th align="left">Algorithms</th><td>XGBoost + SHAP</td></tr>
  <tr><th align="left">Why we use it</th><td>Primary paper justifying our use of SHAP for explainability (<b>Research Gap 1</b>).</td></tr>
</table>

### 🧠 Paper 2: Explainable Determinant Analysis

<table align="center" width="100%">
  <tr><th align="left" width="22%">Title</th><td>Explainable Housing Price Prediction with Determinant Analysis</td></tr>
  <tr><th align="left">Authors</th><td>Teoh, E. Z., Yau, W.-C., Ong, T. S., &amp; Connie, T.</td></tr>
  <tr><th align="left">Year / Venue</th><td>2023 · International Journal of Housing Markets and Analysis, 16(5), 1021–1045</td></tr>
  <tr><th align="left">DOI</th><td><a href="https://doi.org/10.1108/IJHMA-02-2022-0025">10.1108/IJHMA-02-2022-0025</a></td></tr>
  <tr><th align="left">Algorithms</th><td>Multinomial logistic regression + SHAP</td></tr>
  <tr><th align="left">Why we use it</th><td>Reinforces explainability as a recognized, publishable research direction.</td></tr>
</table>

### 🧠 Paper 3: Open Data + XAI in Smart Cities

<table align="center" width="100%">
  <tr><th align="left" width="22%">Title</th><td>The Impacts of Open Data and eXplainable AI on Real Estate Price Predictions in Smart Cities</td></tr>
  <tr><th align="left">Authors</th><td>Trindade Neves, F., Aparicio, M., &amp; de Castro Neto, M.</td></tr>
  <tr><th align="left">Year / Venue</th><td>2024 · Applied Sciences, 14(5), 2209</td></tr>
  <tr><th align="left">DOI</th><td><a href="https://doi.org/10.3390/app14052209">10.3390/app14052209</a></td></tr>
  <tr><th align="left">Algorithms</th><td>XGBoost (Optuna-tuned) + SHAP</td></tr>
  <tr><th align="left">Why we use it</th><td>Supports including rich location and context features (distance to metro, school, hospital, IT hub, AQI).</td></tr>
</table>

### 🇮🇳 Paper 4: India-Specific Comparative Study

<table align="center" width="100%">
  <tr><th align="left" width="22%">Title</th><td>Analysis of the Effectiveness of Predicting Housing Prices Based on Different Machine Learning Models (Bangalore, India case study)</td></tr>
  <tr><th align="left">Authors</th><td>Wang, W.</td></tr>
  <tr><th align="left">Year / Venue</th><td>2024 · Proceedings of MIED 2024</td></tr>
  <tr><th align="left">DOI</th><td><a href="https://doi.org/10.2991/978-94-6463-542-3_50">10.2991/978-94-6463-542-3_50</a></td></tr>
  <tr><th align="left">Algorithms</th><td>Random Forest, Ridge Regression, XGBoost (+ stacking)</td></tr>
  <tr><th align="left">Why we use it</th><td>Key paper supporting <b>Research Gap 2</b>: it tests only one Indian city.</td></tr>
</table>

### 🇮🇳 Paper 5: India-Specific ML Baseline

<table align="center" width="100%">
  <tr><th align="left" width="22%">Title</th><td>House Price Prediction Using Machine Learning</td></tr>
  <tr><th align="left">Authors</th><td>Kalidass, J., Dharshalini, T., Nivetha, R., &amp; Subasri, A. P.</td></tr>
  <tr><th align="left">Year / Venue</th><td>2024 · IRJET, 11(4)</td></tr>
  <tr><th align="left">Algorithms</th><td>Random Forest, Gradient Boosting</td></tr>
  <tr><th align="left">Why we use it</th><td>Second India-specific baseline, reinforcing strong algorithm families for Indian housing data.</td></tr>
</table>

### 📊 Paper 6: Regression Algorithm Comparison

<table align="center" width="100%">
  <tr><th align="left" width="22%">Title</th><td>House Price Prediction: Comparative Analysis of Regression-Based Machine Learning Algorithms</td></tr>
  <tr><th align="left">Authors</th><td>Aniobi, D. E., Ochuba, C. O., &amp; Nguideen, S. B.</td></tr>
  <tr><th align="left">Year / Venue</th><td>2023 · IJRASET</td></tr>
  <tr><th align="left">DOI</th><td><a href="https://doi.org/10.22214/ijraset.2023.56232">10.22214/ijraset.2023.56232</a></td></tr>
  <tr><th align="left">Algorithms</th><td>Linear Regression, Random Forest, Extra Trees, KNN</td></tr>
  <tr><th align="left">Why we use it</th><td>General evidence supporting our own algorithm comparison.</td></tr>
</table>

---

## 🧾 Comparison Table

<table align="center" width="100%">
  <tr>
    <th align="center">#</th>
    <th align="center">Paper</th>
    <th align="center">Year</th>
    <th align="center">Focus area</th>
    <th align="center">Key technique</th>
    <th align="center">Relevance</th>
  </tr>
  <tr><td align="center">1</td><td align="center"><b>Kee &amp; Ho</b></td><td align="center">2025</td><td align="center">Explainability</td><td align="center">XGBoost + SHAP</td><td align="center">Core method for Gap 1</td></tr>
  <tr><td align="center">2</td><td align="center"><b>Teoh et al.</b></td><td align="center">2023</td><td align="center">Explainability</td><td align="center">Regression + SHAP</td><td align="center">Confirms explainability as a real gap</td></tr>
  <tr><td align="center">3</td><td align="center"><b>Trindade Neves et al.</b></td><td align="center">2024</td><td align="center">Context / open data</td><td align="center">XGBoost + SHAP</td><td align="center">Justifies rich location features</td></tr>
  <tr><td align="center">4</td><td align="center"><b>Wang</b></td><td align="center">2024</td><td align="center">India, single city</td><td align="center">RF, Ridge, XGBoost, Stacking</td><td align="center">Core evidence for Gap 2</td></tr>
  <tr><td align="center">5</td><td align="center"><b>Kalidass et al.</b></td><td align="center">2024</td><td align="center">India, baseline ML</td><td align="center">RF, Gradient Boosting</td><td align="center">Confirms strong algorithms for Indian data</td></tr>
  <tr><td align="center">6</td><td align="center"><b>Aniobi et al.</b></td><td align="center">2023</td><td align="center">Algorithm comparison</td><td align="center">Linear Reg, RF, Extra Trees, KNN</td><td align="center">General comparison evidence</td></tr>
</table>

---

## 🕳️ Research Gaps Identified

<table align="center" width="100%">
  <tr>
    <th align="center" width="50%">🧠 Gap 1: Explainability</th>
    <th align="center" width="50%">🌍 Gap 2: Generalization</th>
  </tr>
  <tr>
    <td align="center"><b>Lack of explainability in Indian housing studies.</b><br/><br/>Papers 4 and 5 report accuracy metrics only, with no explanation of which features drive each prediction. Papers 1–3 demonstrate SHAP-based explainability, but on non-Indian datasets. No paper combines SHAP explainability with an India-wide, multi-city dataset.</td>
    <td align="center"><b>Single-city limitation in Indian studies.</b><br/><br/>Both India-focused papers train and evaluate on a single city or dataset, with no test of whether the model generalizes to other Indian cities or tiers.</td>
  </tr>
</table>

---

## 🧩 How This Project Addresses Both Gaps

<table align="center" width="100%">
  <tr>
    <th align="center" width="20%">Component</th>
    <th align="center" width="50%">What we do</th>
    <th align="center" width="30%">Supported by</th>
  </tr>
  <tr>
    <td align="center"><b>Dataset</b></td>
    <td align="center">A synthetic but realistic dataset spanning 60 Indian cities across all city tiers and all major regions</td>
    <td align="center">Fills the India-wide, multi-city data gap</td>
  </tr>
  <tr>
    <td align="center"><b>Modeling</b></td>
    <td align="center">Comparison of Linear Regression, Random Forest and XGBoost</td>
    <td align="center">Papers 4, 5 and 6</td>
  </tr>
  <tr>
    <td align="center"><b>Generalization testing</b></td>
    <td align="center">A dedicated city-holdout split alongside a standard random split</td>
    <td align="center">Addresses <b>Gap 2</b></td>
  </tr>
  <tr>
    <td align="center"><b>Explainability</b></td>
    <td align="center">SHAP applied to the final model</td>
    <td align="center">Papers 1–3 · addresses <b>Gap 1</b></td>
  </tr>
</table>

---

## 📖 Bibliography (APA Format)

- Aniobi, D. E., Ochuba, C. O., & Nguideen, S. B. (2023). House price prediction: Comparative analysis of regression-based machine learning algorithms. *International Journal for Research in Applied Science and Engineering Technology.* https://doi.org/10.22214/ijraset.2023.56232

- Kalidass, J., Dharshalini, T., Nivetha, R., & Subasri, A. P. (2024). House price prediction using machine learning. *International Research Journal of Engineering and Technology, 11*(4).

- Kee, T., & Ho, W. K. O. (2025). eXplainable machine learning for real estate: XGBoost and Shapley values in price prediction. *Civil Engineering Journal, 11*(5), 2116–2133. https://doi.org/10.28991/CEJ-2025-011-05-022

- Teoh, E. Z., Yau, W.-C., Ong, T. S., & Connie, T. (2023). Explainable housing price prediction with determinant analysis. *International Journal of Housing Markets and Analysis, 16*(5), 1021–1045. https://doi.org/10.1108/IJHMA-02-2022-0025

- Trindade Neves, F., Aparicio, M., & de Castro Neto, M. (2024). The impacts of open data and eXplainable AI on real estate price predictions in smart cities. *Applied Sciences, 14*(5), 2209. https://doi.org/10.3390/app14052209

- Wang, W. (2024). Analysis of the effectiveness of predicting housing prices based on different machine learning models. In *Proceedings of the 2024 2nd International Conference on Management Innovation and Economy Development (MIED 2024).* https://doi.org/10.2991/978-94-6463-542-3_50

---

> [!NOTE]
> **Note on the dataset.** This project uses a synthetic dataset generated programmatically to reflect realistic Indian real estate market patterns, disclosed transparently as synthetic rather than scraped real listings. This is independent of the literature review above and does not affect the validity of the research gap or methodology. Dataset details are in [`data/raw/README.md`](../../data/raw/README.md).

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f172a,50:1e3a8a,100:7c3aed&height=100&section=footer" alt="footer wave" width="100%"/>

</div>