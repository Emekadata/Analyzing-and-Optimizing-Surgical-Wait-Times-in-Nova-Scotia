# Analyzing-and-Optimizing-Surgical-Wait-Times-in-Nova-Scotia

## 🧠 Overview
This project applies advanced time series modeling to analyze and predict surgical wait times in Nova Scotia. By leveraging historical government health data, we identify trends, highlight inefficiencies across facilities, and generate forecasts for six high-priority procedures. The goal is to inform better healthcare planning and reduce patient wait times using data-driven strategies.

---

## 📁 Project Structure
- **Data Source**: Nova Scotia Open Data Portal  
- **Models Used**:  
  - Simple Exponential Smoothing (SES)  
  - Holt’s Linear Trend  
  - Facebook Prophet  
  - Hybrid (Best MAE Selection)  
- **Forecast Horizon**: Next 4 quarters  
- **Key Metrics**: Mean Absolute Error (MAE)

---

## 📌 Objectives
- Clean and preprocess wait time data across hospitals and procedures.
- Identify outliers, bottlenecks, and regional disparities.
- Forecast median wait times for surgeries like:
  - Cystoscopy
  - Hernia Repair (Adult & Inguinal/Femoral)
  - Gallbladder Surgery
  - Hysterectomy (Cancer not suspected)
  - Gastrointestinal Tract Surgery

---

## 🔧 Tools & Technologies
- **Language**: Python
- **Libraries**:
  - `pandas`, `numpy` — Data manipulation
  - `matplotlib`, `seaborn` — Visualization
  - `scikit-learn` — Evaluation
  - `statsmodels` — SES/Holt modeling
  - `prophet` — Facebook Prophet forecasts

---

## 📈 Methodology

### Data Cleaning
- Mapped missing `Specialty` from `Procedure`
- Imputed median values for missing wait times
- Standardized inconsistent period formats (e.g., `q1_2022` → `2022_Q1`)

### EDA Insights
- Visualizations showed disparities in wait times across facilities.
- Cape Breton and Valley Regional showed longest delays.
- South Shore Regional consistently demonstrated high efficiency.

### Forecasting Models
- **SES/Holt**: Used based on stationarity (ADF Test)
- **Prophet**: Used for non-linear/seasonal data
- **Hybrid**: Chose model with lowest MAE per procedure

---

## 🏆 Key Results

| Procedure                          | Best Model | MAE     |
|-----------------------------------|------------|---------|
| Cystoscopy                        | Prophet    | 3.46    |
| Gallbladder Surgery               | Prophet    | 18.50   |
| Hysterectomy (Cancer not suspected) | Prophet | 9.57    |
| Hernia Repair (Adult)            | SES/Holt   | 11.97   |
| Hernia Repair - Inguinal/Femoral | SES/Holt   | 15.02   |
| GI Tract Surgery                 | Prophet    | 8.58    |

---

## 📚 References
- Government of Nova Scotia: [https://waittimes.novascotia.ca](https://waittimes.novascotia.ca)  
- Fraser Institute Reports  
- ARIMA-Hybrid Modeling Literature  
- Carandang et al. (2018) Surgical Wait Time Studies

---

## ✅ Future Enhancements
- Integrate external variables (e.g., staffing levels, hospital policies)
- Explore deep learning models for high-volume procedures
- Create a dashboard for real-time policy use

---

## 👨‍⚕️ Author
**Chukwuemeka Onyeukwu**  
Data Science & Healthcare Analytics Enthusiast  
