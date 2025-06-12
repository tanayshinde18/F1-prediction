
# 🏁 Canadian Grand Prix F1 Race Prediction

This repository contains a machine learning-based prediction model for the 2024 Formula 1 Canadian Grand Prix. Using the FastF1 API and data from recent races, the model predicts lap times based on sector-wise performance data.

## 📂 Project Structure

- **canadianGP.ipynb**: Main Jupyter notebook used for fetching data, preprocessing, training, and predicting lap times.
- **F1_cache_CanadianGP/**: Cache directory for FastF1 session data (generated automatically).

## 📌 Features

- Fetches historical F1 race session data using `FastF1`
- Extracts lap-wise and sector-wise performance data
- Preprocesses and cleans data
- Trains a **Gradient Boosting Regressor** for lap time prediction
- Evaluates model performance using **MAE**, **RMSE**, etc.

## 🚀 How to Run

1. Clone the repository:

```bash
git clone https://github.com/your-username/canadianGP-prediction.git
cd canadianGP-prediction
```

2. Install dependencies:

```bash
pip install fastf1 pandas numpy scikit-learn matplotlib
```

3. Run the notebook:

Open `canadianGP.ipynb` in Jupyter Notebook or VS Code and execute the cells step-by-step.

## 📊 Model & Data

- **Model**: `GradientBoostingRegressor`
- **Input Features**: Sector1Time, Sector2Time, Sector3Time
- **Target**: LapTime
- **Data Source**: `FastF1` API (2024 Race 9 – Canadian GP)

## 📁 Caching

All FastF1 data is cached to the `F1_cache_CanadianGP` folder for efficiency in repeated runs.

## 📈 Future Work

- Compare performance with other regressors like Random Forest or XGBoost
- Predict full race outcome or finishing positions
- Visualize lap time trends and driver consistency

## 🧠 Tech Stack

- Python
- FastF1
- Scikit-learn
- Pandas & NumPy
- Jupyter Notebook


## 🌦️ Weather Integration (Optional)

This project can be extended by incorporating real-time weather data using the [OpenWeather API](https://openweathermap.org/api). Weather conditions like temperature, humidity, and rain can significantly impact race performance.

### 🔑 Getting Your API Key

1. Visit [OpenWeather API](https://openweathermap.org/api).
2. Create a free account.
3. Navigate to the API keys section in your dashboard.
4. Copy your unique API key.

### 🔧 How to Use It in the Notebook

1. Find the section in the notebook where weather data is to be fetched or integrated (e.g., `# Weather API Integration`).
2. Replace the placeholder API key with your actual key like so:

```python
api_key = "YOUR_API_KEY_HERE"
```

3. Use the `requests` library or `pyowm` to fetch data from the API:

```python
import requests

city = "Montreal"
url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}"
weather_data = requests.get(url).json()
```

4. You can integrate fields like `weather_data['main']['temp']` into your feature set.

> Note: This step is optional but adds valuable real-world context to your model.

