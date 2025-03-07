# 📊 Telecom Customer Churn Prediction - MLOps Pipeline

## 🚀 Project Overview

This repository contains a comprehensive end-to-end MLOps pipeline for predicting customer churn in the telecom sector using Neural Network models. Leveraging best practices in machine learning operations, this project integrates automated workflows, experiment tracking, model deployment, containerization, and monitoring systems to create a production-ready ML solution.

### Scientific Approach

The customer churn prediction model implements a neural network architecture, which is particularly effective for this domain due to:

1. **Non-linear pattern recognition**: Neural networks excel at capturing complex non-linear relationships between customer attributes and churn behavior
2. **Feature interaction learning**: The model automatically discovers interactions between multiple features without explicit feature engineering
3. **Scalability with data volume**: The architecture efficiently handles large telecom datasets with numerous features
4. **Adaptability**: The pipeline supports hyperparameter tuning to find optimal configurations for the model

## 📑 Key Features

✅ **Modularized Code Architecture**: Clean separation of concerns with dedicated modules for each ML pipeline step  
✅ **Automated CI/CD Workflows**: Comprehensive automation via Makefile for consistent, reproducible execution  
✅ **Experiment Tracking**: MLflow integration for logging metrics, hyperparameters, and model artifacts  
✅ **REST API for Predictions**: FastAPI service with Swagger UI for interactive model predictions  
✅ **Containerized Deployment**: Docker packaging for consistent runtime environments  
✅ **Comprehensive Monitoring**: Performance visualization via MLflow, Elasticsearch, and Kibana  
✅ **Data & Model Validation**: Built-in validation steps to ensure data quality and model performance  


## 🏗️ Project Architecture

```sh
📂 churn-mlops/
├── 📂 api/                 # FastAPI implementation
│   └── 💻 app.py           # API endpoints and prediction logic
├── 📂 data/                # Dataset and preprocessing artifacts
│   ├── 📜 telecom_df_encoded.csv   # Processed dataset
├── 📂 models/              # Trained model storage
│   ├── 📜 nn_model.joblib  # Serialized neural network model
│   └── 📜 scaler.joblib    # Feature scaling parameters
├── 📂 tests/               # Unit and integration tests
├── 📂 mlruns/              # MLflow experiment tracking data
├── 📜 mlflow.db            # Local storage file for MLflow experiment 
├── 💻 main.py              # Main execution script with CLI interface
├── 💻 model_pipeline.py    # Modularized ML functions
├── 💻 monitoring.py        # System resource monitoring
├── 💻 logger.py            # Logging to Elasticsearch
├── 📜 Dockerfile           # Container definition
├── 📜 docker-compose.yml   # Multi-container setup for monitoring
├── 📜 requirements.txt     # Project dependencies
├── 📜 Makefile             # Automation commands
└── 📜 README.md            # Project documentation
```

## 📌 Project Phases

The project is implemented in six distinct phases:

### 1️⃣ Modularization
- Conversion of notebook-based code into a structured, reusable Python package
- Implementation of dedicated functions for each ML pipeline step in `model_pipeline.py`
- Clear separation between data preparation, model training, and evaluation

### 2️⃣ CI/CD Automation
- Comprehensive Makefile for automating the entire workflow
- Automated code quality checks using Black, MyPy, Flake8, and Bandit
- Integrated testing with pytest for ensuring code reliability

### 3️⃣ MLflow Integration
- Experiment tracking for model metrics, parameters, and artifacts
- Model registry for versioning and deployment management
- Performance visualization through the MLflow UI

![image](https://github.com/user-attachments/assets/f21f739c-db1f-4da5-aa94-ffa99750fd4a)


### 4️⃣ API Deployment
- FastAPI service for real-time predictions
- Swagger UI for interactive API documentation and testing
- JSON response format with prediction results and confidence scores

![image](https://github.com/user-attachments/assets/0c86db70-fa0d-4ac8-9620-023693f0b684)
 

### 5️⃣ Containerization
- Docker packaging for consistent deployment across environments
- Multi-container orchestration with Docker Compose
- Automated build, run, and push workflow for Docker images
  
![image](https://github.com/user-attachments/assets/69887992-ca25-46e0-98df-ce7ae895cf12)


### 6️⃣ Monitoring & Observability
- MLflow for model performance tracking
- Elasticsearch for log aggregation and metric storage
- Kibana dashboards for visualization and alerting
- System resource monitoring for deployment health
  
![image](https://github.com/user-attachments/assets/cfb919a0-e4e9-4155-b9f0-fd1f83f91298)


## 🔧 Setup Instructions

### 1️⃣ Clone the Repository

```sh
git clone https://github.com/dhou22/Churn-Prediction--Mlops-.git
cd churn-mlops
```

### 2️⃣ Environment Setup

```sh
# Create virtual environment and install dependencies
make venv
make install

# Verify setup with code quality checks
make ci-test
```

### 3️⃣ Data Preparation

```sh
# Prepare and validate the dataset
make prepare
make validate-data
```

### 4️⃣ Model Training & Evaluation

```sh
# Train the model with MLflow tracking
make train-mlflow

# Evaluate model performance
make evaluate

# Register model in MLflow registry
make mlflow-registry
```

![image](https://github.com/user-attachments/assets/6a11444a-4137-4676-9dcb-f7733d1a43cb)


### 5️⃣ API Deployment

```sh
# Start the FastAPI service
make run-api

# Open Swagger UI documentation
make open-swagger
```

The API will be available at: [[http://localhost:8080/docs](http://127.0.0.1:8000/docs)](http://127.0.0.1:8000/docs)

### Example Prediction Request

```json
{
  "row_index": 50
}
```

### Example Response

```json
{
  "message": "🎉 Churn prediction result successfully generated! 🎉",
  "row_index": 50,
  "prediction": 1,
  "prediction_message": "❌ This customer is likely to churn.",
  "prediction_probability": 1,
  "prediction_confidence": "💯 Prediction confidence: 100.00%",
  "input_features": {
    "Account length": 138,
    "Area code": 408,
    "Number vmail messages": 0,
    "Total day minutes": 241.8,
    "Total day calls": 93,
    "Total day charge": 41.11,
    "Total eve minutes": 170.5,
    "Total eve calls": 83,
    "Total eve charge": 14.49,
    "Total night minutes": 295.3,
    "Total night calls": 104,
    "Total night charge": 13.29,
    "Total intl minutes": 11.8,
    "Total intl calls": 7,
    "Total intl charge": 3.19,
    "Customer service calls": 3,
    "State_encoded": 10,
    "International plan_encoded": 0,
    "Voice mail plan_encoded": 0
  },
  "note": "ℹ️ Churn prediction is based on customer behavior and interaction data."
}
```

### 6️⃣ Monitoring Setup

```sh
# Start MLflow server
make mlflow-server

# Start Elasticsearch and Kibana
make start-monitoring

# Monitor system resources
make monitor-system
```

![image](https://github.com/user-attachments/assets/12ecfa45-0e92-46da-8bbc-b85589df2c46)



- MLflow UI: [http://localhost:5000](http://127.0.0.1:5000/#/experiments)
- Kibana Dashboard: http://localhost:5601

## pie chart of resources monitoring 
  ![image](https://github.com/user-attachments/assets/bc36501b-61c7-4799-90b9-2f07f948386d)


## churn prediction dashboard 
![image](https://github.com/user-attachments/assets/cf9f0340-2f8c-4992-8411-5f5db85facfc)


## model metrics dashboard 
![image](https://github.com/user-attachments/assets/4bc0340f-5af5-428d-a965-0dd1fdb3c789)



### 7️⃣ Docker Deployment

```sh
# Build and run Docker container
make build
make run
docker run -d -p 8080:8000 --name mlops_project_v3 dhou22/mlops:v2

# Deploy to DockerHub
make push

# Full deployment workflow
make full_deploy
```
![image](https://github.com/user-attachments/assets/6ae5d485-b98b-4d1d-a983-8cac76c298c9)


## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/health` | Check API status |
| POST   | `/predict/` | Get churn prediction (expects JSON input) |



## 🛠️ Makefile Commands

### Setup & Training

| Command | Description |
|---------|-------------|
| `make all` | Full setup & training pipeline |
| `make venv` | Create Python virtual environment |
| `make install` | Install project dependencies |
| `make ci-test` | Run code quality checks |
| `make prepare` | Prepare data for training |
| `make validate-data` | Validate data quality |
| `make train-mlflow` | Train model with MLflow logging |
| `make mlflow-registry` | Register model in MLflow registry |
| `make evaluate` | Evaluate model performance |
| `make test` | Run unit tests |

### Deployment

| Command | Description |
|---------|-------------|
| `make run-api` | Start FastAPI service |
| `make open-swagger` | Open Swagger UI in browser |
| `make build` | Build Docker image |
| `make run` | Run Docker container |
| `make stop` | Stop and remove Docker container |
| `make push` | Push Docker image to DockerHub |
| `make deploy` | Build and push Docker image |
| `make full_deploy` | Complete deployment workflow |

### Monitoring

| Command | Description |
|---------|-------------|
| `make mlflow-ui` | Start MLflow UI |
| `make mlflow-server` | Start MLflow server |
| `make start-monitoring` | Start Elasticsearch & Kibana |
| `make log-test` | Send test logs to Elasticsearch |
| `make monitor-system` | Monitor system resources |
| `make monitor-docker` | Monitor Docker containers |
| `make detect-drift` | Run model drift detection |

### Maintenance

| Command | Description |
|---------|-------------|
| `make clean` | Clean temporary files |
| `make clean-logs` | Clean logs & MLflow data |
| `make clean-all` | Full project reset |
| `make ci-cd` | Run full CI/CD pipeline |
| `make notify-success` | Send notification via Slack/Email |
| `make help` | Show available commands |

## 📈 Model Performance

The neural network model is evaluated on several key metrics:

- **Accuracy**: Overall prediction correctness
- **Precision**: Proportion of correct positive predictions
- **Recall**: Proportion of actual positives correctly identified
- **F1 Score**: Harmonic mean of precision and recall
- **AUC-ROC**: Area under the ROC curve
- **Log Loss**: Cross-entropy loss function value

MLflow automatically tracks these metrics across experiments, enabling systematic comparison of model versions.


Here's an improved version of your README section:

---

## 📜 License

This project is licensed under the **MIT License**.  
© 2024 **Dhouha Meliane**  
Email: [dhouhameliane@esprit.tn](mailto:dhouhameliane@esprit.tn)


