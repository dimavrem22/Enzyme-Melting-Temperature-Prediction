# Enzyme-Melting-Temperature-Prediction
Using machine learning to predict the thermostability of enzymes from their amino acid sequences. 

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

