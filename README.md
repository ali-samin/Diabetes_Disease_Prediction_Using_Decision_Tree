# Diabetes Disease Prediction

This project focuses on predicting whether a patient is diabetic using a dataset containing various health metrics. We implement multiple machine learning models (Decision Tree, Support Vector Classifier, and Naive Bayes) to determine the likelihood of diabetes, with the Decision Tree as the primary model. The project also includes a web-based interface for user interaction, allowing users to input specific health data and receive a diabetes risk prediction.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Model](#model)
- [Files in the Repository](#files-in-the-repository)
- [How to Run](#how-to-run)
- [Technologies Used](#technologies-used)
- [Results and Metrics](#results-and-metrics)

## Project Overview

The main objective of this project is to build and evaluate machine learning models that predict whether a person is diabetic based on multiple health-related attributes. We utilize three models—Decision Tree, Support Vector Classifier, and Naive Bayes—with Decision Tree being the primary model for classification. The models are deployed using Flask, providing an interactive web interface for user inputs and real-time predictions.

## Dataset

The dataset used in this project is located in the `Dataset/diabetes.csv` file. The dataset includes the following features:
- Pregnancies
- Glucose
- Blood Pressure
- Skin Thickness
- Insulin
- BMI (Body Mass Index)
- Diabetes Pedigree Function
- Age
- Outcome (Target variable: 1 for Diabetic, 0 for Non-Diabetic)

Certain columns (like Glucose, Insulin, Blood Pressure) contained 0 values, which were replaced with their mean values, as 0 is not valid for these features.

## Model

The models utilized in this project include:

- **Decision Tree (primary model)**
- **Support Vector Classifier**
- **Naive Bayes**

## Training and Evaluation Steps:
- **Data Preprocessing**: Handling missing or incorrect values (e.g., 0 values for certain features).
- **Feature Scaling**: Standard scaling is applied to standardize features before feeding them into the model.
- **Model Training**: The model was trained using a logistic regression classifier with hyperparameter tuning via grid search.
- **Performance Metrics**: Accuracy, Precision, Recall, and F1-Score were calculated to evaluate the model.

## Files in the Repository

- `Dataset/diabetes.csv`: The dataset used for training and testing the model.
- `Dataset/modelForPrediction.pkl`: Trained Decision Tree model saved using pickle.
- `Model/modelForPredictionSVC.pkl`: Trained Support Vector Classifier model.
- `Model/modelForPredictionGaussionNB.pkl`: Trained Naive Bayes model.
- `Model/standardScaler.pkl`: The scaler used to standardize the input data.
- `Notebook/Decision_Tree_SVC.ipynb`: The Jupyter Notebook containing the code for data preprocessing, training, and evaluation of the model.
- `application.py`: The Flask application to serve the model and handle user inputs for predictions.
- `templates/`: Folder containing HTML files for the front-end of the web application.
  - `home.html`: Home page of the web application.
  - `index.html`: Main page for interacting with the model.
  - `single_prediction.html`: Page displaying the prediction result.

## How to Run

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/ali-samin/Diabetes_Disease_Prediction_Using_Decision_Tree.git
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
3. Run the Flask application:
   ```bash
   python application.py
4. Open a web browser and navigate to http://127.0.0.1:5000/ to access the web interface.

## Technologies Used

- Python: Core programming language.
- Flask: For developing the web application.
- Scikit-learn: For machine learning algorithms.
- Pandas: For data manipulation.
- NumPy: For numerical computations.
- Matplotlib and Seaborn: For data visualization.

## Results and Metrics
Each model was evaluated based on several performance metrics:

- Accuracy: Measures the percentage of correctly predicted cases.
- Precision: The ratio of correctly predicted positive observations to the total predicted positives.
- Recall: The ratio of correctly predicted positive observations to all observations in the actual class.
- F1-Score: A weighted average of Precision and Recall.

The trained model is saved in the Model/modelForPrediction.pkl file and is used in the Flask app to make real-time predictions based on user input.
