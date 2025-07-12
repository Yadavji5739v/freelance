# AI Campaign Predictor - Project Structure

## 📁 Complete Project Overview

```
ai-campaign-predictor/
├── 📄 README.md                    # Main project documentation
├── 📄 setup.py                     # Automated setup script
├── 📄 start.bat                    # Windows startup script
├── 📄 start.sh                     # Unix/Linux startup script
├── 📄 PROJECT_STRUCTURE.md         # This file
│
├── 🐍 backend/                     # Python Flask Backend
│   ├── 📄 app.py                   # Main Flask API server
│   ├── 📄 requirements.txt         # Python dependencies
│   │
│   └── 🤖 models/                 # Machine Learning Models
│       ├── 📄 data_generator.py   # Dataset generation (30+ features)
│       ├── 📄 ml_models.py        # ML models (Logistic, Random Forest, LSTM)
│       └── 📄 model_trainer.py    # Training pipeline
│
├── ⚛️ frontend/                    # React Frontend
│   ├── 📄 package.json            # Node.js dependencies
│   │
│   ├── 📁 public/                 # Static assets
│   │   └── 📄 index.html          # Main HTML template
│   │
│   └── 📁 src/                    # React source code
│       ├── 📄 index.js            # React entry point
│       ├── 📄 App.js              # Main app component
│       │
│       ├── 📁 components/         # Reusable components
│       │   └── 📄 Layout.js       # Main layout with sidebar
│       │
│       ├── 📁 pages/              # Page components
│       │   ├── 📄 Dashboard.js    # Overview dashboard
│       │   ├── 📄 Predictor.js    # Campaign prediction form
│       │   ├── 📄 Analytics.js    # Charts and analytics
│       │   └── 📄 Models.js       # Model management
│       │
│       └── 📁 utils/              # Utility functions
│           └── 📄 api.js          # API service functions
│
└── 📁 docs/                       # Documentation (created during setup)
    └── 📁 screenshots/            # Application screenshots
```

## 🔧 Technical Components

### Backend (Python Flask)

#### **Main API Server (`app.py`)**
- **Flask REST API** with CORS support
- **Endpoints:**
  - `GET /` - API information
  - `POST /api/predict` - Campaign predictions
  - `GET /api/models` - Model information
  - `GET /api/stats` - Performance statistics
  - `POST /api/retrain` - Model retraining
  - `GET /api/sample-campaign` - Sample data

#### **Machine Learning Models (`models/`)**

**Data Generator (`data_generator.py`)**
- Generates realistic campaign dataset with **30+ features**
- Features include: campaign type, platform, audience demographics, content metrics, timing, historical performance
- Creates 1000+ training records with realistic correlations

**ML Models (`ml_models.py`)**
- **Logistic Regression**: Binary classification for performance prediction
- **Random Forest**: Ensemble method with high accuracy (92% R²)
- **LSTM Neural Network**: Deep learning for sequence prediction
- Supports multiple target variables: engagement, bounce rate, CTR, success score

**Model Trainer (`model_trainer.py`)**
- Automated training pipeline
- Data preprocessing and feature engineering
- Model evaluation and performance metrics
- Model persistence (saves .pkl and .h5 files)

### Frontend (React + Material-UI)

#### **Main Components**

**Layout (`components/Layout.js`)**
- Responsive sidebar navigation
- Material-UI theme integration
- Mobile-friendly design

**Pages:**

**Dashboard (`pages/Dashboard.js`)**
- Overview cards with key metrics
- Performance charts
- Model status indicators
- Recent activity feed

**Campaign Predictor (`pages/Predictor.js`)**
- Interactive form for campaign parameters
- Real-time prediction display
- Multiple model selection
- Sample data loading

**Analytics (`pages/Analytics.js`)**
- Performance trend charts
- Platform distribution pie chart
- Campaign type comparison
- Model performance table

**Models (`pages/Models.js`)**
- Model overview cards
- Training status indicators
- Retraining functionality
- Detailed performance metrics

#### **API Integration (`utils/api.js`)**
- Axios-based HTTP client
- Request/response interceptors
- Error handling
- Centralized API endpoints

## 🎯 Features 

### **AI/ML Capabilities**
- **3 Different ML Models**: Logistic Regression, Random Forest, LSTM
- **4 Prediction Targets**: Engagement Rate, Bounce Rate, CTR, Success Score
- **30+ Features**: Comprehensive campaign parameters
- **Real-time Predictions**: Instant results via API
- **Model Retraining**: On-demand model updates

### **User Interface**
- **Modern Dashboard**: Material-UI with responsive design
- **Interactive Forms**: Campaign parameter input
- **Real-time Charts**: Performance visualization
- **Mobile Responsive**: Works on all devices
- **Professional Design**: Clean, modern interface

### **Technical Architecture**
- **RESTful API**: Flask backend with JSON responses
- **React Frontend**: Component-based architecture
- **State Management**: React Query for server state
- **Error Handling**: Comprehensive error management
- **CORS Support**: Cross-origin requests enabled

## 📊 Data & Models

### **Dataset Features (30+)**
- Campaign demographics (type, platform, format)
- Audience targeting (age, interests)
- Content metrics (length, media type)
- Timing features (launch time, seasonality)
- Platform-specific metrics
- Historical performance data
- Quality and creativity scores

### **Model Performance metrics to use**
- **Logistic Regression**: Accuracy score
- **Random Forest**: R² score
- **LSTM Neural Network**: R² score
- **Overall System**: Average accuracy

## 📊 Final Prediction Ranges

#### ✅ **Engagement Rate (0.1% – 25%)**
- Good : 0.1% – 2% → Low interaction; may need content or targeting improvement
- Better : 2% – 7% → Average engagement; audience is moderately responsive
- Best : 7% – 25% → High engagement; content is well-targeted and effective
-
#### 🔁 Bounce Rate (10% – 90%)
- Best : 10% – 30% → Highly engaging content; users are staying and interacting
- Better : 30% – 60% → Average bounce; acceptable for general campaigns
- Good : 60% – 90% → Poor retention; revisit content or audience targeting Note: Lower bounce rate is better.

####🖱️ Click-Through Rate (CTR) (0.1% – 15%)
- Good : 0.1% – 2% → Low conversion; possible issues with CTA or targeting
- Better : 2% – 5% → Decent interest; campaign is performing moderately well
- Best : 5% – 15% → High click activity; campaign is well-optimized

#### 🧠 Success Score (0 – 100)
- Good : 0 – 40 → Low predicted performance; needs improvements
- Better : 41 – 70 → Moderate success potential; acceptable performance
- Best : 71 – 100 → Strong performance; campaign likely to succeed 
