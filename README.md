<div align="center">

# 🚗 Vehicle MLOps Pipeline

### End-to-End Machine Learning Lifecycle • Automated Training • Model Registry • CI/CD • Cloud Deployment

**A production-oriented MLOps project that demonstrates how a machine learning model can move from raw data to a reproducible, validated, containerized, cloud-deployed prediction system.**

<br/>

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python\&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green?logo=mongodb\&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-S3%20%7C%20ECR%20%7C%20EC2-orange?logo=amazonaws\&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker\&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-black?logo=githubactions\&logoColor=white)
![MLOps](https://img.shields.io/badge/MLOps-End--to--End-purple)

<br/>

**Data Engineering** • **Model Training** • **Model Evaluation** • **Model Registry** • **CI/CD** • **Cloud Deployment**

</div>

---

## 📌 Project Overview

This project demonstrates a complete **end-to-end MLOps workflow** for a vehicle-related machine learning problem.

Instead of stopping at model training inside a Jupyter Notebook, the project focuses on the complete ML lifecycle:

> **Data → Validation → Transformation → Training → Evaluation → Model Registry → Deployment → Prediction**

The system follows a modular architecture where individual ML stages are implemented as reusable components and connected through automated pipelines.

It integrates **MongoDB Atlas** for data storage, **AWS S3** for model registry, **Docker** for containerization, **AWS ECR** for container image storage, **AWS EC2** for deployment, and **GitHub Actions** for automated CI/CD.

---

# ✨ What Makes This Project Different?

Traditional ML projects often look like:

```text
Dataset → Notebook → Model → Accuracy
```

This project takes the production-oriented approach:

```text
                    ┌──────────────────┐
                    │  MongoDB Atlas   │
                    │   Data Source    │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │  Data Ingestion  │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Data Validation  │
                    │   schema.yaml    │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌─────────────────────┐
                    │ Data Transformation │
                    │ Feature Engineering │
                    └─────────┬───────────┘
                              │
                              ▼
                    ┌──────────────────┐
                    │  Model Training  │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Model Evaluation │
                    └───────┬──────────┘
                            │
                       Better Model?
                            │
                            ▼
                    ┌──────────────────┐
                    │ AWS S3 Registry  │
                    │ Versioned Model  │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Prediction Layer │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Docker Container │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │    AWS ECR       │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │    AWS EC2       │
                    │ Production App   │
                    └──────────────────┘
```

---

# 🧠 MLOps Concepts Demonstrated

This repository showcases more than model development. It demonstrates several concepts used in real ML engineering environments.

| Area                   | Implementation                                           |
| ---------------------- | -------------------------------------------------------- |
| 📥 Data Ingestion      | Fetches dataset programmatically from MongoDB Atlas      |
| ✅ Data Validation      | Dataset structure checked using schema configuration     |
| 🔄 Data Transformation | Preprocessing and feature engineering pipeline           |
| 🤖 Model Training      | Reusable model training component                        |
| 📊 Model Evaluation    | Compares candidate and existing models                   |
| 📦 Model Registry      | Production models stored in AWS S3                       |
| 🚀 Model Pusher        | Pushes approved model artifacts to the registry          |
| 🔮 Prediction Pipeline | Loads trained artifacts for inference                    |
| 📝 Logging             | Centralized application logging                          |
| ⚠️ Exception Handling  | Custom exception handling across pipeline components     |
| 🐳 Containerization    | Application packaged using Docker                        |
| 🔁 CI/CD               | Automated build/deployment workflow using GitHub Actions |
| 📦 Container Registry  | Docker images stored in AWS ECR                          |
| ☁️ Deployment          | Application hosted on AWS EC2                            |
| 🔄 Retraining          | Training pipeline can be triggered through a route       |

---

# 🛠️ Technology Stack

### 👨‍💻 Core Development

```text
Python 3.10
Conda
Pip
PyProject
setup.py
YAML
Jupyter Notebook
```

### 📊 Machine Learning & Data Engineering

```text
Exploratory Data Analysis
Feature Engineering
Data Validation
Data Transformation
Model Training
Model Evaluation
Prediction Pipeline
```

### 🗄️ Database

```text
MongoDB Atlas
```

MongoDB serves as the upstream data source for the training pipeline.

Raw records are stored inside MongoDB collections and retrieved programmatically during **Data Ingestion**.

### ☁️ AWS Services

```text
AWS IAM
AWS S3
AWS ECR
AWS EC2
```

**S3** → ML model registry
**ECR** → Docker image registry
**EC2** → Application deployment
**IAM** → Controlled AWS service access

### ⚙️ DevOps / MLOps

```text
Git
GitHub
GitHub Actions
Docker
Self-Hosted GitHub Runner
Environment Variables
Automated CI/CD
```

---

# 🏗️ Modular Project Architecture

The project separates **configuration, components, entities, pipelines, storage, utilities and application logic** instead of keeping everything inside a single notebook.

```text
vehicle-mlops/
│
├── .github/
│   └── workflows/
│       └── aws.yaml
│
├── artifact/
│
├── config/
│   └── schema.yaml
│
├── notebook/
│   ├── mongoDB_demo.ipynb
│   └── EDA / Feature Engineering notebooks
│
├── src/
│   │
│   ├── aws_storage/
│   │
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_validation.py
│   │   ├── data_transformation.py
│   │   ├── model_trainer.py
│   │   ├── model_evaluation.py
│   │   └── model_pusher.py
│   │
│   ├── configuration/
│   │   ├── mongo_db_connections.py
│   │   └── aws_connection.py
│   │
│   ├── constants/
│   │
│   ├── data_access/
│   │
│   ├── entity/
│   │   ├── config_entity.py
│   │   ├── artifact_entity.py
│   │   ├── estimator.py
│   │   └── s3_estimator.py
│   │
│   ├── exception/
│   │
│   ├── logger/
│   │
│   ├── pipeline/
│   │   ├── training_pipeline.py
│   │   └── prediction_pipeline.py
│   │
│   └── utils/
│       └── main_utils.py
│
├── static/
├── templates/
│
├── app.py
├── demo.py
├── template.py
├── setup.py
├── pyproject.toml
├── requirements.txt
├── Dockerfile
├── .dockerignore
└── README.md
```

> The exact folder structure may vary slightly as the project evolves.

---

# 🔄 Complete ML Pipeline

## 1️⃣ Data Ingestion

The first production pipeline component connects directly to **MongoDB Atlas**.

```text
MongoDB Atlas
      ↓
MongoDB Connection
      ↓
Data Access Layer
      ↓
Fetch Collection
      ↓
Convert Records → DataFrame
      ↓
Create Data Ingestion Artifact
```

This separates database access from the ML pipeline and makes the data source configurable.

---

## 2️⃣ Data Validation

Before training, the incoming dataset is validated against the expected schema.

The project maintains dataset information inside:

```text
config/schema.yaml
```

This enables the pipeline to verify that the received data satisfies expected structural requirements before moving further.

```text
Incoming Dataset
       ↓
Schema Configuration
       ↓
Validation Checks
       ↓
Validated Dataset
```

This helps prevent invalid or unexpected data from silently entering the model-training pipeline.

---

## 3️⃣ Data Transformation

Once the dataset passes validation, the transformation component performs preprocessing and prepares features for machine learning.

```text
Validated Data
      ↓
Preprocessing
      ↓
Feature Engineering
      ↓
Transformation Pipeline
      ↓
Model-Ready Dataset
```

Transformation logic is kept separate from model training so the same preprocessing workflow can later be reused during prediction.

---

## 4️⃣ Model Training

The transformed dataset is passed to the **Model Trainer**.

The trainer is responsible for creating and storing the trained ML artifact.

```text
Transformed Data
       ↓
Model Trainer
       ↓
Train Model
       ↓
Evaluate Training Result
       ↓
Model Artifact
```

The project uses reusable estimator abstractions instead of tightly coupling inference logic with one script.

---

## 5️⃣ Model Evaluation

A newly trained model should not automatically replace the existing production model.

The project therefore contains a dedicated **Model Evaluation** stage.

```text
New Model
    +
Existing Production Model
          ↓
     Comparison
          ↓
Performance Improvement?
     ↓             ↓
    YES            NO
     ↓              ↓
Accept Model    Reject Model
```

A model-change threshold is configured in the project:

```python
MODEL_EVALUATION_CHANGED_THRESHOLD_SCORE = 0.02
```

This introduces a controlled model-promotion mechanism instead of blindly deploying every new training result.

---

# 📦 Model Registry with AWS S3

Approved model artifacts can be stored inside an **AWS S3-based model registry**.

```text
Model Evaluation
       ↓
Approved Model
       ↓
Model Pusher
       ↓
AWS S3
       ↓
model-registry/
```

Example configuration:

```python
MODEL_BUCKET_NAME = "my-model-mlopsproj"
MODEL_PUSHER_S3_KEY = "model-registry"
```

The S3 abstraction provides functionality for pulling and pushing model artifacts between the application and cloud storage.

This allows the prediction system to work with the approved model rather than depending only on local files.

---

# 🔮 Prediction Pipeline

The project contains a dedicated prediction pipeline for performing inference.

```text
User Input
    ↓
Prediction Pipeline
    ↓
Preprocessing
    ↓
Approved Model
    ↓
Prediction
    ↓
Application Response
```

Separating training and prediction logic makes the application easier to maintain and closer to a real production ML architecture.

---

# 🔁 Training Pipeline

Individual components are orchestrated through a central training pipeline.

```text
Data Ingestion
      ↓
Data Validation
      ↓
Data Transformation
      ↓
Model Trainer
      ↓
Model Evaluation
      ↓
Model Pusher
```

The application can also expose a dedicated training route:

```text
/training
```

allowing the training workflow to be initiated through the application when required.

---

# 📝 Production-Oriented Logging

A centralized logger is implemented so pipeline activity can be tracked during execution.

Instead of relying completely on:

```python
print("Model Training Started")
```

the project uses structured logging throughout the ML workflow.

This is useful for:

* debugging pipeline failures
* tracking execution stages
* deployment monitoring
* investigating unexpected behaviour

---

# ⚠️ Custom Exception Handling

The project also implements a custom exception layer.

```text
Application Error
       ↓
Custom Exception
       ↓
Error Context
       ↓
Logger
```

This provides more useful debugging information than isolated Python exceptions and makes errors easier to trace across pipeline components.

---

# 🗃️ MongoDB Atlas Integration

MongoDB Atlas acts as the project's cloud data source.

The data flow is:

```text
Local Dataset
     ↓
MongoDB Collection
     ↓
MongoDB Atlas
     ↓
Data Access Layer
     ↓
Training Pipeline
```

The database URI is provided through an environment variable instead of being committed to source control.

### Linux / macOS

```bash
export MONGODB_URL="mongodb+srv://<username>:<password>@<cluster-url>"
```

Verify:

```bash
echo $MONGODB_URL
```

### Windows PowerShell

```powershell
$env:MONGODB_URL="mongodb+srv://<username>:<password>@<cluster-url>"
```

Verify:

```powershell
echo $env:MONGODB_URL
```

---

# 🐳 Dockerized Application

The entire application is containerized using Docker.

```text
Source Code
    ↓
Dockerfile
    ↓
Docker Build
    ↓
Container Image
    ↓
AWS ECR
    ↓
AWS EC2
```

This provides a consistent runtime environment across development and deployment environments.

---

# ♾️ CI/CD Pipeline

One of the major highlights of this project is its automated deployment workflow.

The repository uses:

```text
GitHub Actions
+
AWS ECR
+
Docker
+
AWS EC2
+
Self-Hosted Runner
```

### CI/CD Architecture

```text
Developer
    │
    │ git push
    ▼
GitHub Repository
    │
    ▼
GitHub Actions
    │
    ├── Build Docker Image
    │
    ├── Authenticate with AWS
    │
    ├── Push Image to ECR
    │
    ▼
AWS ECR
    │
    ▼
Self-Hosted GitHub Runner
    │
    ▼
AWS EC2
    │
    ├── Pull Image
    │
    ├── Start Container
    │
    ▼
🚀 Updated ML Application
```

A new commit can therefore trigger the deployment workflow without manually rebuilding and transferring the application.

---

# 🔐 GitHub Actions Secrets

Sensitive AWS credentials are **not intended to be stored directly in source code**.

The CI/CD workflow expects repository secrets such as:

```text
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
ECR_REPO
```

For production environments, credentials should follow the **principle of least privilege**, and AWS IAM roles or short-lived credentials should be preferred wherever possible.

---

# ☁️ AWS Deployment Architecture

The deployment combines multiple AWS services:

```text
                       ┌─────────────┐
                       │   GitHub    │
                       └──────┬──────┘
                              │
                              ▼
                    ┌─────────────────┐
                    │ GitHub Actions  │
                    └───────┬─────────┘
                            │
                    Build Docker Image
                            │
                            ▼
                       ┌─────────┐
                       │ AWS ECR │
                       └────┬────┘
                            │
                       Pull Image
                            │
                            ▼
                       ┌─────────┐
                       │ AWS EC2 │
                       └────┬────┘
                            │
                            ▼
                     ML Application

Approved Models ───────────────► AWS S3
Training Data  ────────────────► MongoDB Atlas
```

---

# 🚀 Getting Started

## 1. Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_REPOSITORY_NAME>
```

---

## 2. Create the Project Environment

```bash
conda create -n vehicle python=3.10 -y
```

Activate it:

```bash
conda activate vehicle
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Verify the installed packages:

```bash
pip list
```

The repository uses `setup.py` / `pyproject.toml` configuration to make internal source packages importable across the project.

---

## 4. Configure MongoDB

Create the environment variable:

```bash
export MONGODB_URL="<YOUR_MONGODB_CONNECTION_STRING>"
```

or on PowerShell:

```powershell
$env:MONGODB_URL="<YOUR_MONGODB_CONNECTION_STRING>"
```

---

## 5. Configure AWS Credentials

For local development, configure AWS credentials through your environment or the AWS CLI.

Required AWS access includes services used by this project such as:

```text
S3
ECR
EC2
```

> Never commit AWS credentials, MongoDB passwords, `.env` files or access keys into the repository.

---

## 6. Run Training Pipeline

The project's training pipeline executes:

```text
Ingestion
   ↓
Validation
   ↓
Transformation
   ↓
Training
   ↓
Evaluation
   ↓
Model Registry
```

The exact entry point can be configured according to the project implementation.

---

## 7. Run the Application

```bash
python app.py
```

After deployment, the application can be exposed through the configured EC2 port, for example:

```text
http://<EC2-PUBLIC-IP>:5080
```

The corresponding EC2 security group must allow only the network access required for the deployed application.

---

# 📓 Experimentation vs Production Code

The repository intentionally separates experimental work from production code.

### Notebook Layer

Used for:

```text
EDA
Dataset Exploration
MongoDB Experiments
Feature Engineering Experiments
```

### Source Layer

Used for:

```text
Reusable Components
Configuration
Pipeline Orchestration
Cloud Integration
Prediction
Deployment
```

This separation helps prevent the common problem of turning a large experimental notebook directly into a production application.

---

# 🧩 Configuration-Driven Design

Important application settings are centralized through configuration files and constants.

Examples include:

```text
Database configuration
Dataset schema
Artifact paths
AWS region
S3 model registry location
Model evaluation threshold
Pipeline configuration
```

This reduces hard-coded logic and makes individual components easier to modify.

---

# 🛡️ Production Considerations

The project demonstrates the deployment lifecycle while keeping security-sensitive values outside the Git repository.

For a production deployment, additional hardening should include:

```text
✓ Least-privilege IAM policies
✓ Private S3 model buckets
✓ Restricted MongoDB network access
✓ Restricted EC2 security-group rules
✓ HTTPS / reverse proxy
✓ IAM roles instead of long-lived credentials
✓ Application authentication where required
✓ Monitoring and alerting
✓ Model/data drift monitoring
✓ Automated testing before deployment
```

---

# 💡 Engineering Principles Used

### Separation of Concerns

Database access, configuration, transformation, training and deployment logic are maintained as separate modules.

### Reproducibility

Dependencies and runtime configuration are explicitly managed.

### Pipeline-Based ML

The ML workflow is implemented as independent stages instead of one monolithic script.

### Model Promotion

New models are evaluated before they are promoted to the model registry.

### Cloud Model Registry

Approved artifacts are stored independently from the application server.

### Automated Delivery

GitHub Actions, Docker, ECR and EC2 provide an automated route from source-code changes to deployment.

---

# 🌟 Key Features

```text
✅ End-to-End ML Training Pipeline
✅ MongoDB Atlas Data Integration
✅ Automated Data Ingestion
✅ Schema-Based Data Validation
✅ Feature Transformation Pipeline
✅ Modular Model Training
✅ Model Evaluation Before Promotion
✅ AWS S3 Model Registry
✅ Automated Model Pusher
✅ Reusable Prediction Pipeline
✅ Centralized Logging
✅ Custom Exception Handling
✅ Docker Containerization
✅ AWS ECR Container Registry
✅ AWS EC2 Deployment
✅ GitHub Actions CI/CD
✅ Self-Hosted GitHub Runner
✅ Environment-Based Secret Management
✅ Application-Based Model Retraining
```

---

# 🔮 Future Improvements

This architecture can be extended with several additional production MLOps capabilities:

### 📊 Monitoring

```text
Model Performance Monitoring
Data Drift Detection
Concept Drift Detection
Infrastructure Monitoring
```

### 🧪 Automated Testing

```text
Unit Tests
Data Validation Tests
Pipeline Tests
API Tests
Docker Build Tests
```

### 📈 Observability

Potential integrations:

```text
Prometheus
Grafana
CloudWatch
MLflow
```

### 🚦 Safer Deployment Strategies

```text
Model Versioning
Rollback Support
Blue/Green Deployment
Canary Deployment
Automated Model Approval Gates
```

### ⚡ Infrastructure Automation

Infrastructure provisioning can later be automated using tools such as:

```text
Terraform
AWS CloudFormation
```

---

# 🎯 What I Learned

Building this project helped me understand that deploying machine learning is much more than training a high-accuracy model.

The project provided hands-on experience with:

```text
→ Designing modular ML systems
→ Moving data from a cloud database into an ML pipeline
→ Building reusable training components
→ Validating data before model training
→ Separating preprocessing from prediction logic
→ Comparing models before production promotion
→ Managing model artifacts through cloud storage
→ Containerizing ML applications
→ Building CI/CD workflows
→ Managing container images with AWS ECR
→ Deploying applications on AWS EC2
→ Connecting GitHub with cloud infrastructure
→ Managing credentials and configuration outside source code
```

---

# 🧭 End-to-End Journey

```text
                       VEHICLE MLOPS
                            │
                            ▼
                    ┌───────────────┐
                    │     DATA      │
                    └───────┬───────┘
                            │
                            ▼
                     MongoDB Atlas
                            │
                            ▼
                       INGESTION
                            │
                            ▼
                       VALIDATION
                            │
                            ▼
                    TRANSFORMATION
                            │
                            ▼
                        TRAINING
                            │
                            ▼
                       EVALUATION
                            │
                            ▼
                    MODEL REGISTRY
                       AWS S3
                            │
                            ▼
                       PREDICTION
                            │
                            ▼
                        DOCKER
                            │
                            ▼
                        AWS ECR
                            │
                            ▼
                        AWS EC2
                            ▲
                            │
                   GitHub Actions CI/CD
                            ▲
                            │
                         GIT PUSH
```

---

<div align="center">

## ⭐ From Notebook to Production

This repository represents my journey of moving beyond simply **training ML models** and learning how to **design, package, evaluate, automate and deploy machine-learning systems**.

### `Build → Validate → Train → Evaluate → Register → Containerize → Deploy → Predict`

<br/>

**Built with Python • MongoDB • AWS • Docker • GitHub Actions • MLOps**

<br/>

⭐ **If you found this project interesting, consider starring the repository!**

</div>
