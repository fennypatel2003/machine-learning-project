# machine-learning-project
Apartment Price Prediction – Machine Learning Pipeline
Project Overview
This project uses Python and Scikit-learn to build a machine learning pipeline that predicts apartment rental prices in the United States. The project follows a machine learning workflow that includes loading and exploring data, splitting the data into training and testing sets, preprocessing numerical and categorical features, training regression models, and evaluating model performance.

Two regression algorithms are compared:
- Linear Regression
- Random Forest Regression
The Random Forest model is used for the final evaluation on the test dataset.
Project Objectives
- Explore an apartment rental dataset.
- Prepare features and a target variable for machine learning.
- Split the data into training and testing sets.
- Handle missing numerical and categorical values.
- Scale numerical features and encode categorical features.
- Build reusable preprocessing pipelines with Scikit-learn.
- Train and compare regression models.
- Evaluate model performance using 10-fold cross-validation and Root Mean Squared Error (RMSE).
Dataset
The project uses the apartments_for_rent.csv dataset provided for the course assignment. It contains 10,000 apartment listings and 10 original columns.

The target variable is:
- price – the apartment rental price.
The features used in the model are:
Feature	Description
latitude	Latitude of the apartment
longitude	Longitude of the apartment
bathrooms	Number of bathrooms
bedrooms	Number of bedrooms
has_photo	Whether the listing has a photo
pets_allowed	Pet policy for the apartment
square_feet	Apartment size in square feet


The id and fee columns are removed during data preparation.
Technologies and Libraries
- Python – programming language
- Jupyter Notebook – development environment
- Pandas – data loading and manipulation
- NumPy – numerical operations
- Matplotlib – data visualization
- Scikit-learn – preprocessing, pipelines, regression models, and evaluation
Project Workflow
1. Data Loading and Exploration
The apartment dataset is loaded into a Pandas DataFrame. The notebook examines the dataset structure, column names, data types, missing values, descriptive statistics, and feature distributions.

Visualizations and correlation analysis are used to explore relationships between apartment characteristics and rental prices.
2. Data Cleaning and Feature Selection
The id and fee columns are removed because they are not useful for the prediction objective in this assignment.

The price column is separated as the target variable, while the remaining columns are used as model features.
3. Training and Testing Split
The dataset is divided into training and testing sets using Scikit-learn's train_test_split.
- Training data: 80%
- Testing data: 20%
- Random state: 42
4. Data Preprocessing Pipelines
Separate pipelines are created for numerical and categorical features.

Numerical pipeline
- Uses SimpleImputer with the median strategy to fill missing values.
- Uses StandardScaler to standardize numerical features.
Categorical pipeline
- Uses SimpleImputer with a constant value of No_Pets for missing pet-policy values.
- Uses OneHotEncoder with drop='first' to encode categorical variables.
A Scikit-learn ColumnTransformer combines both pipelines and applies the appropriate transformations to each group of columns.
5. Model Training
Two regression models are trained using the preprocessed training data.

Linear Regression

A Linear Regression model is trained as the initial prediction model.

Random Forest Regression

A Random Forest Regressor is trained using random_state=42 and is evaluated as an alternative to Linear Regression.
6. Model Evaluation
Both models are evaluated using 10-fold cross-validation with Root Mean Squared Error (RMSE).

The notebook reports that the Random Forest model reduces the average RMSE by more than 22% compared with Linear Regression during cross-validation.

The fitted preprocessing transformer is then applied to the test data using transform(), without fitting the transformations again. The Random Forest model makes predictions on the prepared test set, and the final RMSE is calculated.
Model Performance
The notebook's comparison indicates that Random Forest Regression performs better than Linear Regression based on the cross-validation RMSE.

However, the assignment notes that prediction error remains relatively high compared with the median apartment rental price. Additional data, feature engineering, alternative algorithms, and hyperparameter tuning could potentially improve performance.

The final test-set RMSE is calculated when the notebook is executed. No specific numerical test RMSE is stated here.
Repository Files
File	Description
pipeline_project.ipynb	Jupyter Notebook containing data exploration, preprocessing pipelines, model training, and evaluation
apartments_for_rent.csv	Dataset required to run the notebook
README.md	Project documentation


How to Run the Project
1. Clone or download this GitHub repository.
2. Make sure Python and Jupyter Notebook are installed.
3. Install the required libraries:
pip install pandas numpy matplotlib scikit-learn jupyter
4. Place apartments_for_rent.csv in the same directory as pipeline_project.ipynb.
5. Start Jupyter Notebook:
jupyter notebook
6. Open pipeline_project.ipynb.
7. Run the notebook cells from beginning to end.
Note: The CSV dataset is required to run the notebook. It is not included automatically with the notebook file.
Key Learning Outcomes
- Building machine learning workflows with Scikit-learn.
- Separating training and testing data.
- Handling missing numerical and categorical values.
- Applying feature scaling and one-hot encoding.
- Creating reusable pipelines with make_pipeline.
- Combining transformations with ColumnTransformer.
- Training Linear Regression and Random Forest Regression models.
- Evaluating models using cross-validation and RMSE.
- Applying fitted preprocessing steps to unseen test data.
Author
Fenny Patel

Course: MDS 640 – Machine Learning
This project was completed as part of the MDS 640 Machine Learning Pipeline Project assignment.
