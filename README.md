# Machine Learning-Based Prediction of Organic Compound Adsorption onto Microplastics in Freshwater

Mini-project (SMBI603 – ML & AI in Bioinformatics) by Harshada Risbud & Nikita Khandare, 
DES Pune University, under the guidance of Dr. Kushagra Kashyap.

## Problem
Microplastics carry organic pollutants in freshwater. This project predicts the sorption 
coefficient (logKd) — how strongly a compound sticks to microplastics — using ML, 
so experiments can be prioritized instead of tested blindly.

## Dataset
- 1101 adsorption records, 233 unique chemical structures
- 27 RDKit molecular descriptors + particle size + polymer/water category
- Target: logKd

## Approach
- Preprocessing via scikit-learn Pipeline (median imputation, scaling, one-hot encoding)
- Two evaluation strategies compared:
  - Conventional random 80/20 split
  - **Chemical-structure-grouped split** (no compound in both train & test — prevents leakage)
- 6 models compared: Dummy, MLR, Ridge, Random Forest, SVM, XGBoost
- 5-fold cross-validation for both schemes
- Interpretation via feature importance + SHAP

## Key Result
XGBoost performed best in both schemes — but R² dropped from **0.864** (random split) 
to **0.658** (grouped split), showing that a naive random split overstates real-world 
performance on unseen chemicals. Grouped 5-fold CV: R² = 0.753 ± 0.019.

## Tech Stack
Python, pandas, scikit-learn, XGBoost, RDKit, SHAP, Matplotlib

## Files
- `notebook.ipynb` — full pipeline
- `MPAP_Data.csv` — dataset
- `report.pdf` — full project report

## Author
Nikita Khandare, M.Sc. Bioinformatics, DES Pune University
