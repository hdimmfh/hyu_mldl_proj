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

## 🔄 Dataset Discussion

- 🙋🏻‍♀️ : The dataset should reflect temporal dynamics (time, weather, holidays).  
- 🙋🏻‍♂️ :  It’s possible to simulate streaming with static data, but it’s not fully aligned with the paper unless timestamps/sequences are present.  
- 🙋 : Should we switch the dataset or stick to the paper?  
- Team agrees to look for datasets; two options proposed:  
  - ✅ **Electricity Load Forecasting** (weather, school, holidays)  
  - ✅ **Daily Website Visitors** (ordered daily data, quantile-friendly)  

🔗 Final decision: Use **Electricity Load Forecasting** dataset (file: `dataset.csv`)

---

## 💬 Team Role Division

- **Kim Yujin + Lee ChaeHyun** → Presentation (PPT Design), Drafted the Prophet section of the slides with key concepts, results, and visual plots
- **Baptiste + Porteix** → Presentation script + oral delivery in English. Summarized and interpreted the assigned academic paper (streaming quantile regression)
- **Koo Myungsoo** → Code (Prophet, RQR), demo notebooks. Main developer in charge of implementation and code structuring 

---

## 💻 Code Summary

- ✅ `prophet_demo.ipynb`: Prophet model with daily/hourly/monthly resampling, autoregression terms  
- ✅ `renewable_quantile_regression_streaming_demo.ipynb`: RQR streaming prediction, live MAPE tracking  

Each method outputs RMSE, MAE, and (for RQR) a list of MAPE values updated per batch.

---

## 🧩 Feedback & Presentation Notes

- 📌 **Slide 14 (Quantile > 0.5)**:  
  This slide is relevant only if the model includes upper quantile predictions (e.g., 0.9), which are useful for anticipating rare events such as power outages.

- 📌 **Final Slide – "Future Work"**:  
  Suggestions are welcome. Feel free to propose additions or revisions for completeness.

- 📌 **RQR Method Explanation**:  
  Please ensure the explanation in the slides clearly aligns with the logic and implementation of the RQR model presented in the code notebooks.

---

## 📎 Reference Materials

- ✅ [📄 Prophet Model - Official GitHub](https://github.com/facebook/prophet)  
- ✅ [📄 Prophet Paper (Taylor & Letham, 2017)](https://peerj.com/articles/3190/)  
- ✅ [📄 Renewable Quantile Regression Paper (Gourieroux et al., 2017)](https://hal.science/hal-01521057/document)  
- ✅ [📄 Dataset: Electricity Load Forecasting](https://www.kaggle.com/datasets/saurabhshahane/electricity-load-forecasting)

---

Please review and let the team know if anything is missing or needs clarification! 💬
