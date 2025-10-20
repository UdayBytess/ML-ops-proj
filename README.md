# 🚗 Vehicle Insurance Prediction MLOps Pipeline

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=for-the-badge&logo=python&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-Cloud-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Container-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-Web_App-000000?style=for-the-badge&logo=flask&logoColor=white)

**A production-grade end-to-end Machine Learning system demonstrating modern MLOps practices**

[Features](#-key-features) • [Architecture](#-architecture-overview) • [Tech Stack](#-tech-stack) • [Getting Started](#-getting-started) • [Deployment](#-cicd--deployment)

</div>

---

## 🎯 Project Overview

The **Vehicle Insurance Prediction MLOps Pipeline** is a comprehensive, production-ready machine learning system that predicts vehicle insurance outcomes using a fully automated workflow. This project showcases industry-standard MLOps practices including cloud integration, containerization, continuous deployment, and model versioning.

Built to demonstrate real-world ML engineering capabilities, this system handles everything from automated data ingestion to cloud deployment with monitoring and scalability in mind.

### 🌟 What Makes This Project Stand Out

- **End-to-End Automation**: From data ingestion to deployment, every step is automated
- **Cloud-Native Architecture**: Built on AWS with S3 for model storage and EC2 for deployment
- **Production-Ready**: Docker containerization with CI/CD pipeline for seamless updates
- **Scalable Database**: MongoDB Atlas integration for cloud-based data management
- **Model Versioning**: Automatic version control and registry using AWS S3
- **Live Web Interface**: Flask-based application for real-time predictions

---

## ✨ Key Features

### 🔄 **Complete MLOps Workflow**
- **Automated Data Pipeline**: MongoDB Atlas → Schema Validation → Feature Engineering → Model Training
- **Version Control**: Git-based tracking with modular, reusable components
- **Model Registry**: AWS S3 integration for storing and versioning trained models
- **Continuous Deployment**: GitHub Actions automates build, test, and deploy cycles

### 🛡️ **Production-Grade Quality**
- **Custom Logging System**: Comprehensive logging for debugging and monitoring
- **Exception Handling**: Robust error handling across all pipeline stages
- **Schema Validation**: YAML-based data validation ensuring data integrity
- **Model Evaluation**: Automated performance tracking and comparison

### ☁️ **Cloud Infrastructure**
- **AWS EC2**: Scalable compute for model deployment
- **AWS S3**: Reliable storage for model artifacts and versioning
- **AWS ECR**: Container registry for Docker images
- **MongoDB Atlas**: Managed NoSQL database with global accessibility

### 🚀 **Deployment & Accessibility**
- **Docker Containerization**: Ensures consistency across environments
- **Self-Hosted Runners**: GitHub Actions runner on EC2 for automated deployment
- **Web Interface**: User-friendly Flask app for predictions
- **API Endpoints**: RESTful endpoints for training and prediction

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                         DATA INGESTION LAYER                         │
├─────────────────────────────────────────────────────────────────────┤
│  MongoDB Atlas  →  Data Access Module  →  Pandas DataFrame          │
└─────────────────────────────────────────────────────────────────────┘
                                 ↓
┌─────────────────────────────────────────────────────────────────────┐
│                      DATA PROCESSING LAYER                           │
├─────────────────────────────────────────────────────────────────────┤
│  Schema Validation  →  Data Transformation  →  Feature Engineering  │
└─────────────────────────────────────────────────────────────────────┘
                                 ↓
┌─────────────────────────────────────────────────────────────────────┐
│                        MODEL TRAINING LAYER                          │
├─────────────────────────────────────────────────────────────────────┤
│  Train Model  →  Evaluate Performance  →  Save Artifacts            │
└─────────────────────────────────────────────────────────────────────┘
                                 ↓
┌─────────────────────────────────────────────────────────────────────┐
│                      MODEL DEPLOYMENT LAYER                          │
├─────────────────────────────────────────────────────────────────────┤
│  Push to S3  →  Build Docker Image  →  Deploy to EC2                │
└─────────────────────────────────────────────────────────────────────┘
                                 ↓
┌─────────────────────────────────────────────────────────────────────┐
│                         INFERENCE LAYER                              │
├─────────────────────────────────────────────────────────────────────┤
│  Flask Web App  →  REST API  →  Real-time Predictions               │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

<table>
<tr>
<td valign="top" width="50%">

### **Core Technologies**
- **Language**: Python 3.10
- **ML Framework**: scikit-learn
- **Data Processing**: Pandas, NumPy
- **Web Framework**: Flask
- **Configuration**: PyYAML

### **Cloud & Infrastructure**
- **Cloud Provider**: AWS (S3, EC2, ECR, IAM)
- **Database**: MongoDB Atlas
- **Containerization**: Docker
- **Environment**: Conda

</td>
<td valign="top" width="50%">

### **DevOps & MLOps**
- **Version Control**: Git, GitHub
- **CI/CD**: GitHub Actions
- **Model Storage**: AWS S3
- **Container Registry**: AWS ECR
- **Deployment**: AWS EC2 (Ubuntu)

### **Development Tools**
- **Logging**: Custom Python Logger
- **Exception Handling**: Custom Error Module
- **Notebooks**: Jupyter (EDA & Feature Engineering)
- **Package Management**: pip, setuptools

</td>
</tr>
</table>

---

## 📦 Project Structure

```
vehicle-mlops-pipeline/
│
├── .github/
│   └── workflows/
│       └── aws.yaml              # CI/CD pipeline configuration
│
├── components/
│   ├── data_ingestion.py         # MongoDB to DataFrame pipeline
│   ├── data_validation.py        # Schema validation logic
│   ├── data_transformation.py    # Feature engineering
│   ├── model_trainer.py          # Model training module
│   ├── model_evaluation.py       # Performance evaluation
│   └── model_pusher.py           # Push models to S3
│
├── configuration/
│   ├── mongo_db_connection.py    # MongoDB Atlas connection
│   └── aws_connection.py         # AWS S3 configuration
│
├── constants/
│   └── __init__.py               # Global constants & configs
│
├── data_access/
│   └── proj1_data.py             # Data access layer
│
├── entity/
│   ├── config_entity.py          # Configuration dataclasses
│   ├── artifact_entity.py        # Artifact tracking
│   ├── estimator.py              # Model wrapper
│   └── s3_estimator.py           # S3 model operations
│
├── pipeline/
│   ├── training_pipeline.py      # End-to-end training flow
│   └── prediction_pipeline.py    # Inference pipeline
│
├── utils/
│   └── main_utils.py             # Helper functions
│
├── aws_storage/                  # S3 push/pull utilities
├── config/
│   └── schema.yaml               # Data validation schema
├── notebooks/                    # EDA & experimentation
├── static/                       # Web app assets
├── template/                     # HTML templates
│
├── app.py                        # Flask application
├── demo.py                       # Testing & demo scripts
├── logger.py                     # Custom logging
├── exception.py                  # Custom exceptions
├── template.py                   # Project structure generator
├── setup.py                      # Package setup
├── pyproject.toml                # Project metadata
├── requirements.txt              # Dependencies
├── Dockerfile                    # Container definition
├── .dockerignore                 # Docker exclusions
└── README.md                     # Documentation
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- Conda (recommended)
- MongoDB Atlas account
- AWS account with S3, EC2 access
- Docker installed
- Git

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/UdayBytess/vehicle-mlops-pipeline.git
cd vehicle-mlops-pipeline
```

### 2️⃣ Set Up Environment

```bash
# Create and activate conda environment
conda create -n vehicle python=3.10 -y
conda activate vehicle

# Install dependencies
pip install -r requirements.txt

# Generate project structure (if needed)
python template.py
```

### 3️⃣ Configure MongoDB Atlas

1. Create a MongoDB Atlas account and deploy a free **M0 cluster**
2. Add network access: `0.0.0.0/0` (or your IP)
3. Create a database user
4. Get connection string (Python driver ≥3.6)
5. Set environment variable:

```bash
# Linux/macOS
export MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/"

# Windows PowerShell
$env:MONGODB_URL="mongodb+srv://<username>:<password>@cluster.mongodb.net/"
```

6. Load dataset using `notebook/mongoDB_demo.ipynb`
7. Verify data in MongoDB Atlas → Browse Collections

### 4️⃣ Configure AWS

1. Create IAM user with S3 and EC2 permissions
2. Create S3 bucket: `my-model-mlopsproj` (region: `us-east-1`)
3. Set AWS credentials:

```bash
export AWS_ACCESS_KEY_ID="your_access_key"
export AWS_SECRET_ACCESS_KEY="your_secret_key"
export AWS_DEFAULT_REGION="us-east-1"
```

### 5️⃣ Run the Pipeline

```bash
# Test the setup
python demo.py

# Run training pipeline
python app.py
# Navigate to: http://localhost:5080/training
```

---

## 🔄 Pipeline Stages

### **Stage 1: Data Ingestion**
- Connects to MongoDB Atlas
- Fetches raw vehicle insurance data
- Converts to Pandas DataFrame
- Saves artifacts for next stage

**Files**: `components/data_ingestion.py`, `data_access/proj1_data.py`

### **Stage 2: Data Validation**
- Validates schema using `config/schema.yaml`
- Checks data types, column names, and constraints
- Generates validation report
- Flags anomalies for review

**Files**: `components/data_validation.py`, `utils/main_utils.py`

### **Stage 3: Data Transformation**
- Handles missing values and outliers
- Encodes categorical variables
- Scales numerical features
- Creates feature engineering pipeline
- Saves transformation objects

**Files**: `components/data_transformation.py`, `entity/estimator.py`

### **Stage 4: Model Training**
- Trains scikit-learn model with optimized hyperparameters
- Implements cross-validation
- Saves trained model artifacts
- Logs training metrics

**Files**: `components/model_trainer.py`

### **Stage 5: Model Evaluation**
- Evaluates model on validation set
- Compares with previous best model (from S3)
- Generates performance metrics
- Decides whether to push new model

**Files**: `components/model_evaluation.py`

### **Stage 6: Model Pusher**
- Pushes best-performing model to AWS S3
- Implements version control
- Updates model registry
- Enables rollback capability

**Files**: `components/model_pusher.py`, `entity/s3_estimator.py`

### **Stage 7: Prediction**
- Loads latest model from S3
- Runs inference on new data
- Returns predictions via Flask API
- Provides confidence scores

**Files**: `pipeline/prediction_pipeline.py`, `app.py`

---

## 🐳 Docker Containerization

### Build Docker Image

```bash
docker build -t vehicle-mlops:latest .
```

### Run Container Locally

```bash
docker run -p 5080:5080 \
  -e MONGODB_URL="your_mongodb_url" \
  -e AWS_ACCESS_KEY_ID="your_key" \
  -e AWS_SECRET_ACCESS_KEY="your_secret" \
  -e AWS_DEFAULT_REGION="us-east-1" \
  vehicle-mlops:latest
```

### Dockerfile Highlights

```dockerfile
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
EXPOSE 5080
CMD ["python", "app.py"]
```

---

## ⚙️ CI/CD & Deployment

### GitHub Actions Workflow

The project uses GitHub Actions for automated CI/CD:

1. **Trigger**: Push to `main` branch
2. **Build**: Creates Docker image
3. **Push**: Uploads to AWS ECR
4. **Deploy**: Pulls and runs on EC2 instance

### Setup GitHub Secrets

Add these secrets to your GitHub repository:

```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
MONGODB_URL
```

### EC2 Deployment Setup

1. Launch Ubuntu EC2 instance (t2.medium, 30GB storage)
2. Install Docker:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

3. Configure self-hosted GitHub runner:
   - Go to GitHub repo → Settings → Actions → Runners → New self-hosted runner
   - Follow instructions to set up on EC2

4. Open port 5080 in EC2 security group:
   - Type: Custom TCP
   - Port: 5080
   - Source: 0.0.0.0/0

### Access Deployed Application

```
http://<EC2_PUBLIC_IP>:5080
```

### API Endpoints

- **Training**: `http://<EC2_PUBLIC_IP>:5080/training`
- **Prediction**: `http://<EC2_PUBLIC_IP>:5080/predict`

---

## 📊 Model Performance

The pipeline includes comprehensive model evaluation:

- **Metrics Tracked**: Accuracy, Precision, Recall, F1-Score, AUC-ROC
- **Validation Strategy**: Stratified K-Fold Cross-Validation
- **Model Comparison**: Automatic comparison with previous best model
- **Versioning**: All models stored with timestamps in S3

---

## 🔐 Security Best Practices

- ✅ Environment variables for sensitive credentials
- ✅ IAM roles with least privilege access
- ✅ MongoDB Atlas IP whitelisting
- ✅ Docker secrets management
- ✅ HTTPS for production deployment (recommended)
- ✅ Regular security updates via GitHub Dependabot

---

## 📈 Future Enhancements

- [ ] **MLflow Integration**: Experiment tracking and model registry
- [ ] **Model Monitoring**: Real-time performance tracking with AWS CloudWatch
- [ ] **A/B Testing**: Framework for comparing model versions in production
- [ ] **Streamlit Dashboard**: Interactive analytics and monitoring interface
- [ ] **Kubernetes Deployment**: Container orchestration for scalability
- [ ] **API Rate Limiting**: Prevent abuse and manage resources
- [ ] **Advanced Feature Store**: Centralized feature management
- [ ] **Automated Retraining**: Trigger retraining based on performance drift

---

## 📚 Learning Resources

This project demonstrates concepts from:

- **MLOps**: [AWS MLOps](https://aws.amazon.com/mlops/), [MLOps.org](https://mlops.org/)
- **Cloud Architecture**: [AWS Well-Architected](https://aws.amazon.com/architecture/well-architected/)
- **CI/CD**: [GitHub Actions Docs](https://docs.github.com/en/actions)
- **Docker**: [Docker Official Docs](https://docs.docker.com/)
- **MongoDB**: [MongoDB University](https://university.mongodb.com/)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Uday**  
*Final-Year CSE Student specializing in AI & Machine Learning*  
*The National Institute of Engineering, Mysuru*

[![GitHub](https://img.shields.io/badge/GitHub-UdayBytess-181717?style=for-the-badge&logo=github)](https://github.com/UdayBytess)

---

## ⭐ Acknowledgments

- MongoDB Atlas for cloud database services
- AWS for cloud infrastructure
- GitHub Actions for CI/CD automation
- The open-source community for amazing tools and libraries

---

<div align="center">

### 🌟 If you found this project helpful, please give it a star! 🌟

**Made with ❤️ and a lot of ☕**

</div>
