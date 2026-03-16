# Group B Temperature Predictive Model

This project features a predictive modeling pipeline for indoor environmental conditions based on the dataset created from the PRE 400 Level Class between 5th March 2026 to 11th Match 2026. The goal of this project is to accurately predict the interior temperature (`TEMP_CELCIUS`) using external weather profiles, physical location data, and occupancy metrics.


## Group Members

|S/N|Name|Mat NO.|
|---|---|---|
|1	|BASSEY FAVOUR	|ENG2102757|
|2	|EFEIZOMOR PRECIOUS	|ENG2102761|
|3	|ETIE CHUKWUDIMWAZU JOSEPH	|ENG1804735|
|4	|OGOINJA SAMUEL TAMARAEMI	|ENG2102798|
|5	|IKOGHO DAVID OMAFUME	|ENG2102774|
|6	|AWOWEDE AKPOBARO OGHENEOCHUKO	|ENG2102755|

## Physical Environment

The data was collected/modeled based on a specific classroom or environment with the following physical dimensions:
- **Width:** 7.07m
- **Length:** 11.54m
- **Height:** 2.45m

## Dataset

The `DATA SET - EMERALD_TEMP.csv` dataset logs various properties over a 7-day period, recording:
- **Time identifiers:** `DAY`, `TIME_OF DAY` (Morning, Afternoon, Evening), `EXACT_TIME(H:M)`
- **Environmental features:** `WEATHER` (Cloudy, Sunny, Clear, Rainy)
- **Spatial identifiers:** `GRID`, `CORNER`, `HEIGHT`
- **Occupancy & Ventilation:** `NO_OF_PERSONS`, `WINDOWS_OPEN`
- *Target Metrics:* `HUMIDITY` and `TEMP_CELCIUS`



## Modeling Pipeline (`Temperature_Model.ipynb`)

The Jupyter Notebook explores multiple machine learning methods to predict the internal continuous temperature based on the recorded conditions:

1. **Preprocessing**: 
   - Non-numeric strings (like `%`) are cleaned.
   - Categorical properties (Weather, Grids, etc.) are One-Hot Encoded.
   - Continuous time features are normalized to minute-of-the-day representations.
   
2. **Modeling**: 
   - **Random Forest Regressor:** Handles the non-linear relationship between categorical grid/weather features and continuous temperature outputs exceptionally well.
   - **Support Vector Regression:** Machine learning algorithm used to predict continuous numerical values rather than discrete classes, Used as an Alternative algorithm for comparison and testing.

3. **Evaluation**: Both models check target splits based on Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R-squared variance captured.

## Getting Started

1. Ensure the dataset (`DATA SET - EMERALD_TEMP.csv`) is present in the root directory.
2. Open and run `Temperature_Model.ipynb` linearly.
3. Review the output evaluation metrics and Actual vs Predicted Scatterplots at the end of the notebook.
