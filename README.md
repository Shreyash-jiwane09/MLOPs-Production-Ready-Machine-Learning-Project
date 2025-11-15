# US Visa Approval Prediction - MLOps Production Pipeline

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.68+-green.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-Latest-orange.svg)
![Docker](https://img.shields.io/badge/Docker-Enabled-blue.svg)
![AWS](https://img.shields.io/badge/AWS-S3-yellow.svg)
![MongoDB](https://img.shields.io/badge/MongoDB-Cloud-green.svg)
![MLOps](https://img.shields.io/badge/MLOps-Production%20Ready-red.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

A production-ready machine learning project that predicts US visa approval status using MLOps best practices, automated pipelines, and cloud deployment capabilities.

## 🎯 Project Overview

This end-to-end ML system predicts whether a US visa application will be approved or denied based on applicant and employer information. The project demonstrates industry-standard MLOps practices including modular architecture, automated training pipelines, model versioning, and deployment with FastAPI.

## 📊 Pipeline Architecture

The project follows a comprehensive MLOps pipeline with the following components:

### Data Ingestion Pipeline
![Data Ingestion](images/data-ingestion.png)

### Data Transformation Pipeline
![Data Transformation](images/data-transformation.png)

### Data Validation Pipeline
![Data Validation](images/data-validation.png)

### Model Training & Evaluation Pipeline
![Model Training](images/Model-Trainer.png)

### Model Pusher Pipeline
![Model Pusher](images/model-pusher.png)

### UI Screen
![UI Screen](images/ui-screen.png)

## 🚀 Key Features

- **Modular ML Pipeline**: Separate components for data ingestion, validation, transformation, training, and evaluation
- **Cloud Integration**: MongoDB for data storage and AWS S3 for model artifacts
- **Data Drift Monitoring**: Evidently AI integration for detecting data drift
- **Web Interface**: FastAPI-based REST API with interactive HTML forms
- **Automated Training**: End-to-end training pipeline with configurable parameters
- **Production Ready**: Docker support and scalable architecture

## 🛠️ Tech Stack

**Machine Learning**: scikit-learn, XGBoost, CatBoost, imbalanced-learn  
**Data Processing**: Pandas, NumPy, SciPy  
**Visualization**: Matplotlib, Seaborn, Plotly  
**MLOps**: Evidently AI, DVC-compatible structure  
**Backend**: FastAPI, Uvicorn  
**Database**: MongoDB  
**Cloud**: AWS S3, boto3  
**Deployment**: Docker, Python 3.x

## 📁 Project Structure

```
├── config/                     # Configuration files (model, schema)
├── us_visa/
│   ├── components/            # ML pipeline components
│   │   ├── data_ingestion.py
│   │   ├── data_validation.py
│   │   ├── data_transformation.py
│   │   ├── model_trainer.py
│   │   ├── model_evaluation.py
│   │   └── model_pusher.py
│   ├── entity/                # Data classes and estimators
│   ├── pipline/               # Training and prediction pipelines
│   ├── configuration/         # AWS and MongoDB connections
│   ├── cloud_storage/         # S3 integration
│   └── utils/                 # Utility functions
├── templates/                 # HTML templates
├── static/                    # CSS and static files
├── notebook/                  # Jupyter notebooks for EDA
├── app.py                     # FastAPI application
├── Dockerfile                 # Container configuration
└── requirements.txt           # Dependencies

```

## 🔧 Installation

1. Clone the repository
```bash
git clone https://github.com/Shreyash-jiwane09/MLOPs-Production-Ready-Machine-Learning-Project.git
cd MLOPs-Production-Ready-Machine-Learning-Project
```

2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies
```bash
pip install -r requirements.txt
```

4. Set up environment variables
Create a `.env` file with:
```
MONGODB_URL=<your-mongodb-connection-string>
AWS_ACCESS_KEY_ID=<your-aws-access-key>
AWS_SECRET_ACCESS_KEY=<your-aws-secret-key>
```

## 🎮 Usage

### Training the Model
```bash
# Through API
curl http://localhost:8000/train

# Or navigate to
http://localhost:8000/train
```

### Making Predictions
```bash
# Start the application
python app.py

# Access the web interface
http://localhost:8000
```

### Docker Deployment
```bash
docker build -t us-visa-prediction .
docker run -p 8000:8000 us-visa-prediction
```

## 📊 ML Pipeline Components

1. **Data Ingestion**: Fetches data from MongoDB and prepares datasets
2. **Data Validation**: Validates schema and data quality using Evidently
3. **Data Transformation**: Handles missing values, encoding, and feature engineering
4. **Model Training**: Trains multiple models (XGBoost, CatBoost) with hyperparameter tuning
5. **Model Evaluation**: Evaluates model performance and validates against thresholds
6. **Model Pusher**: Deploys approved models to S3 and production directory

## 🎯 Input Features

- Continent
- Education of Employee
- Job Experience
- Job Training Requirements
- Number of Employees
- Company Age
- Region of Employment
- Prevailing Wage
- Unit of Wage
- Full-time Position Status

## 📈 Model Performance

The project uses ensemble methods and handles class imbalance using SMOTE techniques. Model evaluation includes precision, recall, F1-score, and AUC metrics.

## 👨‍💻 Author

**Shreyash Jiwane**  
Email: shrey.jiwane09@gmail.com

## 📝 License

This project is open source and available for educational purposes.

---

*Built as part of MLOps learning and practical implementation of production-ready machine learning systems.*
