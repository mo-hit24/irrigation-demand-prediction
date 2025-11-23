# 🌾 AquaPulse

**Leveraging AI for Sustainable Irrigation Planning in Indian Agriculture**

> *Combining LSTM neural networks and TimeGPT foundation models to forecast water demand and enable data-informed irrigation planning across India's agricultural sector.*

### For more detailed insights and analysis, [Click Here](https://www.notion.so/portfolio-ms/AquaPulse-AI-Driven-Agricultural-Water-Demand-Forecasting-2977d94a2e9d80f595c4fa11b181ebde)

## 🎯 Quick Summary

| Challenge | Solution | Impact |
|-----------|----------|--------|
| 80% of India's freshwater used in agriculture with reactive planning | AI-driven water demand forecasting (LSTM + TimeGPT) | Enable proactive irrigation planning, reduce water waste, support 15+ states |
| Climate variability & monsoon uncertainty | Probabilistic forecasting with confidence intervals & drought scenarios | Support policy decisions 6-12 months ahead |
| Crop/region-specific demands not captured | Granular predictions by state, crop, and season | Identify high-risk zones (Rajasthan +65%, Pondicherry +67%) |


## 📊 At a Glance

```
Forecasting Horizon: 2024–2030
Crops Covered: Rice | Wheat | Sugarcane (77% of agri water demand)
Geographic Scope: 15+ Indian states
Historical Data: 50+ years (1970–2024)
AI Models: LSTM (local patterns) + TimeGPT (global trends)
Best Model Accuracy: 18.4% SMAPE (TimeGPT)
```

## 🚨 Problem Statement

### The Challenge

India's agriculture sector faces a **perfect storm** of challenges:

- **Climate Variability**: Unpredictable monsoons + rising groundwater depletion threaten irrigation reliability
- **Reactive Planning**: Decisions based on short-term rainfall data instead of forward-looking forecasts
- **Geographic Complexity**: Water needs vary dramatically across crops and regions. One-size-fits-all policies fail
- **Fragmented Stakeholders**: Farmers, planners, and policymakers have competing information needs

**The Result?** Crop failures, farmer distress, and unsustainable water extraction.

### Why this problem

```
Irrigation Stress → Crop Failure → Economic Loss & Food Insecurity
```

- Threatens farmer livelihoods across rural India
- Compromises food security
- Accelerates groundwater depletion
- Limits economic resilience in agricultural zones

## 🔬 Technical Implementation

### Data Integration Pipeline

We aggregated **50+ years of data** from authoritative sources:

| Data Source | Coverage | Purpose |
|---|---|---|
| **FAO AQUASTAT** | Global irrigation statistics | Crop water requirements (CWR) |
| **ICRISAT** | Rainfall, production trends | Climate & agricultural drivers |
| **Ministry of Agriculture** | State-wise crop area & yield | Regional demand estimation |

**Result**: Unified dataset covering 15+ states, 3 major crops, 50+ years.

### Feature Engineering

Key features engineered to capture agricultural and climate drivers:

```python
# Water Demand Calculation
Irrigation Fraction = Irrigated Area ÷ Total Crop Area
Crop Water Requirement (CWR):
  - Rice: 12,000 m³/ha
  - Wheat: 5,000 m³/ha
  - Sugarcane: 18,000 m³/ha
Water Demand = Crop Area × CWR

# Climate Risk
Drought Flag = 1 if (Rainfall < 75% of Normal), else 0
```

**Outcome**: Production-ready pipeline in Python (Pandas, NumPy) enabling scalability and reproducibility.

## 🤖 Model Architecture

### Dual-Model Strategy for Robustness

Instead of choosing one model, we **leveraged complementary strengths**:

#### LSTM (Long Short-Term Memory)

- **Purpose**: Capture fine-grained temporal dependencies and regional volatility
- **Strength**: Detects localized anomalies and state-specific patterns
- **Architecture**: Bidirectional LSTM + attention layers
- **Best for**: Identifying high-risk zones and drought impacts

#### TimeGPT (Foundation Model)

- **Purpose**: Global trend forecasting with built-in uncertainty quantification
- **Strength**: Few-shot learning; inherent credible intervals
- **Architecture**: Pre-trained transformer encoder-decoder
- **Best for**: National-level planning and probabilistic decision-making

## 📈 Model Performance

### Overall Accuracy

| Metric | LSTM | TimeGPT | Winner |
|---|---|---|---|
| **MAE** (10⁶ m³) | 5,192 | 1,015 | TimeGPT|
| **RMSE** (10⁶ m³) | 3,546 | 2,000 | TimeGPT|
| **SMAPE** (%) | 46.9% | 18.4% | TimeGPT|

### Per-Crop Analysis

```
RICE: MAE 3,170 | Moderate upward trend; monsoon-sensitive
WHEAT: MAE 986 | Stable baseline; highest drought sensitivity  
SUGARCANE: MAE 1,036 | SHARP RISE - sustainability concern
```

## 🚀 Future Roadmap

### Near-term (6–12 months)
- **Visual Dashboard**: Deploy real-time forecasts for irrigation planners and district officers
- **Satellite Integration**: Satellite-based evapotranspiration data for block-level granularity
- **Stakeholder Feedback**: Iterate with farmers and policymakers to refine predictions

### Long-term (1–2 years)
- **Multi-Horizon Forecasting**: Climate scenario modeling (RCP 4.5, 8.5) through 2050
- **Causal Inference**: Isolate policy intervention impacts (subsidies, crop switching)
- **Federated Learning**: Privacy-preserving collaboration across agricultural agencies
- **Advanced Architectures**: Attention-based models for climate-water co-forecasting

## 🛠️ Technical Stack

- **Languages**: Python 3.9+
- **Deep Learning**: TensorFlow/Keras (LSTM), Nixtla TimeGPT API
- **Data Processing**: Pandas, NumPy, Scikit-learn
- **Evaluation Metrics**: MAE, RMSE, SMAPE
- **Data Sources**: FAO AQUASTAT, ICRISAT, Ministry of Agriculture (India)
