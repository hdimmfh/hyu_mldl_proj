# ⭐️ hyu_mldl_proj
Comparative time series forecasting using Facebook Prophet and Renewable Quantile Regression (RQR) on electricity demand data with streaming updates and anomaly detection.

---

# 📌 Project Overview: Time Series Forecasting with Prophet and RQR

This notebook summarizes the direction, rationale, and team conversation history behind the project.  
It is intended for sharing in our KakaoTalk group as a compact reference.

---

## 🧭 Project Goal

Compare the performance of two forecasting approaches:
- **Prophet** (batch learning, rolling forecast)
- **Renewable Quantile Regression (RQR)** (streaming learning using summary statistics)

Based on: Electricity load forecasting dataset with time-dependent external factors (weather, calendar, etc.)

---

## 📈 Project Direction

1. **Prophet**: Evaluate performance on hourly, daily, monthly resolutions using resampling
2. **RQR**: Simulate streaming updates + quantile prediction (e.g., 0.5, 0.9)
3. **Quantitative Evaluation**: RMSE, MAE, MAPE for both models on aligned time intervals
4. **(Optional)**: Outlier detection using Prophet (via residuals or prediction intervals)

---

## 🔄 Dataset Discussion (KakaoTalk History Summary)

- ChaeHyun: The dataset should reflect temporal dynamics (time, weather, holidays).
- GPT: It’s possible to simulate streaming with static data, but it’s not fully aligned with the paper unless timestamps/sequences are present.
- Yujin: Should we switch the dataset or stick to the paper?
- Team agrees to look for datasets; two options proposed:
  - ✅ **Electricity Load Forecasting** (weather, school, holidays)
  - ✅ **Daily Website Visitors** (ordered daily data, quantile-friendly)

🔗 Final decision: Use **Electricity Load Forecasting** dataset (file: `continuous dataset.csv`)

---

## 💬 Team Role Division

- **Kim Yujin + ChaeHyun** → Presentation (PPT Design)
- **Foreign students** → Presentation script + oral delivery in English
- **Koo Myungsoo** → Code (Prophet, RQR), demo notebooks

---

## 💻 Code Summary

- ✅ `prophet_demo.ipynb`: Prophet model with daily/hourly/monthly resampling, autoregression terms
- ✅ `renewable_quantile_regression_streaming_demo.ipynb`: RQR streaming prediction, live MAPE tracking
- ✅ `MLDL.zip`: Bundled code files for presentation

Each method outputs RMSE, MAE, and (for RQR) a list of MAPE values updated per batch.

---

## 🧩 Feedback & Presentation Notes

- PPT page 14 (quantile > 0.5) should only be included if predicting upper quantiles (e.g., 0.9) for use cases like power outage planning
- Final slide ("Future Work") → feedback welcomed
- Ensure RQR explanation is aligned with `.docx` explanation provided

---

## 📌 Files Shared

- ✅ [Electricity Load Forecasting Draft.pdf]
- ✅ [explanation for RQR.docx]
- ✅ [Canva Slide Deck](https://www.canva.com/design/DAGqDJa4HMU/iYCOfvQaLwet0gGfNfjOjw/edit?utm_content=DAGqDJa4HMU)
- ✅ [Prophet & RQR Notebooks]
- ✅ [Final consolidated ZIP]

---

Please review and let the team know if anything is missing or needs clarification! 💬
