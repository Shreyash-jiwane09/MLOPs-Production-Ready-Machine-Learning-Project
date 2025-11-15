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

- **CI/CD Pipeline**: Automated deployment using GitHub Actions with self-hosted EC2 runner
- **Cloud Deployment**: Complete AWS integration (EC2, ECR, S3) for production-ready deployment
- **Modular ML Pipeline**: Separate components for data ingestion, validation, transformation, training, and evaluation
- **Data Drift Monitoring**: Evidently AI integration for detecting data drift and model degradation
- **Containerized Application**: Docker-based deployment with automated image building and registry management
- **Cloud Integration**: MongoDB Atlas for data storage and AWS S3 for model artifacts versioning
- **Web Interface**: FastAPI-based REST API with interactive HTML forms
- **Automated Training**: End-to-end training pipeline with configurable parameters

## 🛠️ Tech Stack

**Machine Learning**: scikit-learn, XGBoost, CatBoost, imbalanced-learn  
**Data Processing**: Pandas, NumPy, SciPy  
**Visualization**: Matplotlib, Seaborn, Plotly  
**MLOps**: Evidently AI, DVC-compatible structure  
**Backend**: FastAPI, Uvicorn  
**Database**: MongoDB Atlas  
**Cloud & Infrastructure**: AWS (EC2, ECR, S3), boto3  
**CI/CD**: GitHub Actions with self-hosted EC2 runner  
**Containerization**: Docker, Docker Compose  
**Version Control**: Git, GitHub

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
# Build Docker image
docker build -t us-visa-prediction .

# Run container with environment variables
docker run -p 8080:8080 \
  -e AWS_ACCESS_KEY_ID=<your-access-key> \
  -e AWS_SECRET_ACCESS_KEY=<your-secret-key> \
  -e AWS_DEFAULT_REGION=<your-region> \
  -e MONGODB_URL=<your-mongodb-url> \
  us-visa-prediction
```

## 🔄 CI/CD Pipeline

This project implements a complete CI/CD pipeline using **GitHub Actions** with a **self-hosted runner on AWS EC2**.

### Pipeline Architecture

```
Git Push → GitHub Actions → Build Docker Image → Push to ECR → Deploy to EC2 → Production
```

### Automated Workflow

1. **Code Commit**: Developer pushes code to GitHub repository
2. **Trigger**: GitHub Actions workflow activates on self-hosted EC2 runner
3. **Build**: Docker image is built with latest code changes
4. **Registry**: Image pushed to Amazon ECR (Elastic Container Registry)
5. **Deploy**: Automated deployment to EC2 production instance
6. **Validation**: Health checks ensure successful deployment

### Key Benefits

- ✅ **Automated Deployment**: Zero-downtime deployments on every commit
- ✅ **Self-Hosted Runner**: Full control over build environment and resources
- ✅ **Container Registry**: Version-controlled Docker images in ECR
- ✅ **Scalable Infrastructure**: EC2-based deployment ready for scaling
- ✅ **Environment Isolation**: Separate staging and production environments

### Environment Variables Required

```bash
AWS_ACCESS_KEY_ID          # AWS credentials for S3 and ECR access
AWS_SECRET_ACCESS_KEY      # AWS secret key
AWS_DEFAULT_REGION         # AWS region (e.g., us-east-1)
MONGODB_URL                # MongoDB Atlas connection string
```

## 📊 ML Pipeline Components

### End-to-End Workflow

1. **Data Ingestion**: 
   - Fetches data from MongoDB Atlas
   - Splits into training and testing datasets
   - Stores in feature store for reproducibility

2. **Data Validation**: 
   - Validates schema and data types
   - Detects data drift using Evidently AI
   - Generates drift reports for monitoring

3. **Data Transformation**: 
   - Handles missing values and outliers
   - Applies encoding (One-Hot, Ordinal)
   - Feature scaling (StandardScaler, PowerTransformer)
   - Handles class imbalance using SMOTE

4. **Model Training**: 
   - Trains multiple algorithms (XGBoost, CatBoost)
   - Hyperparameter tuning for optimal performance
   - Cross-validation for model robustness

5. **Model Evaluation**: 
   - Evaluates on precision, recall, F1-score, AUC
   - Validates against acceptance thresholds
   - Compares with baseline models

6. **Model Pusher**: 
   - Saves approved models to AWS S3
   - Updates production model artifacts
   - Maintains model version history

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

### Production Deployment

- **Hosting**: AWS EC2 instance
- **Port**: 8080
- **Container**: Docker-based deployment
- **Registry**: Amazon ECR for image management
- **Storage**: AWS S3 for model artifacts
- **Database**: MongoDB Atlas for application data

## 👨‍💻 Author

**Shreyash Jiwane**  
Email: shrey.jiwane09@gmail.com

## 📝 License

This project is open source and available for educational purposes.

---

*Built as part of MLOps learning and practical implementation of production-ready machine learning systems.*
