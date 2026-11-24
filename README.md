# Crop Recommendation from Sensor Data 🌱📡

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/deyem1/crop-recommendation-ml/blob/main/iot_agicultural_Machine_Learning.ipynb)

Recommends the best crop to plant from the kinds of readings a field IoT sensor node would collect: soil nitrogen (N), phosphorus (P), potassium (K), temperature, humidity, pH and rainfall.

The idea is a smart-farming pipeline. Sensors in the field stream readings, and the model tells the farmer which of 22 crops suits that soil and climate.

## Pipeline

1. **EDA:** mean N/P/K needs per crop, distributions, correlation heatmap. P and K turn out to be strongly correlated.
2. **Preprocessing:** label encoding of the 22 crop classes, 80/20 train/test split.
3. **Model:** XGBoost classifier.
4. **Evaluation:** classification report and confusion matrix.

## Results

XGBoost reaches **~99–100 % accuracy** on the held-out test set.

> ⚠️ This Kaggle dataset is clean and well separated, so near-perfect scores are expected. Real field data would be noisier. The next step is to test on readings from an actual sensor node.

## Data

[Crop Recommendation Dataset](https://www.kaggle.com/datasets/78c7595cbf5a98a8cc488e5b9f6911f216680e5a221e6704ba7be4d7ef42c753) (Kaggle): 2,200 rows, 7 features, 22 crops.

## Run it

Click the Colab badge above, upload `Crop_recommendation.csv`, and run all cells.

## Tech

Python · pandas · seaborn · scikit-learn · XGBoost

## Next steps

- Wire this to a live sensor node (ESP32 + NPK, DHT22 and pH sensors) through ThingsBoard
- Serve the model as a small API and dashboard
