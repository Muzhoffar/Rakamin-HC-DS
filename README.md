# 🏦 Home Credit Default Risk Prediction

> **ML Credit Scoring Model for Financial Inclusion**  
> Virtual Internship - Rakamin Academy x Home Credit Indonesia

---

## 🎯 Problem Statement

Home Credit melayani nasabah dengan riwayat kredit terbatas (thin-file). Tantangannya:
- **Baseline default rate: 8.07%** dari aplikasi pinjaman
- Sulitnya prediksi kemampuan bayar tanpa credit history
- Trade-off antara risk mitigation vs customer access

**Objective:** Bangun model ML untuk meminimalkan default risk sambil memaksimalkan approval rate.

---

## 📊 Solution & Results

### **Model Performance**
- **Algorithm:** LightGBM (winner dari 3 models tested)
- **AUC-ROC:** 0.7877
- **KS Statistic:** 0.4353
- **Cross-Validation:** 5-Fold Stratified (std < 0.01)

### **Business Impact**
| Metric | Baseline | With Model | Improvement |
|--------|----------|------------|-------------|
| **Default Rate** | 8.07% | 3.98% | **↓ 51%** |
| **Approval Rate** | ~50% | 75.9% | **↑ 52%** |
| **Annual Profit** | - | Rp 8,989M | **NEW** |

**Optimal Threshold:** 0.10 (predicted default probability)

---

## 💡 Key Insights

### **1. Income Segmentation Analysis**
- **Top 30% earners (Q8-Q10):** 6.1-7.0% default rate
- **Bottom 30% earners (Q1-Q3):** 8.4% default rate
- **Action:** Target marketing ke high-income segments untuk lower risk

### **2. Occupation Risk Profiling**
**Low Risk (Opportunity):**
- Accountants: 4.8% default (LOW market penetration!)
- IT Professionals: 6.5% default (VERY LOW penetration!)

**High Risk (Avoid):**
- Low-skill Laborers: 17.2% default
- Drivers: 11.3% default

**Action:** Fast-track approval untuk accountants & IT, enhanced verification untuk high-risk occupations

### **3. Feature Importance**
**Top Predictors:**
1. **EXT_SOURCE** (~35% importance) - External credit bureau scores
2. **Payment Behavior** - Late payment history
3. **Demographics** - Age, employment length
4. **Credit Ratios** - Credit/Income, Annuity/Credit

**Action:** Mandatory credit bureau check untuk semua aplikasi

---

## 🎯 Strategic Recommendations

### **1. Deploy Model**
Implementasi LightGBM dengan threshold 0.10
- **Expected:** Rp 8.9 Miliar annual profit
- **Risk reduction:** 51% (8.07% → 3.98%)

### **2. Targeted Acquisition**
Fokus marketing pada:
- High-income segments (Q8-Q10)
- Low-risk occupations (Accountants, IT professionals)

### **3. Risk-Based Pricing**
- **Low Risk:** 8-10% APR (attract & retain)
- **Medium Risk:** 12-15% APR
- **High Risk:** 15-25% APR or reject

### **4. Early Warning System**
Monitor EXT_SOURCE dan payment behavior sebagai sinyal peringatan dini

---

## 📁 Repository Contents

```
├── README.md                          # Project documentation
├── Home_Credit_Analysis.ipynb         # Full analysis (307K samples, 329 features)
├── Home_Credit_Presentation.pdf       # Business presentation (10 slides)
└── submission.csv                     # Submission file
```

---

## 📈 Dataset

**Source:** Home Credit Default Risk

**Data Structure:**
- Training: 307,511 applications
- Test: 48,744 applications
- Features: 329 (engineered from 121 original)
- Target: Binary (0 = No Default, 1 = Default)

**Relational Tables:**
- application_train/test
- bureau + bureau_balance
- previous_application
- POS_CASH_balance
- credit_card_balance
- installments_payments

---

## 📊 Model Comparison

| Model | AUC Score | Training Time | Notes |
|-------|-----------|---------------|-------|
| Logistic Regression | 0.6708 | Fast | Baseline |
| Random Forest | 0.7608 | Slow | Good performance |
| **LightGBM** | **0.7877** | Fast | **Best overall** ✅ |

**Why LightGBM?**
- Superior AUC score (+2.7% vs RF, +11.7% vs LR)
- Fast training on large dataset (307K rows)
- Excellent categorical feature handling
- Robust to missing values

---

## 👨‍💻 Author

**Rifqi Sirojul Muzhoffar**

📧 Email: rmuzhoffar@gmail.com
💼 LinkedIn: https://www.linkedin.com/in/rifqi-sm/ 
🔗 GitHub: https://github.com/Muzhoffar

---

## 🙏 Acknowledgments

- **Rakamin Academy** - Virtual Internship Program
- **Home Credit Indonesia** - Dataset & business context

---
