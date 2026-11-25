<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&height=140&color=0:0f172a,50:1e3a8a,100:7c3aed&text=India%20House%20Prices%20(Synthetic)&fontColor=ffffff&fontSize=34&fontAlignY=38&desc=Dataset%20documentation&descAlignY=62&descSize=16" alt="India House Prices (Synthetic) Dataset" width="100%"/>

<br/>

![Rows](https://img.shields.io/badge/rows-260%2C000-0d9488?style=flat-square)
![Columns](https://img.shields.io/badge/columns-57-4f46e5?style=flat-square)
![Cities](https://img.shields.io/badge/cities-60-7c3aed?style=flat-square)
![States](https://img.shields.io/badge/states%20%2F%20UTs-31-db2777?style=flat-square)
![Years](https://img.shields.io/badge/years-2022%E2%80%932025-ea580c?style=flat-square)
![Type](https://img.shields.io/badge/data-synthetic-f59e0b?style=flat-square)
![Format](https://img.shields.io/badge/format-CSV-64748b?style=flat-square)

<br/>

[Summary](#-summary) · [Generation](#-how-it-was-generated) · [Quick start](#-quick-start) · [Columns](#-column-dictionary) · [Missing values](#-missing-values) · [Use cases](#-use-cases) · [Modeling notes](#-modeling-notes) · [Limitations](#-known-limitations) · [License](#-license)

</div>

---

> [!WARNING]
> **Disclaimer:** this is a **synthetic (artificially generated)** dataset, not real scraped property listings. Prices and property details were generated programmatically using realistic city-wise pricing logic and random variation designed to resemble real Indian housing market patterns.
>
> In any report or citation, always describe it as **"a synthetic dataset modeled on real-world housing market patterns"**. Never describe it as actual collected or scraped listings.

---

## 📊 Summary

<table align="center" width="100%">
<tr>
<th align="center" width="20%">📄 Rows</th>
<th align="center" width="20%">🧱 Columns</th>
<th align="center" width="20%">🏙️ Cities</th>
<th align="center" width="20%">🗺️ States / UTs</th>
<th align="center" width="20%">📅 Years</th>
</tr>
<tr>
<td align="center"><b>260,000</b></td>
<td align="center"><b>57</b></td>
<td align="center"><b>60</b></td>
<td align="center"><b>31</b></td>
<td align="center"><b>2022–2025</b></td>
</tr>
</table>

<br/>

<table align="center" width="100%">
<tr>
<th align="center" width="30%">Item</th>
<th align="center" width="70%">Detail</th>
</tr>
<tr>
<td align="center">📁 File name</td>
<td align="center"><code>india_house_prices_synthetic.csv</code></td>
</tr>
<tr>
<td align="center">📦 Size</td>
<td align="center">~78.5 MB</td>
</tr>
<tr>
<td align="center">🔤 Format</td>
<td align="center">CSV (UTF-8, comma-separated)</td>
</tr>
<tr>
<td align="center">🎯 Target variable</td>
<td align="center"><code>price_inr</code> (total price in INR)<br/><code>price_per_sqft</code> (alternative target)</td>
</tr>
<tr>
<td align="center">📅 Time range</td>
<td align="center">Listings dated 2022–2025</td>
</tr>
<tr>
<td align="center">🌍 Geographic coverage</td>
<td align="center">60 cities across 31 states / UTs</td>
</tr>
</table>

<br/>

**City tiers:** 8 metro · 28 tier-2 · 24 tier-3 towns

<table align="center" width="100%">
<tr>
<th align="center" width="30%">Tier</th>
<th align="center" width="20%"><code>city_tier</code> value</th>
<th align="center" width="20%">Cities</th>
<th align="center" width="30%">Share of the 60 cities</th>
</tr>
<tr>
<td align="center">🏙️ Metro</td>
<td align="center"><code>1</code></td>
<td align="center"><b>8</b></td>
<td align="center"><code>▓░░░░░░░░░</code> 13%</td>
</tr>
<tr>
<td align="center">🏢 Tier-2</td>
<td align="center"><code>2</code></td>
<td align="center"><b>28</b></td>
<td align="center"><code>▓▓▓▓▓░░░░░</code> 47%</td>
</tr>
<tr>
<td align="center">🏘️ Tier-3</td>
<td align="center"><code>3</code></td>
<td align="center"><b>24</b></td>
<td align="center"><code>▓▓▓▓░░░░░░</code> 40%</td>
</tr>
</table>

---

## ⚙️ How It Was Generated

| Step | What happens | Detail |
|:---:|:---|:---|
| **1** | 🏙️ **City base prices** | Each of the 60 cities gets a realistic price-per-sqft range based on known market tiers. For example, Mumbai is Rs. 14,000–32,000/sqft, and a tier-3 town is Rs. 1,800–4,000/sqft. |
| **2** | 🏠 **Property-level simulation** | Price per sqft is adjusted for age, floor level, furnishing, amenity count, RERA status, construction status, property type, distance to city center and metro, and builder reputation. |
| **3** | 🎲 **Random market noise** | About ±7% random variation is added to mimic real-world unpredictability. |
| **4** | 💰 **Final price** | `price_inr = price_per_sqft × super_built_up_area_sqft` |

---

## 🚀 Quick start

```python
import pandas as pd

df = pd.read_csv(
    "data/raw/india_house_prices_synthetic.csv",
    parse_dates=["listing_date"],
)

print(df.shape)   # (260000, 57)
df.head()
```

> [!TIP]
> If the file is only a few lines of text, Git LFS did not download it. Run `git lfs pull` in the project folder.

---

## 📖 Column Dictionary

All 57 columns, grouped by purpose. The `#` column is the position in the CSV.

| Group | Columns | `#` range |
|:---|:---:|:---:|
| 🆔 Identification and time | 2 | 1–2 |
| 📍 Location | 6 | 3–8 |
| 🏠 Property details | 16 | 9–24 |
| 🛋️ Amenities and features | 11 | 25–35 |
| 🚇 Proximity | 9 | 36–44 |
| 🌿 Environment | 3 | 45–47 |
| 🤝 Seller, legal and market | 8 | 48–55 |
| 🎯 Targets | 2 | 56–57 |

Types: `0/1` means a binary flag (1 = yes, 0 = no).

### 🆔 Identification and time

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 1 | `property_id` | string | Unique listing ID |
| 2 | `listing_date` | date | Date listed (2022–2025) |

### 📍 Location

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 3 | `city` | string | City name |
| 4 | `state` | string | State / Union Territory |
| 5 | `city_tier` | int | 1 = metro, 2 = tier-2, 3 = tier-3 |
| 6 | `locality` | string | Simulated neighborhood name |
| 7 | `latitude` | float | Approx. property latitude |
| 8 | `longitude` | float | Approx. property longitude |

### 🏠 Property details

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 9 | `property_type` | string | Apartment / Villa / Independent House / Penthouse / Builder Floor / Studio |
| 10 | `bhk` | int | Number of bedrooms (1–5) |
| 11 | `super_built_up_area_sqft` | float | Total built-up area |
| 12 | `carpet_area_sqft` | float | Usable indoor area |
| 13 | `plot_area_sqft` | float | Land area (villas / independent houses; blank for apartments/studios) |
| 14 | `bathrooms` | int | Number of bathrooms |
| 15 | `balconies` | int | Number of balconies |
| 16 | `floor_no` | int | Floor of the unit |
| 17 | `total_floors` | int | Total floors in building |
| 18 | `age_of_property_years` | int | Age of property |
| 19 | `construction_status` | string | Ready to Move / Under Construction |
| 20 | `possession_status` | string | Immediate / Within 6 Months / 1 Year / 2 Years |
| 21 | `furnishing_status` | string | Unfurnished / Semi-Furnished / Furnished |
| 22 | `facing` | string | Direction the unit faces |
| 23 | `parking_spots` | int | Number of parking spots |
| 24 | `society_type` | string | Gated Society / Standalone Building / Township |

### 🛋️ Amenities and features

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 25 | `has_lift` | 0/1 | Lift available |
| 26 | `has_gym` | 0/1 | Gym available |
| 27 | `has_swimming_pool` | 0/1 | Pool available |
| 28 | `has_clubhouse` | 0/1 | Clubhouse available |
| 29 | `has_power_backup` | 0/1 | Power backup available |
| 30 | `has_security_24x7` | 0/1 | 24x7 security |
| 31 | `has_park` | 0/1 | Park / garden available |
| 32 | `has_rainwater_harvesting` | 0/1 | Rainwater harvesting |
| 33 | `has_solar_panels` | 0/1 | Solar panels installed |
| 34 | `is_pet_friendly` | 0/1 | Pet friendly |
| 35 | `vastu_compliant` | 0/1 | Vastu-compliant layout |

### 🚇 Proximity

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 36 | `distance_to_city_center_km` | float | Distance to city center |
| 37 | `city_has_metro` | 0/1 | Whether the city has a metro system |
| 38 | `distance_to_metro_km` | float | Distance to nearest metro station (blank if no metro) |
| 39 | `distance_to_airport_km` | float | Distance to nearest airport |
| 40 | `distance_to_railway_station_km` | float | Distance to nearest railway station |
| 41 | `distance_to_school_km` | float | Distance to nearest school |
| 42 | `distance_to_hospital_km` | float | Distance to nearest hospital |
| 43 | `distance_to_mall_km` | float | Distance to nearest mall |
| 44 | `distance_to_it_hub_km` | float | Distance to nearest IT park / business hub |

### 🌿 Environment

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 45 | `water_supply` | string | Municipal / Borewell / Both |
| 46 | `flood_risk_zone` | string | Low / Medium / High |
| 47 | `air_quality_index` | float | Simulated AQI |

### 🤝 Seller, legal and market

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 48 | `builder_reputation_score` | float | Score 1–10 |
| 49 | `seller_type` | string | Owner / Agent / Builder |
| 50 | `rera_registered` | 0/1 | RERA registration status |
| 51 | `ownership_type` | string | Freehold / Leasehold / Co-operative Society |
| 52 | `property_tax_annual_inr` | float | Annual property tax (INR) |
| 53 | `maintenance_charges_monthly_inr` | float | Monthly maintenance (INR) |
| 54 | `days_on_market` | int | Days the listing has been active |
| 55 | `is_negotiable` | string | Yes / No |

### 🎯 Targets

| # | Column | Type | Description |
|:---:|:---|:---:|:---|
| 56 | `price_inr` | float | **Target:** total listed price (INR) |
| 57 | `price_per_sqft` | float | Price per square foot (INR). Alternative target |

---

## 🕳️ Missing values

Two columns contain **intentional** blanks. They are expected and are not data errors.

| Column | Blank when | Why |
|:---|:---|:---|
| `plot_area_sqft` | The property is an apartment or studio | Only villas and independent houses have their own plot |
| `distance_to_metro_km` | `city_has_metro` is 0 | The city has no metro system, so there is no nearest station |

---

## 🧭 Use cases

| Use case | Example |
|:---|:---|
| 📈 **Regression** | Predict `price_inr` with Linear Regression, Random Forest, XGBoost and others |
| ⚖️ **Model comparison** | Compare algorithms on the same split |
| 🌍 **Cross-city generalization** | Train on some cities or tiers, test on others |
| 🧠 **Explainable AI** | Apply SHAP to explain individual price predictions |
| 🔍 **Feature importance** | Find which amenities and distances matter most |
| 📊 **EDA** | Price trends by city tier, BHK, property type and furnishing status |

---

## 🛡️ Modeling notes

> [!IMPORTANT]
> `price_inr` is computed as `price_per_sqft × super_built_up_area_sqft`, so the two targets are directly linked. When predicting one, **exclude the other from the features**, or the model gets the answer for free (target leakage).

- **Identifier:** `property_id` is a unique ID per listing, so it carries no pricing information. Drop it before training.
- **Missing values:** handle the two intentional blanks above on purpose, for example with an indicator or a fill value, rather than dropping those rows.
- **Cross-city testing:** split by `city` (or `city_tier`) so the test set contains cities the model has never seen.

---

## 🚧 Known limitations

> [!WARNING]
> - **Synthetic data:** prices are simulated, not observed real transactions. Treat absolute values as illustrative only.
> - **Generated localities:** locality names are generated, not real neighborhood names.
> - **No market shocks:** the data does not reflect real short-term market events such as policy changes or local demand shocks.
> - **Intentional blanks:** `plot_area_sqft` and `distance_to_metro_km` contain missing values where not applicable. This is expected, not a data error.

---

## 📄 License

Free to use for **educational and academic purposes** (student project / coursework use). Because this is synthetic data generated for this project, there are no third-party data rights attached. Always label it as **synthetic** when it is used or shared.

<br/>

⬅️ Back to the [main project README](../../README.md)

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&section=footer&height=100&color=0:0f172a,50:1e3a8a,100:7c3aed" alt="Footer" width="100%"/>

</div>