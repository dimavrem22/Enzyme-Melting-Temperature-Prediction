# Enzyme-Melting-Temperature-Prediction
Using machine learning to predict the thermostability (melting temperature) of enzymes from their amino acid sequences. 

## Project Data 
All data used for the completion of this project can be found in the following Google Drive Folder: 
<a href="https://drive.google.com/drive/folders/1YxB08VlF5I2qg24pWgSZNsRXUJAaigic?usp=sharing">Project Data</a>

## Dataset
Data used for the project was taken from the <a href="https://www.kaggle.com/competitions/novozymes-enzyme-stability-prediction">Novozymes Kaggle Competition</a> [1]. The dataset is comprised of enzymes' amino acid sequences, expeimental pH levels, and experimentally determined melting temepratures. The dataset contains over 30,000 entries. 

## Data Filtering
The data was filtered using the following criteria: 
- No missing values
- ph of 7 (neutral) 
- Amino acid sequence between 100 and 1000 in length

Applying the criteria resulted in a sample size of 23,462 enzymes. 

## Feature Extraction 
Features were extracted from the amino acid sequneces using FEGS (Feature Extraction based on Graphical and Statistical Features) tool published and open-sourced in 2021 [2]. The featurizer accepts an amino acid sequence and returns a 578-dimensional vector based on physiochemical properties of amino acids as well as amino acid/ dipeptide frequencies.

## Train/Test Split
All entries were randomly split into training (75%) and testing (25%) sets. 

## Feature Normalization
All features of the training set were normalized to a Gaussian distribution. Each feature had a mean of zero and a standard distribution of one. The testing data was then normalized using the same fit. This ensured that ML model traing was in no way influenced by entries from the testing set. 

## Training Machine Learning Models 
The following regression models were trained and tested: 
- Multiple Linear Regression
- Ridge Regression
- Lasso Regression
- Support Vector Regression
- Decision Tree Regressor
- Random Forest Regressor
- Multiple Layer Perceptron

The following metrics were used for model evaluation: 
- Mean Squared Error (MSE) 
- Root Mean Squared Error (RMSE)
- R-squared 
- Mean Absolute Error (MAE) 

## Cross Validation for Parameter Optimization
Grid Search was used to find the optimal parameters for the **Random Forest Regressor**: 
- Number of decision trees: 200
- Maximum Decision Tree Depth: 20 

CV was used to find the optimal parameters for the **Multiple Layer Perceptron**: 
- Activation Function: _logistic_
- Maximum GD Iterations: 100 
- Number of Hidden Layers: 300

## Comparing the Performance of all Models
<img width="500" alt="Screenshot 2022-12-28 at 5 19 29 PM" src="https://user-images.githubusercontent.com/90374336/209880305-983dcde9-417b-4de9-842a-8ff0f95cd0b6.png">

Model with best **absolute** performance: **Random Forest Regressor** 
Model with best overall performance: **Multiple Layer Perceptron**
