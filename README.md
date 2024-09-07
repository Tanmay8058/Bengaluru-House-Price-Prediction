# Bengaluru House Price Prediction

## Project Overview
This project aims to predict house prices in Bengaluru using various features such as area type, location, size, and the number of rooms, bathrooms, and balconies. The dataset contains 13,000 rows and 9 columns, each providing valuable insights into housing prices. The project includes thorough data analysis, feature engineering, handling of categorical and numerical data, model selection, and tuning, followed by deployment using a Scikit-Learn pipeline.

## Dataset Description
The dataset consists of the following columns:
- **Area_type**: The type of area where the house is located (e.g., Super built-up, Plot area).
- **Total_sqft**: The total area of the house in square feet.
- **Location**: The location of the house within Bengaluru.
- **Size**: The size of the house in terms of the number of bedrooms (BHK) or rooms (RK).
- **Society**: The name of the society where the house is located.
- **Bath**: The number of bathrooms in the house.
- **Balcony**: The number of balconies in the house.
- **Price**: The price of the house.

## Key Steps in the Project

### 1. Data Analysis
- **Initial exploration**: Analyzed the structure of the data, including missing values and key statistics.
- **Missing values**: Identified columns with missing data, such as `Society`, `Balcony`, and `Bath`, and explored various imputation techniques to fill in these gaps.

### 2. Feature Selection
- **Domain knowledge & Statistical rules**: Based on domain knowledge, features like `Society` were excluded due to a high number of categories and the potential risk of overfitting. Additionally, statistical methods were used to evaluate feature importance.
- **Dimensionality reduction**: Features that did not contribute significantly to the prediction model were removed to avoid overfitting and high dimensionality.

### 3. Handling Categorical Data
- **Encoding**: Implemented both one-hot encoding and frequency encoding for categorical columns like `Location` and `Area_type`.
- **Data Cleaning**: Used the `FuzzyWuzzy` module to clean and correct misspelled location names, ensuring uniformity across the dataset.
  
### 4. Imputation of Missing Values
- **KNN Imputer**: Applied the KNN imputer to handle missing values, especially for numerical columns like `Bath` and `Balcony`.
- **Probabilistic Imputation**: For categorical columns with missing values, a probabilistic imputation technique was used, filling in values based on the likelihood of occurrence within each category.

### 5. Feature Engineering
- **New Features**: Added relevant features such as:
  - **Price per Square Foot**: Calculated the price per square foot for each house.
  - **Room to Bathroom Ratio**: Created a feature for the ratio of rooms to bathrooms to capture housing size dynamics.
  - **Type of House**: Classified houses into categories such as BHK (Bedroom-Hall-Kitchen) and RK (Room-Kitchen).

### 6. Handling Outliers
- **IQR Method**: Detected and removed outliers using the Interquartile Range (IQR) method. This ensured the data followed a more normal distribution, which is crucial for regression models.

### 7. Data Preparation for Model Training
- **Standardization & Encoding**: Standardized numerical features and used one-hot encoding for categorical variables, ensuring the data was ready for model training.
- **Pipeline Creation**: Built a Scikit-Learn pipeline with column transformers for encoding, scaling, and model training, ensuring streamlined deployment and reusability.

### 8. Model Selection & Cross-Validation
- **Model Training**: Trained and evaluated six different models using cross-validation, including Decision Tree, Random Forest, and Linear Regression models.
- **Best Model**: Achieved the best performance with a Decision Tree Regressor, with a cross-validated R² score of 0.99, improving predictive accuracy by 30%.

### 9. Hyperparameter Tuning
- **GridSearchCV**: Optimized hyperparameters using GridSearchCV, fine-tuning the model's performance and improving efficiency by 20%.

### 10. Final Model & Deployment
- **Model Saving**: The final selected model was saved using the Pickle module, ensuring easy deployment and future use.

## Tools & Technologies Used
- **Languages**: Python
- **Libraries**: Pandas, NumPy, Scikit-Learn, FuzzyWuzzy, Matplotlib, Seaborn
- **Techniques**: Cross-Validation, Hyperparameter Tuning, Imputation (KNN & Probabilistic), Feature Engineering, IQR Method for Outliers
- **Deployment**: Scikit-Learn Pipeline, Pickle

## YouTube Video
[![Bengaluru House Price Prediction](https://img.youtube.com/vi/YOUR_VIDEO_ID_HERE/0.jpg)](https://youtu.be/P1iXa9DgXFA?si=uz7l92smtUOWFuvI)

