# 📊 Business Trends & Forecasting in Vancouver  
### UBC DSCI DataQuest 2025 — Team Saya Very Mager (SVM)

This repository contains our complete analytical pipeline for the DataQuest 2025 competition.  
We analyze **Vancouver’s business licence data from 1997–2025**, quantify the impact of COVID-19, evaluate long-term business survival, and forecast sector- and neighborhood-level activity for **2026–2035** using a weighted ensemble of modern forecasting models.

Our official presentation deck is included in:  
**`SVM.pdf`**

---

# 📝 Abstract

Vancouver’s business ecosystem experienced significant disruption during COVID-19, with highly uneven recovery across sectors. Using 28 years of business-licence data, we built an end-to-end pipeline combining **EDA**, **COVID impact quantification**, **Kaplan–Meier survival analysis**, and a **multi-model ensemble forecaster**.  
Our results identify which industries show long-term resilience, which sectors require strategic pivots, and where future business growth is likely to concentrate geographically.

---

# 🗂 Repository Structure

```

root/
│── README.md
│── SVM.pdf                         # Final presentation deck (DataQuest submission)
│
│── source/
│    ├── Graphs.ipynb               # EDA + sector trends + geographic maps
│    ├── BusinessTrends&COVID19.ipynb   # COVID impact + recovery analysis
│    ├── EnsembleModel.ipynb        # Forecasting models + weighted ensemble
│
│── data/
│    ├── business_licences_1997_2012.csv
│    ├── business_licences_2013_2024.csv
│    ├── business_licences_2024_present.csv

````

---

# 🎯 Problem Statement

**Goal:** Determine which types of businesses will grow, remain stable, or decline in Vancouver over the next decade.

We address:
- Long-term sector trends (1997–2025)  
- COVID-19 disruption + recovery  
- Business longevity by industry  
- Forecasts for 11 sectors × 22 neighborhoods (2026–2035)  

---

# 🧠 Methodology Overview

### **1. Data Preparation**
- Combined all datasets (1997–2012, 2013–2024, 2024–present)  
- Standardized categories (80+ → 12 major sectors)  
- Built unique business identifiers  
- Created COVID phase labels (pre, during, post)  
- Aggregated by LocalArea × BusinessType × Year  

### **2. EDA & Geographic Analysis**
- New vs. active business trends  
- Long-term sector shifts  
- Deck.gl neighborhood-level mapping  

### **3. COVID-19 Impact & Recovery**
Using formulas from slide 8: :contentReference[oaicite:1]{index=1}  
- **Impact %** = Change during COVID vs. pre-COVID  
- **Recovery %** = Change post-COVID vs. during COVID  

### **4. Survival Analysis (Kaplan–Meier)**
- Estimated business longevity curves for all 12 sectors  
- Identified sectors with highest long-term survival probabilities  

### **5. Forecasting Framework (2026–2035)**
Using a weighted ensemble (slide 14–15):
| Model | Weight | Purpose |
|-------|--------|----------|
| **PatchTST** | 30% | Transformer for long-horizon trends |
| **N-BEATS** | 30% | Robust for short series |
| **CatBoost** | 30% | Strong tabular ML with lag features |
| **Naive** | 10% | Stable baseline for sparse annual data |

### **6. Outputs**
- Forecasts for all BusinessType × LocalArea pairs  
- Sector-level and neighborhood-level projections  

---

# 🧪 Key Findings

### 📉 COVID-19 Impact (slide 9)  
Most negatively affected sectors:  
- **Education, Arts & Entertainment** (−16.2%)  
- **Logistics & Transportation** (−9.8%)  
- **Personal & Beauty Services** (−9.0%)  

### 📈 Post-COVID Recovery (slide 10)  
Fastest recovery:  
- **Healthcare & Wellness** (+42.4%)  
- **Logistics & Transportation** (+25.4%)  
- **Financial Services** (+21.6%)  

### 🔒 Survival Analysis (slide 11)  
Highest long-term survival:  
- **Healthcare & Wellness**  
- **Real Estate & Property**  
- **Logistics & Transportation**  

### 🔮 Forecast 2026–2035 (slides 16–21)  
Growth sectors:  
- Technology & Digital  
- Healthcare & Wellness  
- Personal & Beauty Services  
- Logistics & Transportation  

Declining sectors:  
- Construction & Building  
- Business & Professional Services  
- Education, Arts & Entertainment  

---

# 🔧 Reproducibility Instructions

### **1. Install Dependencies**
(Provide your environment or let us generate `requirements.txt` for you.)
```bash
pip install -r requirements.txt
````

### **2. Run Notebooks (in order)**

1. `Graphs.ipynb`
2. `BusinessTrends&COVID19.ipynb`
3. `EnsembleModel.ipynb`

All figures and outputs in the presentation are reproducible from these notebooks.

---

# ✔ Competition Evaluation Alignment

Our submission meets all DataQuest evaluation criteria:

### **✓ Technical Rigor**

Clear methodology spanning preprocessing → analysis → forecasting.

### **✓ Interpretability**

COVID impact charts, survival curves, and easy-to-read sector rankings.

### **✓ Reproducibility**

All results can be regenerated via three notebooks.

### **✓ Insight Quality**

Specific, actionable findings by sector and geography.

### **✓ Forward-Looking Analysis**

10-year forecasts with modern ML + DL ensembles.

### **✓ Clear Communication**

Matches SVM.pdf deck exactly with consistent output.

---

# 🙏 Acknowledgements

Data sources and references listed in slide 24 of `SVM.pdf`.  
