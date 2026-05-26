# Vertical-Farming-Cost-Prediction
Regression-based operational cost prediction for vertical farming using hybrid microgrid data
# 🌱 Operational Cost Prediction for Vertical Farming with Hybrid Microgrid Systems

> Predicting energy-based operational costs of vertical farming systems using regression models — RWTH Aachen University, Machine Learning Course (Group 6)

---

## 📌 Overview

Vertical farming offers a sustainable solution to urban food security, but high operational costs — especially energy expenses — remain a major barrier to large-scale adoption.

This project builds a supervised regression pipeline to predict the **dual objective value** (operational cost lower bound) of a vertical farming system integrated with a **Hybrid Microgrid (HMG)**. Accurate cost prediction supports financial planning, energy mix optimization, and investment feasibility analysis.

---

## 📊 Dataset

| Property | Details |
|---|---|
| **Samples** | 200 observations |
| **Features** | 343 total (14 base features, time-invariant & time-varying) |
| **Target Variable** | `dual` — dual objective value (operational cost lower bound) |
| **Source** | RWTH Aachen Machine Learning Course |

**Feature categories:**
- Energy production: photovoltaic systems, wind turbines, grid
- Energy consumption: LEDs, air conditioning, heaters
- Economic factors: energy sourcing costs, surplus energy prices
- Environmental: outside air temperature

---

## 🧠 Methodology

```
JSON Data Loading → EDA & Cleaning → Feature Selection → Model Training → Evaluation
```

**Key steps:**
1. **EDA** — Constant feature removal, dimensionality analysis (200×300 after cleaning)
2. **Forward Stepwise Feature Selection** — Greedy iterative approach minimizing RMSE
3. **Stability-Based K-Fold Selection** — Sensitivity analysis for optimal CV folds
4. **Model Comparison** — Linear, Ridge, and Lasso regression with nested K-Fold cross-validation
5. **Hyperparameter Tuning** — GridSearchCV for regularization strength

---

## 📈 Results

| Model | Performance |
|---|---|
| Baseline (Linear Regression) | Full feature set benchmark |
| Ridge Regression | Reduced overfitting via L2 regularization |
| **Lasso Regression** | **~20% reduction in prediction error** ✅ |

> Lasso regularization outperformed baseline by effectively reducing irrelevant features through L1 penalty.

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat-square&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat-square&logo=python&logoColor=white)

**Key libraries:** `sklearn`, `pandas`, `numpy`, `matplotlib`, `seaborn`, `statsmodels`

---

## 📁 Repository Structure

```
├── vertical_farming_cost_prediction.ipynb   # Main notebook
├── data_aggregated/                         # JSON source files (inst_0.json ... inst_199.json)
│   └── inst_*.json
└── README.md
```

> ⚠️ **Note:** Place the `data_aggregated/` folder in the same directory as the notebook before running.

---

## 🚀 How to Run

```bash
# 1. Clone the repository
git clone https://github.com/KhushhaliSharmaa/Vertical-Farming-Cost-Prediction.git

# 2. Install dependencies
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels

# 3. Place data_aggregated/ folder in the project directory

# 4. Open and run the notebook
jupyter notebook vertical_farming_cost_prediction.ipynb
```

---

## 👥 Group Members

| Name |
|---|
| Khushali Sharma |
| Pallavi Pradip Jadhav |
| Shradha Mallikarjun Patil |
| Mukhil Sarvesh Sivaprakash |
| Muhammad Tauhid Yusham |

*Machine Learning Course — RWTH Aachen University*

---

## 📄 License

This project was developed as part of an academic course at RWTH Aachen University. For educational purposes only.
