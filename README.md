# 📊 Churn Prediction - MLOps Pipeline

## 🚀 Project Overview

This repository contains an end-to-end **MLOps pipeline** for **Customer Churn Prediction** using a Neural Network model. The project follows industry-standard MLOps practices, integrating:

- **Automated CI/CD** (via Makefile)
- **Model Tracking & Experimentation** (MLflow)
- **API Deployment** (FastAPI)
- **Containerization** (Docker & DockerHub)
- **Monitoring** (Elasticsearch & Kibana)

## 📑 Features

✅ **Modularized Code**: Well-structured components for data processing, training, and prediction.
✅ **Automated Workflows**: All key steps automated using a Makefile.
✅ **Experiment Tracking**: MLflow for logging metrics, hyperparameters, and artifacts.
✅ **REST API for Predictions**: FastAPI serving the trained model.
✅ **Containerized Deployment**: Docker to package the entire application.
✅ **Model & System Monitoring**: Kibana dashboard visualizing logs from Elasticsearch.
✅ **CI/CD Integration**: Automated testing, training, and deployment pipelines.

## 🏗️ Project Architecture

```
📂 churn-mlops
├── 📂 data/                # Processed data files
├── 📂 models/              # Trained model artifacts
├── 📂 scripts/             # Python scripts for training and evaluation
├── 📂 api/                 # FastAPI service
├── 📜 main.py              # Main training pipeline
├── 📜 app.py               # FastAPI app
├── 📜 Dockerfile           # Docker image setup
├── 📜 docker-compose.yml   # Multi-container setup
├── 📜 Makefile             # Automation commands
└── 📜 README.md            # Project Documentation
```

## 📌 Setup Instructions

### 1️⃣ **Clone the Repository**

```sh
git clone https://github.com/yourusername/churn-mlops.git
cd churn-mlops
```

### 2️⃣ **Set Up Virtual Environment & Install Dependencies**

```sh
make venv
make install
```

### 3️⃣ **Run MLflow for Experiment Tracking**

```sh
make mlflow-ui
```

- Access MLflow UI at [**http://localhost:5000**](http://localhost:5000)

### 4️⃣ **Train the Model with MLflow Logging**

```sh
make train-mlflow
```

### 5️⃣ **Register Model in MLflow Registry**

```sh
make mlflow-registry
```

### 6️⃣ **Deploy API using FastAPI**

```sh
make run-api
```

- API available at [**http://localhost:8000/docs**](http://localhost:8000/docs)

### 7️⃣ **Run Monitoring Stack (Elasticsearch & Kibana)**

```sh
make start-monitoring
```

- Kibana Dashboard: [**http://localhost:5601**](http://localhost:5601)

### 8️⃣ **Build & Deploy with Docker**

```sh
make build
make push
make run
```

- API will be accessible at `http://localhost:8080`

### 9️⃣ **Run Full CI/CD Pipeline**

```sh
make ci-cd
```

## 📡 Endpoints

| Method | Endpoint    | Description                               |
| ------ | ----------- | ----------------------------------------- |
| GET    | `/health`   | Check API status                          |
| POST   | `/predict/` | Get churn prediction (expects JSON input) |

## 📊 Monitoring Setup

- **MLflow**: Tracks experiments, parameters, and model performance.
- **Elasticsearch**: Collects logs and performance metrics.
- **Kibana**: Visualizes logs and trends.
- **System Monitoring**: Tracks CPU, RAM, and Docker container performance.

## 🛠️ Future Enhancements

🔹 Deploy on **Cloud Platforms** (AWS/GCP/Azure)\
🔹 Implement **Model Retraining Pipeline**\
🔹 Improve **Automated Alerting & Logging**

## 📜 License

MIT License © 2024 Your Name

