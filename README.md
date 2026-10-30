# StockSense – AI Inventory Intelligence Platform

StockSense is a comprehensive full-stack decision-support system for retail inventory management. It uses Machine Learning models to forecast demand and predict stock-out risks to optimize inventory replenishment.

## Features
- **Executive Dashboard:** Overall KPI and alerts view.
- **Demand Intelligence:** AI-powered 7-day demand forecasting.
- **Inventory Risk:** Predict stock-out probability and classify risks (HIGH/MEDIUM/LOW).
- **Manager Action Center:** Actionable recommendations based on the ML pipeline.
- **ML Pipeline Visualization:** Interactive React Flow diagram showing data and model workflows.
- **Model Performance:** Metrics and feature importance for both demand and stockout models.

## Tech Stack
- **Frontend:** React.js, Vite, Recharts, React Flow, Lucide Icons, pure CSS.
- **Backend:** Python Flask, Flask-CORS, Pandas, scikit-learn, joblib.

## Project Structure
```text
StockSense/
│
├── backend/
│   ├── app.py                      # Flask API main entry
│   ├── requirements.txt            # Python dependencies
│   ├── models/                     # Place your Joblib models here (.pkl)
│   │   ├── demand_forecasting_model.pkl (Required)
│   │   └── stockout_risk_model.pkl      (Required)
│   └── services/
│       ├── prediction_service.py   # Loads models and runs inferences
│       └── recommendation_service.py # Core business logic engine
│
└── frontend/                       # React frontend application
    ├── package.json
    ├── src/
    │   ├── api.js                  # Axios setup and API calls
    │   ├── App.jsx                 # Router and Main Layout
    │   ├── index.css               # Styling
    │   └── pages/                  # Dashboard, MLPipeline, etc.
```

## Setup Instructions

### 1. Backend Setup
You must have Python installed.

1. Navigate to the backend directory:
   ```bash
   cd StockSense/backend
   ```
2. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Add your Trained Models:
   Place your existing `.pkl` files inside `backend/models/`:
   - `demand_forecasting_model.pkl`
   - `stockout_risk_model.pkl`

4. Run the Flask Server:
   ```bash
   python app.py
   ```
   *The backend will run at http://localhost:5000*

### 2. Frontend Setup
You must have Node.js and npm installed.

1. Navigate to the frontend directory:
   ```bash
   cd StockSense/frontend
   ```
2. Install Node dependencies:
   ```bash
   npm install
   ```
3. Start the Vite development server:
   ```bash
   npm run dev
   ```
   *The frontend will typically run at http://localhost:5173*

## Note on Machine Learning Models
This platform uses your pre-trained `joblib` models. The input features from the UI are sent exactly as captured to the backend. Ensure that the features passed via `app.py` match the feature dimensions expected by your models. 
If models are missing, the prediction endpoints will output dummy logical approximations so the UI can still be tested and previewed.

## Author
Built for the Data Science Hackathon.
