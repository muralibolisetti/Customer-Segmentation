# Customer Personality Analysis & Segmentation

This project implements an end-to-end data preparation, cleaning, feature engineering, and exploratory analysis pipeline for customer segmentation using demographic, transactional, and campaign response data.

---

## 📊 Project Results & Key Findings

### 1. Data Cleaning & Preprocessing Summary

* **Raw Shape:** 2,240 records across 29 features.


* **Missing Value Imputation:** 24 missing values in `Income` were median-imputed.


* **Outlier Removal:** Records with `Age >= 100` or `Income >= 600,000` were removed.


* **Final Processed Shape:** 2,236 records and 32 features.



### 2. Feature Engineering Summary

* **Demographic Metrics:** Extracted `Age` from birth year, simplified `Education` into 3 tiers (Undergraduate, Graduate, Postgraduate), and mapped `Marital_Status` into `Partner` vs. `Single`.


* **Household Dynamics:** Created `Children` (`Kidhome` + `Teenhome`), `Family_Size`, and binary `Is_Parent`.


* **Transactional Aggregations:** Derived `Total_Spending` across all product categories, `Total_Purchases` across all sales channels, and `Total_Accepted_Campaigns`.


* **Tenure:** Computed `Customer_Days` relative to the latest enrollment date.



### 3. Feature Correlation Analysis

![Heat Correlation Map](./cottelation_heatmap.jpeg)
(Extracted from the analysis notebook output)

#### Key Correlation Takeaways:

* **Income vs. Spending:** Strong positive correlation between `Income` and `Total_Spending`, with high-income customers spending heavily on `MntWines` and `MntMeatProducts`.


* **Family Structure Impact:** The presence of children (`Children`, `Is_Parent`) negatively correlates with total spending, while showing higher deal-seeking behavior (`NumDealsPurchases`).


* **Channel Utilization:** In-store (`NumStorePurchases`) and catalog (`NumCatalogPurchases`) purchases scale positively with income, whereas `NumWebVisitsMonth` shows an inverse relationship with total monetary value.



---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python 3.9+


* **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `scipy`


---

## 📂 Repository Structure

```text
├── data/
│   └── marketing_campaign.csv          # Raw dataset
├── images/
│   └── correlation_heatmap.png         # Generated feature correlation matrix
├── notebooks/
│   └── mlpbl.ipynb                     # Data cleaning & EDA notebook
├── extract_images.py                   # Script to dump Base64 plots from .ipynb
├── requirements.txt                    # Project dependencies
└── README.md                           # Documentation & results

```

---

## 🚀 How to Run

1. **Clone the repository:**
```bash
git clone https://github.com/<your-username>/customer-personality-analysis.git
cd customer-personality-analysis

```


2. **Install dependencies:**
```bash
pip install -r requirements.txt

```


3. **Extract embedded images from the notebook:**
```bash
python extract_images.py

```


4. **Run the Jupyter Notebook:**
```bash
jupyter notebook notebooks/mlpbl.ipynb

```
