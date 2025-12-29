# SmartGrid Energy Prediction with LSTM

## Project Overview
This project predicts **hourly electricity consumption** for EcoVolt’s Smart Grid using a Deep Learning LSTM model. The goal is to anticipate peak loads and prevent network overloads.

## Dataset
- `data.csv` contains hourly consumption and production data from various energy sources:
  - `DateTime`: Timestamp
  - `Consumption`: Total electricity consumption (MW)
  - Production sources: `Nuclear`, `Solar`, `Wind`, `Hydroelectric`, `Coal`, `Oil and Gas`, `Biomass`

## Steps Performed in Notebook
1. **Data Preparation**
   - Convert `DateTime` to datetime type
   - Sort by time and set as index
   - Normalize data with `MinMaxScaler`

2. **Sequence Creation**
   - Create sequences of 24 hours for LSTM input
   - Shape of input: `(samples, timesteps=24, features)`

3. **Train/Test Split**
   - 80% training, 20% testing (time order preserved)

4. **Model Architecture**
   - LSTM (64 units) → Dropout (0.2) → Dense (1)
   - Optimizer: Adam, Loss: MSE

5. **Training & Evaluation**
   - 30 epochs, monitored loss/val_loss
   - Plots: predicted vs actual consumption
   - Model saved as `LstmSmartGrid.keras`

## Usage
- Open the notebook in Google Colab
- Run all cells to reproduce preprocessing, training, and evaluation
- Plots and model saved inside the notebook outputs

## Notes
- SQL analysis (SELECT, WHERE, GROUP BY, aggregation, temporal functions) is part of evaluation but not implemented in this notebook
