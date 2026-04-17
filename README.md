# 🚦 TrafficGNN Pro — Smart City Traffic Intelligence

A full-stack, real-time **Traffic Flow Prediction** system using **Graph Neural Networks (GNN)**, built with Streamlit.

---

## 📦 Project Structure

```
traffic_gnn_app/
├── app.py              ← Main Streamlit application
├── requirements.txt    ← Python dependencies
└── README.md           ← This file
```

---

## 🚀 Deploy on Streamlit Cloud (Free)

### Step 1 — Push to GitHub
```bash
git init
git add .
git commit -m "TrafficGNN Pro — initial commit"
git remote add origin https://github.com/YOUR_USERNAME/traffic-gnn-pro.git
git push -u origin main
```

### Step 2 — Deploy on Streamlit Cloud
1. Go to **https://streamlit.io/cloud**
2. Click **"New app"**
3. Connect your GitHub repo
4. Set **Main file path** → `app.py`
5. Click **Deploy** 🎉

---

## 🧠 GNN Architecture

```
Input: [Flow, Speed, Occupancy] × N_nodes × T_steps
         ↓
Graph Convolutional Layers (2×)
  H^(l+1) = σ(D̃^(-½) Ã D̃^(-½) H^(l) Θ^(l))
         ↓
GRU Temporal Encoder
  h_t = GRU(H_spatial_t, h_{t-1})
         ↓
Multi-Step Decoder
  ŷ_{t+1:t+k} = FC(h_T)
         ↓
Output: Predicted Flow & Speed (k steps ahead)
```

---

## 📊 Features

### 🏠 Live Dashboard
- Real-time KPI metrics (flow, speed, congestion)
- Active alert feed with severity levels
- 24h congestion distribution chart
- Live sensor status ticker

### 🕸️ Graph Network
- Interactive road network visualization
- Node = sensor, Edge = road, Color = congestion
- Graph statistics (degree, density, diameter)
- Traffic flow heatmap (24h × sensors)

### 📊 GNN Prediction
- Sensor-level flow forecasting (5-min steps)
- Confidence interval visualization
- Speed gauge (real-time)
- Model performance metrics (MAE, RMSE, MAPE, R²)

### 🏙️ Smart City Applications
1. **Dynamic Route Recommendation** — AI optimal routing
2. **Congestion Early Warning** — Predict & alert 15–30 min ahead
3. **Smart Parking Prediction** — Zone-level availability
4. **Logistics Optimization** — Delivery window scheduling
5. **Road Maintenance Planning** — Low-impact maintenance windows
6. **Adaptive Toll Pricing** — Dynamic demand-based pricing

### 📈 Analytics
- Origin-Destination matrix
- Sensor correlation heatmap
- Speed-flow fundamental diagram

### 📥 Download Center
- Current traffic state (CSV)
- Full 24h data (CSV)
- Graph edge list (CSV)
- GNN predictions (CSV)
- Graph structure (JSON)
- Model config (JSON)
- Complete ZIP package

---

## 🔧 Local Development

```bash
pip install -r requirements.txt
streamlit run app.py
```

---

## 📐 GNN Formulas

| Formula | Description |
|---------|-------------|
| `G = (V, E, W)` | Graph with nodes V, edges E, weights W |
| `H^(l+1) = σ(D̃^(-½) Ã D̃^(-½) H^(l) Θ^(l))` | Graph Conv Layer |
| `ŷ_{t+k} = GRU(H_s, H_t)` | ST-GNN output |
| `L = MAE + λ·MSE` | Training loss |

---

## 🛠️ Tech Stack

- **Frontend**: Streamlit + Plotly
- **Graph Library**: NetworkX
- **Data**: NumPy + Pandas
- **Simulation**: Spatio-Temporal GNN simulation
- **Deployment**: Streamlit Cloud (free tier)

---

*TrafficGNN Pro — Built for Smart Cities*
