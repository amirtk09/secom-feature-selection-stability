
<div align="center">

# 🔬 Feature Selection Stability Analysis on SECOM Dataset

**Notebook:** `CDM__5_Final.ipynb`  
**Dataset:** SECOM (UCI Machine Learning Repository)  
**Author:** AmirHossein Talebi Koohestani  
**University:** Amir Kabir University of Technology (Tehran Polytechnic)  
**Supervisor:** Dr. Mehdi Ghatee  
**TA:** Dr. Behnam Yousefimehr  

</div>

## 📖 Project Overview

This project presents a **comparative benchmark of feature selection techniques** for high-dimensional manufacturing data. The primary goal is to identify a subset of features that maximizes classification performance while maintaining **stability** against noise and minimizing **computational cost**.

The following approaches are evaluated:

1. **Filter Method:** Mutual Information  
2. **Wrapper Method:** Recursive Feature Elimination (RFE)  
3. **Decomposition Method:** Singular Value Decomposition (SVD) Scoring  

---

## 🚀 Installation & Setup

### Prerequisites

- Python 3.8+
- pip
- Jupyter Notebook

### Quick Start

```bash
git clone https://github.com/amirtk09/secom-feature-selection-stability.git
cd secom-feature-selection-stability
pip install numpy pandas scikit-learn matplotlib matplotlib-venn
jupyter notebook
```

Run the notebook `CDM__5_Final_.ipynb`.  
The dataset is downloaded automatically inside the notebook.

---

## 🧠 Techniques & Methodology

### 1. Data Preprocessing

- **Cleaning:** Removal of zero-variance columns (590 → 474 features)
- **Imputation:** Median imputation for missing values
- **Scaling:** Standardization using `StandardScaler`

### 2. Feature Selection Algorithms

| Method | Type | Description |
|------|------|------------|
| Mutual Information | Filter | Measures non-linear dependency between features and target |
| RFE (Random Forest) | Wrapper | Iteratively removes weakest features; high accuracy, high cost |
| SVD Scoring | Hybrid | Uses singular values and loadings to rank feature importance |

### 3. Stability Analysis

- Injected **5% random noise**
- Repeated selection **5 times**
- Measured robustness using **Jaccard overlap**

---

## 📊 Experimental Results

| Method | Accuracy | F1-Score | Selection Time | Stability (Avg / 20) |
|------|---------|----------|----------------|---------------------|
| Mutual Info | 0.59 | 0.70 | ~2.82 s | – |
| RFE | **0.78** | **0.83** | ~4.88 s | 12.6 |
| SVD | 0.72 | 0.79 | **~0.00 s** | **18.8** |

### Key Findings

- RFE achieves the highest predictive performance at significant computational cost.
- SVD provides an excellent speed–stability trade-off.
- Mutual Information underperforms in this high-dimensional setting.

---

## 📈 Visualizations

- PC1 vs PC2 loadings plot
- Feature overlap Venn diagrams
- Accuracy, F1-score, and runtime comparisons
