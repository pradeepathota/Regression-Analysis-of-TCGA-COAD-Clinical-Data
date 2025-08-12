# Regression-Analysis-of-TCGA-COAD-Clinical-Data

This project trains and evaluates a logistic regression classifier to predict patient vital_status from clinical variables. It includes quick EDA, visualization, class-imbalance handling, threshold tuning, and ROC analysis.

## Data
Input file: clinical_data_ready_for_analysis.csv (CSV)

Target column: vital_status

If categorical (e.g., “Alive/Dead”), it is label-encoded to numeric.

Features: numeric columns are used directly (categoricals beyond vital_status are not encoded by default).

## Requirements
Python 3.9+

Packages:
1. pandas
2. numpy
3. matplotlib
4. seaborn
5. scikit-learn

## workflow
	1.	Load clinical_data_ready_for_analysis.csv.
	2.	EDA: Print describe(), info(), and missing-value counts.
	3.	Visualize:
	•	Histograms for all columns
	•	Seaborn pairplot (can be slow for many columns)
	•	Correlation heatmap of numeric features
	4.	Encode target: If vital_status is object dtype, convert to numeric via label encoding.
	5.	Select features: Use numeric columns only (excluding vital_status).
	6.	Split data: 70/30 train/test with stratify=y.
	7.	Handle imbalance: Compute balanced class weights from the training set.
	8.	Train model: Logistic Regression (max_iter=1000, class_weight=balanced).
	9.	Evaluate:
	•	Confusion matrix & classification report at thresholds 0.5 and 0.6
	•	ROC curve and AUC

 ## output
1. Console:
    
   a. Dataset summary (.describe(), .info()), missing value counts.
   
   b. Model performance at thresholds 0.5 and 0.6 (confusion matrix, precision, recall, F1-score, accuracy).
   
   c. ROC AUC score.

2. Plots:
 
   a. Histograms of numeric features.
   
   b. Pairplot showing feature relationships.
   
   c. Correlation heatmap (numeric features).
   
   d.	ROC curve with AUC.

3. Artifacts:
   
   a. Trained Logistic Regression model.
   
   b. Class weights dictionary.

   c. Label encoder
   
