# Wave Energy Converter (WEC) Placement Optimization Project
This project focuses on the placement optimization of Wave Energy Converters (WECs) near Adelaide, Australia, using advanced data science and machine learning techniques. The dataset contains spatial coordinates of 16 WECs, their absorbed power, and the total energy output (target variable: Powerall). The goal is to develop regression models to predict the total power output (Powerall) based on WEC configurations, enabling insights for optimizing renewable energy systems.
# Download Dataset:
1. https://drive.google.com/drive/folders/1IY9baziLtXFUCFZWiB3oLTGNHCE7KrC8?usp=sharing
# Objectives
1. Dataset Analysis:
Understand how WEC positions influence the total power output.
Optimize configurations for maximizing energy production.
2. Machine Learning Models:
Build and compare various regression models.
Perform hyperparameter tuning and feature selection to identify the best-performing models.
Generalization: Test the best model on a new dataset from Tasmania to ensure robust performance.
# Files in Repository
1. Group_14_Raw_Data.csv: Raw dataset with WEC configurations and energy outputs.
2. Group_14_Cleaned_Data.csv: Preprocessed dataset after cleaning, scaling, and handling missing values.
3. Group_14_Data_Cleaning.ipynb: Jupyter Notebook detailing the data cleaning process and Exploratory Data Analysis (EDA).
4. Group_14_Data_Cleaning.pdf: PDF export of the data cleaning notebook for documentation.
5. Group_14_Model_Building.ipynb: Model training, evaluation, and feature selection steps.
6. Group_14_Model_Building.pdf: PDF export of the model building notebook.
7. Group_14_Test_Results.ipynb: Evaluation of the best model on the Tasmania dataset.
8. Group_14_Test_Results.pdf: PDF export of the test results notebook.
9. best_model.joblib: Saved best-performing model for future use.
10. scaler.joblib: Saved scaler for preprocessing new data.
# Methodology
1. Step 1: Dataset Overview
Dataset contains WEC positions (X1, X2, ..., Y16), absorbed power (P1, P2, ..., P16), and total power output (Powerall).
2. Step 2: Data Cleaning and Preprocessing
Handling Missing Values: KNN imputation for zeros in WEC positions and absorbed power.
Outlier Handling: Removed or replaced based on their proportion in the dataset.
Feature Scaling: Standardized all numeric features for consistent model performance.
Skewness Correction: Applied transformations for highly skewed features.
3. Step 3: Model Building
Models Trained:
Linear Regression
K-Nearest Neighbors (KNN)
Random Forest
SVM (Linear and RBF Kernels)
Gradient Boosting
Evaluation Metrics:
Root Mean Squared Error (RMSE)
𝑅2 Score
Top Performers: SVM (Linear Kernel): Best baseline model with RMSE: 229.98, 𝑅2 : 0.9999.
Ensemble Model: Best overall performance with RMSE: 3238.25, 
𝑅2 : 0.997.
4. Step 4: Feature Selection and Tuning
Lasso Regression: Selected most significant features.
Hyperparameter Tuning: Optimized parameters using RandomizedSearchCV.
Bi-Directional Elimination: Reduced feature set to enhance model efficiency.
5. Step 5: Deployment and New Data Evaluation
Generalization:Tested on a new dataset from Tasmania.
Results: RMSE: 19,177.67, 
𝑅2 : 1.0000, demonstrating robust and generalizable predictions.

# Key Results
* Model	Train RMSE	Test RMSE	Train_R2 Test_𝑅2
1. Linear Regression	369.96	230.30	0.9999	0.9999
2. SVM (Linear)	370.07	229.98	0.9999	0.9999
3. Ensemble Model	2882.75	3238.25	0.9973	0.9966
4. XGBoost	8587.59	9687.17	0.9758	0.9699
5. Neural Network	189,440.63	190,418.75	-10.77	-10.62

# How to Run
1. Preprocess New Data:
  Use scaler.joblib to scale new data.
2. Load Best Model:
  Use best_model.joblib for predictions.
3. Predict:
  Load your new data and predict using the Group_14_Test_Results.ipynb notebook.

# Team Members
Name	UH ID	Responsibilities
1. Md Moshiur Rahman:	2400991	:Data Cleaning, Model Training, Documentation
2. Jayaprakash Yadav Guntumani:	2391724	:Hyperparameter Tuning, Feature Selection, Model Building
3. Tanushree Mukherjee:	2413888	:Neural Network Development, XGBoost, Ensemble Models
4. Divya Sai Sree Pilli:	2404251	:Gradient Boosting, Insights, Final Model Testing

# Future Work
1. Deploy the best model in a real-world wave energy system.
2. Explore advanced ensemble techniques for further accuracy improvements.
3. Investigate other datasets for broader generalizability.
