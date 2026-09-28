# Bike Sharing Demand - Regression

Predicts hourly bike rentals (`count`) from weather and calendar data using the Kaggle Bike Sharing Demand dataset (10,886 hourly records, 2011-2012).

## What I did
- Checked data quality (no missing values or duplicates) and explored demand by hour, season and weather
- Engineered time features from `datetime` (year, month, hour, day of week)
- Used a time-based 80/20 split so the model is validated on future data
- Compared 4 models: Linear Regression, Random Forest, Gradient Boosting, Random Forest with log target
- Saved the final Random Forest and built a small widget to predict demand

## Results
| Model | MAE | RMSE | R2 | RMSLE |
|---|---|---|---|---|
| Linear Regression | 141.39 | 184.04 | 0.285 | 1.241 |
| Random Forest | 46.14 | 72.11 | 0.890 | 0.342 |
| Gradient Boosting | 46.62 | 70.88 | 0.894 | 0.419 |
| Random Forest + Log Target | 54.82 | 86.33 | 0.843 | 0.375 |

Random Forest was chosen: best MAE and RMSLE. `hour` was the most important feature (~59%).

## Run it
1. Download the dataset from Kaggle (Bike Sharing Demand) and put `train.csv` where the notebook expects it
2. `pip install -r requirements.txt`
3. Open `notebooks/regression.ipynb`

## Structure
- `notebooks/` - main notebook
- `results/` - plots
- `models/` - saved model (link below if hosted externally)
