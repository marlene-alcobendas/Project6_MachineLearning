
# 📦 Optimal Service Level Selection for Aircraft Parts Shipments
### Master's in Data Analytics - Machine Learning Project


## 📌 Project Overview
This project aims to optimize **logistics service level selection (Normal / Urgent / Critical)** by leveraging historical shipment data and Machine Learning models.

The objective is **to recommend the most cost-efficient service level that still meets the real delivery leadtime**, avoiding unnecessary premium services while maintaining operational performance.

This project has been developed as part of a **Data Analyst Master program**, with a strong focus on **real business applicability in supply chain and transportation operations**.

---

## 🎯 Business Problem
In logistics operations, shipments are often booked with higher-cost service levels (e.g. Critical) than actually required.

This leads to:
- Unnecessary transportation costs
- Inefficient service level usage
- Limited data-driven decision making

**Key question:**  
> Based on historical delivery performance, which service level should be chosen to meet the required delivery leadtime at the lowest possible cost?

---

## 🧠 Solution Approach
The project follows a **classification-based Machine Learning approach**:

1. **Historical leadtime analysis**
2. **Target engineering** to define the optimal service level
3. **Feature engineering** using shipment, route and temporal variables
4. **Model training and evaluation**
5. **Service level recommendation**

---

## 🗂 Dataset Description
The dataset contains historical shipment records including:

### Key Features
- Shipment characteristics:
  - `Pcs`, `Gwgt`, `Cwgt`
- Route information:
  - Origin and destination airports
  - Zones and countries
- Time features:
  - `month`, `day_of_week`, `hour`
- Operational flags:
  - `DGR` (Dangerous Goods)
- Current service level information

### Target Variable
- **`sla_recommended`**  
  The optimal service level (`Normal`, `Urgent`, `Critical`) based on real delivery leadtime vs SLA thresholds.

---

## ⚙️ Methodology

### 1️⃣ Data Preparation
- Cleaning inconsistent timestamps
- Calculating **real leadtime in hours**
- Removing data leakage features
- Encoding categorical variables
- Scaling numerical variables using pipelines

### 2️⃣ Target Engineering
- Service level is **downgraded only when historical performance proves it was unnecessary**
- If the shipment met the SLA → no change
- If a cheaper SLA would still have met the delivery leadtime → downgrade
- If even the cheapest SLA would not have met the delivery leadtime → operational issue, not cost optimization

### 3️⃣ Models Evaluated
- Baseline model
- Logistic Regression
- Random Forest
- Gradient Boosting (final selected model)

### 4️⃣ Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-score (macro and weighted)
- Confusion Matrix

---

## 🏆 Model Selection
**Gradient Boosting** was selected as the final model due to:
- Better balance between precision and recall across all classes
- Strong performance on minority classes
- Higher macro-averaged metrics, ensuring fairness between service levels

---

## 📊 Results
- Significant reduction in over-usage of premium service levels
- Improved alignment between **real delivery leadtime** and **service level cost**
- Model predictions are interpretable and business-ready


---

## 🚀 Next Steps
- Integrate cost data to quantify savings (€)
- Add SHAP analysis for model explainability
- Deploy as a decision-support tool
- Extend model to real-time service level recommendation

---

## 🛠 Technologies Used
- Python
- Pandas & NumPy
- Scikit-learn
- Matplotlib
- Jupyter Notebook

---

## 👤 Authors
**Marlene Alcobendas**  
Data Analyst | Supply Chain & Logistics Analytics

**Iván Prieto**  
Data Analyst | Procurement Analyst

