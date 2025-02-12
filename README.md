# NYISO-Electricity-Consumption-and-Pricing-Insights
# NYISO Electricity Analysis Project

## Overview
This project analyzes New York Independent System Operator (NYISO) electricity market data to develop predictive models for price forecasting, anomaly detection, and load demand prediction. Using advanced time series analysis and machine learning techniques, the project demonstrates capabilities in processing and analyzing large-scale energy market data.

## Technologies Used
- **PySpark**: 
  - Data processing and analysis
  - Structured Streaming for real-time data processing
- **Machine Learning Libraries**:
  - MLlib: Distributed machine learning with Spark
  - scikit-learn: Additional ML algorithms and tools
- **Python**: Primary programming language
  - Matplotlib: Data visualization
- **Google Colab**: Development environment

## Data Source
- NYISO Electricity Market Dataset (2001-2023)
- Key components:
  - Pricing Data: Locational-based marginal prices (LBMP)
  - Load Data: Real-time and forecasted electricity demand
  - Features include:
    - PTID (Pricing Node ID)
    - Integrated Load
    - LBMP (Locational Based Marginal Price)
    - Marginal Cost of Losses
    - Marginal Cost of Congestion

## Key Features

### 1. Price Prediction Model
- Prediction of electricity prices (LBMP) based on historical load patterns
- Feature engineering for improved accuracy
- Model performance metrics and validation
- Real-time prediction capabilities using structured streaming

### 2. Price Spike Detection
- Anomaly detection in electricity prices
- Analysis of sudden changes due to:
  - Demand fluctuations
  - Grid congestion
  - Transmission losses
- Real-time monitoring and alerting system

### 3. Load Demand Forecasting
- Predictive modeling of electricity demand
- Integration of multiple features:
  - Historical prices
  - Grid conditions
  - Congestion costs
  - Loss metrics
- Streaming-based prediction system

## Technical Implementation

### Data Processing Pipeline
```python
# Example streaming configuration
spark.readStream \
    .format("csv") \
    .option("header", "true") \
    .load("path_to_data") \
    .filter("month IN ('03', '06', '09', '12')")
```

### Model Development Process
1. Data preprocessing and cleaning
2. Feature engineering and selection
3. Model training and validation
4. Performance optimization
5. Streaming implementation
6. Real-time prediction

## Results and Performance Metrics

### Price Prediction Model
- Mean Absolute Error (MAE)
- Root Mean Square Error (RMSE)
- R-squared value

### Anomaly Detection
- Precision
- Recall
- F1 Score

### Load Forecasting
- Forecast Accuracy
- Mean Absolute Percentage Error (MAPE)
- Prediction Intervals

## Validation Strategy
- Training data: All months except Mar, Jun, Sep, Dec
- Testing data: Mar, Jun, Sep, Dec (via streaming)
- Cross-validation techniques
- Performance monitoring and model updating

## Setup Instructions

1. Clone the repository
2. Configure Google Colab environment
3. Mount Google Drive
4. Install required dependencies
5. Load data and run analysis notebooks

## Usage

```python
# Example usage of streaming prediction
from pyspark.ml import PipelineModel
from pyspark.sql.functions import *

# Load trained model
model = PipelineModel.load("path_to_model")

# Setup streaming prediction
prediction_stream = model.transform(input_stream)
```

## Dependencies
- PySpark
- scikit-learn
- Python 3.x
- Required Python packages listed in requirements.txt

## Project Structure
```
├── notebooks/
│   ├── data_preprocessing.ipynb
│   ├── price_prediction.ipynb
│   ├── anomaly_detection.ipynb
│   └── load_forecasting.ipynb
├── models/
│   ├── price_predictor.model
│   ├── anomaly_detector.model
│   └── load_forecaster.model
├── data/
│   ├── raw/
│   └── processed/
└── README.md
```

## Future Enhancements
- Integration with real-time NYISO data feeds
- Advanced feature engineering
- Deep learning models for improved accuracy
- Enhanced visualization dashboard
- Multi-node deployment capability



## Acknowledgments
- Project completed as part of the Introduction to Big Data and Analytics course at George Washington University
- NYISO for providing the electricity market dataset
- Apache Spark community for the analytics framework
