# 🌦️ Weather Prediction Model (India 2000–2024)

This project uses **machine learning models** to predict **next-day weather conditions** for Indian cities.  
It performs both **regression** (temperature, wind, rain) and **classification** (weather condition codes).  

---

## 📌 Features
- **Multi-output regression** with Ridge:
  - Next-day maximum temperature  
  - Next-day wind speed  
  - Next-day rain sum  

- **Classification** with Logistic Regression:
  - Predicts **next-day weather condition** (e.g., clear sky, rain, thunderstorm)  

- **Data preprocessing**:
  - Date handling, sorting, missing value removal  
  - Weather code encoding  
  - Train/test splitting  

- **Evaluation metrics**:
  - Regression: **R² per target**  
  - Classification: **Accuracy, Confusion Matrix, Classification Report**  

- **Custom input prediction** for new weather samples  

---

## 📂 Dataset
- File: `DATA_CSV/india_2000_2024_daily_weather.csv`  
- Time span: **2000–2024**  
- Features:
  - Temperature (max, min, apparent)  
  - Precipitation & rain sum  
  - Weather code (numeric categories)  
  - Wind speed, gusts, direction  

### Weather Code Mapping
| Code | Description |
|------|-------------|
| 0    | Clear sky |
| 1    | Mainly clear |
| 2    | Partly cloudy |
| 3    | Overcast |
| 45   | Fog |
| 61   | Rain: slight |
| 63   | Rain: moderate |
| 65   | Rain: heavy |
| 95   | Thunderstorm |
| 99   | Thunderstorm with heavy hail |
*(See code for full mapping.)*  

---

## ⚙️ Installation
Clone this repository and install dependencies:  

```bash
git clone https://github.com/yourusername/weather-prediction.git
cd weather-prediction
pip install -r requirements.txt
```

## Requirements

- Python 3.8+

- numpy, pandas

- scikit-learn

. Install via:
```
pip install numpy pandas scikit-learn
```

## 🚀 Usage
  1. Run the script
    python weather_prediction.py
  2. Example Prediction
```bash
new_data = pd.DataFrame([{
    'temperature_2m_max': 33,
    'temperature_2m_min': 26,
    'apparent_temperature_max': 35,
    'apparent_temperature_min': 27,
    'precipitation_sum': 0,
    'rain_sum': 0,
    'weather_code': 10, 
    'wind_speed_10m_max': 10,
    'wind_gusts_10m_max': 15,
    'wind_direction_10m_dominant': 180
}])
```

## Regression prediction
pred_reg = multi_reg.predict(new_data)[0]
print("Next-day max temp:", pred_reg[0])
print("Next-day wind speed:", pred_reg[1])
print("Next-day rain sum:", pred_reg[2])

## Classification prediction
pred_cls = clf.predict(new_data)[0]
desc = weather_code_map.get(pred_cls, f"Unknown code {pred_cls}")
print("Next-day weather code:", pred_cls, "-", desc)


## 🔮 Future Improvements

Add Random Forest / Gradient Boosting / Neural Networks

Hyperparameter tuning with GridSearchCV

Visualization of predictions (temp vs actual, confusion matrix heatmap)

Deploy as a Streamlit app or Flask API

Connect to a live weather API for real-time forecasts

## 👨‍💻 Author

Abhishek Kumar
MCA (AI/ML) | ML & Data Science Enthusiast
