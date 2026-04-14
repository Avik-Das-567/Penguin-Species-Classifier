# 🐧 Penguin Species Classifier
An interactive machine learning web application that predicts the species of a penguin based on its physical characteristics. The app leverages a **Random Forest Classifier** and provides real-time predictions through a user-friendly interface.

**🔗 Live App: https://penguins-species-classifier.streamlit.app**

## Overview
This project demonstrates an end-to-end machine learning workflow integrated into a web application. It combines data preprocessing, model training, and inference within a single pipeline, enabling users to input penguin attributes and obtain species predictions instantly. The application is built using **Streamlit** for the frontend and **Scikit-learn** for model development.

## Dataset
The dataset used in this project is the cleaned version of the Palmer Penguins dataset, containing observations of penguins from three species:
- Adelie  
- Chinstrap  
- Gentoo  

**Dataset Source:** [Penguins Dataset](https://raw.githubusercontent.com/dataprofessor/data/master/penguins_cleaned.csv)

### Features used:
- Island  
- Bill length (mm)  
- Bill depth (mm)  
- Flipper length (mm)  
- Body mass (g)  
- Sex  

### Target variable:
- Species  

The data is dynamically loaded from an external source within the application.

## Tech Stack

- **Frontend:** Streamlit  
- **Backend / ML:** Scikit-learn  
- **Data Handling:** Pandas, NumPy  

### Dependencies:
- streamlit  
- numpy  
- pandas  
- scikit-learn  

## Machine Learning Model

The application uses a **Random Forest Classifier**, an ensemble learning method that builds multiple decision trees and aggregates their predictions.

### Key characteristics:
- Handles both numerical and categorical features  
- Robust to overfitting compared to single decision trees  
- Provides class probability estimates  

The model is trained dynamically within the app during runtime using the full dataset.

## Project Workflow & Pipeline

The application follows a structured machine learning pipeline:

### 1. Data Loading
- Dataset is fetched from an external CSV source
- Loaded into a Pandas DataFrame
- Features (`X_raw`) and target (`y_raw`) are separated

### 2. User Input Collection
- Inputs are captured via sidebar widgets:
  - Dropdowns for categorical variables
  - Sliders for numerical variables  
- A single-row DataFrame is created for user input

### 3. Data Integration
- User input is concatenated with the original dataset  
- Ensures consistent encoding across both training and inference data  

### 4. Feature Engineering
- Categorical variables (`island`, `sex`) are encoded using **one-hot encoding**
- This transformation is applied uniformly to both training data and input sample

### 5. Target Encoding
- Species labels are mapped to numerical values:
  - Adelie → 0  
  - Chinstrap → 1  
  - Gentoo → 2  

### 6. Model Training
- A Random Forest Classifier is initialized and trained on the processed dataset
- Training occurs at runtime using all available data

### 7. Prediction & Inference
- The trained model predicts:
  - **Class label** (species)
  - **Class probabilities** for each species  
- Output is formatted into a structured DataFrame

### 8. Output Visualization
- Prediction probabilities are displayed using progress bars  
- Final predicted species is highlighted prominently  

## Application Features

- Interactive input controls for real-time predictions  
- Visualization of dataset relationships via scatter plots  
- Transparent data exploration using expandable sections  
- Probability-based prediction display for interpretability  

## Key Design Decisions

### 1. Dynamic Training
The model is trained during each run instead of using a pre-trained model.  
This ensures:
- Simplicity of deployment  
- No dependency on serialized model files  

### 2. Unified Encoding Strategy
Combining input data with the original dataset before encoding guarantees:
- Consistent feature alignment  
- Avoidance of missing dummy variables  

### 3. Lightweight Architecture
The application avoids complex pipelines or external APIs, making it:
- Easy to deploy  
- Easy to understand  
- Suitable for demonstration and learning purposes  

## Conclusion

This project showcases the practical integration of machine learning into an interactive web application. It highlights the complete lifecycle, from data preprocessing to real-time inference, within a clean and accessible interface.

The application serves as a strong demonstration of:
- Applied machine learning.
- Data preprocessing techniques.
- Model deployment using Streamlit.
