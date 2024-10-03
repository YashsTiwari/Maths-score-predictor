# Student Performance Prediction Web Application

This repository contains a web application that predicts student performance based on various features like gender, parental level of education, lunch type, and test preparation course. The project follows a modular architecture, utilizing machine learning techniques to predict students' math scores, and is developed using Python, Flask, and multiple regression models.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Project Architecture](#project-architecture)
- [Folder Structure](#folder-structure)
- [How to Use](#how-to-use)
- [Modeling Process](#modeling-process)
- [Web Application Screenshots](#web-application-screenshots)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)

---

## Project Overview

The goal of this project is to predict a student's math score using various demographic and academic features. We employed several machine learning models, evaluated them, and deployed the best-performing model using Flask for real-time predictions. The application allows users to input custom data and receive predicted math scores based on trained models.

---

## Project Architecture

- **Data Ingestion**: Collecting and splitting the dataset into training and testing sets.
- **Data Transformation**: Handling missing values, scaling numerical features, and encoding categorical features using pipelines.
- **Model Training**: Training multiple machine learning models (Random Forest, Decision Tree, Gradient Boosting, XGBoost, etc.) using GridSearchCV to find the best parameters.
- **Prediction Pipeline**: Serving predictions via a web interface where users input features, and the system returns the predicted math score.
  
---

## Folder Structure

```
repo/
│
├── artifacts/                 # Contains generated artifacts like models and preprocessing objects
├── catboost_info/             # CatBoost specific info
├── logs/                      # Logging information
├── notebook/                  # Jupyter notebooks for EDA and model training
├── src/                       # Main source code
│   ├── components/            # Components for data ingestion, transformation, and model training
│   │   ├── __init__.py        # Initialization script
│   │   ├── data_ingestion.py  # Script for data ingestion
│   │   ├── data_transformation.py # Script for data transformation
│   │   ├── model_trainer.py   # Script for training models
│   ├── pipeline/              # Pipeline for predictions
│   │   ├── __init__.py        # Initialization script
│   │   ├── predict_pipeline.py # Prediction pipeline script
│   ├── exception.py           # Custom exception handling
│   ├── logger.py              # Logging configuration
│   ├── utils.py               # Utility functions like saving/loading models, model evaluation
├── static/                    # Static files for the web application (CSS, JS)
├── templates/                 # HTML templates for the web application
├── app.py                     # Flask application entry point
├── setup.py                   # Setup file for the project
├── Readme.md                  # README file
├── .gitignore                 # Files to ignore in Git
└── requirements.txt           # Required libraries for the project
```

---

## How to Use

### Prerequisites

- Python 3.7 or higher
- pip (Python package installer)

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/student-performance-prediction.git
   cd student-performance-prediction
   ```

2. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Start the Flask web application:

   ```bash
   python app.py
   ```

4. Open your browser and go to `http://127.0.0.1:8001/` to access the web interface.

---

## Modeling Process

### Data Ingestion

The `data_ingestion.py` script reads the dataset and splits it into training and testing sets. The raw data is saved to the `artifacts/` folder for reference.

### Data Transformation

The `data_transformation.py` script applies transformations like imputing missing values, scaling numerical columns, and one-hot encoding categorical variables. The transformations are applied via a scikit-learn `Pipeline` for seamless integration with model training.

### Model Training

We train several models, including:
- Random Forest
- Decision Tree
- Gradient Boosting
- XGBoost
- CatBoost
- AdaBoost

The `model_trainer.py` script uses GridSearchCV to find the best parameters for each model. The best model is saved to the `artifacts/` folder as `model.pkl`.

### Prediction Pipeline

The `predict_pipeline.py` script loads the trained model and preprocessing object, applies transformations to the input features, and returns the predicted math score.

---

## Web Application Screenshots

### Home Page
![](https://github.com/YashsTiwari/Maths-score-predictor/blob/c69243800e66af88d5397b0d708c19cc8150a028/home.png)

### Prediction Page
![](https://github.com/YashsTiwari/Maths-score-predictor/blob/c69243800e66af88d5397b0d708c19cc8150a028/predict.png)

---

## Technologies Used

- **Languages**: Python
- **Web Framework**: Flask
- **Machine Learning**: scikit-learn, XGBoost, CatBoost
- **Data Processing**: pandas, numpy
- **Model Tuning**: GridSearchCV
- **Model Evaluation**: r2_score

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a Pull Request.

---

## License

This project is licensed under the MIT License.
