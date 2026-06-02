# 🪨 Rockfall Risk Predictor

[![Python Version](https://img.shields.io/badge/python-3.9%20%7C%203.10%20%7C%203.11%20%7C%203.12-blue)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/framework-Flask-lightgrey)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

An end-to-end Machine Learning-powered early warning system designed to predict and analyze the likelihood of **rockfall events** based on geological, environmental, and real-time sensor data. 

This repository contains the complete ML workflow—from data ingestion and scaling to model training, evaluation, and a fully interactive **Flask web interface** for real-time predictions.

---

## 🚀 Live Demo

You can access and interact with the live running model here:
👉 **[Live Rockfall Predictor App](https://rockfall-predictor.onrender.com)** *(If deploying to Render, update this URL once active)*

---

## 🚀 Key Features

* **Advanced Predictive Engines**: Evaluates multiple machine learning models (Logistic Regression, Random Forest, AdaBoost, K-Nearest Neighbors, Decision Trees, and CatBoost) to automatically deploy the best-performing model.
* **Robust Preprocessing Pipeline**: Built-in automated pipelines using `scikit-learn` for handling missing data, standardizing features, and handling categorical data.
* **Interactive Web App**: Sleek, modern, responsive UI built with Flask and Bootstrap 5 to input geological values and fetch instant risk assessments.
* **Flexible Architecture**: Dynamically skips heavy native dependencies (e.g., XGBoost) if local C/C++ libraries (like OpenMP) are missing, ensuring high portability across operating systems.

---

## 📂 Project Structure

```text
rockfall-prediction-model/
│
├── artifacts/              # Serialized trained models, preprocessor, and datasets
│   ├── model.pkl           # Best-performing trained model (Random Forest)
│   ├── preprocessor.pkl    # Data transformation pipeline
│   └── data.csv            # Cleaned data splits
│
├── src/                    # Modular source code
│   ├── components/
│   │   ├── data_ingestion.py      # Splits data and initializes pipeline
│   │   ├── data_transformation.py # Scales features and prepares inputs
│   │   └── model_trainer.py       # Trains, hypertunes, and evaluates ML models
│   ├── pipeline/
│   │   └── predict_pipeline.py    # Maps web-form inputs to pipeline model
│   ├── logger_config.py           # Streamlined logging system
│   └── exception_config.py        # Robust custom exception handling
│
├── templates/              # Flask web UI templates
│   ├── index.html          # Dynamic landing page
│   └── home.html           # Prediction form and result display
│
├── static/                 # Stylesheets, logos, and UI assets
├── application.py          # Flask main application entry point
├── setup.py                # Package installation configurations
└── requirements.txt        # Project dependencies
```

---

## ⚙️ Installation & Setup

Ensure you have **Python 3.9+** installed on your system.

### 1. Clone the Repository
```bash
git clone https://github.com/anshspc/Rockfall-Predictor.git
cd rockfall-Predictor
```

### 2. Set Up a Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 🏃 How to Run Locally

### Run the ML Training Pipeline
If you want to re-train the models and update the serialized assets (`.pkl` files) using new datasets:
```bash
python src/components/data_ingestion.py
```

### Start the Web Application
```bash
python application.py
```
Open **[http://127.0.0.1:5000/](http://127.0.0.1:5000/)** in your browser to launch the web dashboard!

---

## 📊 Evaluation & Metrics

The training pipeline automatically tests several classifiers. On the benchmark dataset, the **Random Forest Classifier** achieved the top score:
* **Selected Model**: Random Forest Classifier
* **Test Accuracy**: `71.0%`
* **F1-Score (Weighted)**: `0.618`

---

## 👥 Credits & Developer Info

* **Lead Developer**: **Ansh** ([@anshspc](https://github.com/anshspc))
* **Project Concept**: Machine learning application focused on geological risk estimation and disaster prevention.

---

## 📬 Contact & Connect

If you have questions, feedback, or would like to collaborate, feel free to reach out:

* **GitHub**: [@anshspc](https://github.com/anshspc)
* **LinkedIn**: [Your LinkedIn Profile](https://linkedin.com/in/your-linkedin-username) *(Update with your link)*
* **Email**: [anshspc@users.noreply.github.com](mailto:anshspc@users.noreply.github.com)

---

## 🛡️ License

This project is open-source and licensed under the **MIT License**.
