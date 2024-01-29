# deep-learning-challenge
 Week 21 Assignment 

## Objective
The objective of this challenge was to create a binary classifier which can predict whether applicants will be successful if funded by a fictitious nonprofit foundation, Alphabet Soup.

### Steps
The following general steps were taken, with specific code/processes commented in the accompanying notebooks:
1. Preprocess the data
2. Compile, train and evaluate the model
3. Optimize the model

### Neural Network Model Report
#### Overview
   The purpose of this analysis is to discuss the performance of the learning model I created for the aforementioned client. The target performance was stated as > 75% accuracy. In an effort to achieve this target, I attempted to optimize the model by adjusting some hyperparameters, and show the effect of these changes on the model's accuracy. 

#### Results
Step 1 - Data Preprocessing
    Target variable (y) = "IS_SUCCESSFUL"    
    Target features (X) = APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, and "ASK_AMT" 
    "EIN" and "NAME" columns were removed as they are neither targets nor features. More columns were removed during the optimization process.
                     
Step 2 - Compiling, Training, and Evaluating the Model

Model 1 - AlphabetSoup1.ipynb
    I used 43 target features (9 bins for "APPLICATION_TYPE" and 6 bins for "CLASSIFICATION" features), 2 hidden layers, starting with 8 and 5 neurons respectively, 2 primary activation functions - the rectified linear unit(ReLU) and sigmoid, and 100 epochs.  This resulted in 72.9% accuracy.
    
Model 2 - AlhabetSoupCharity_Optimization.ipynb
    Here, I used 51 target features(11 bins for "APPLICATION_TYPE" and 12 bins for "CLASSIFICATION" features), 2 hidden layers, 30 and 18 neurons respectively, 2 primary activation functions - the rectified linear unit(ReLU) and sigmoid, and 140 epochs.  This resulted in 72.5% accuracy.
    
Model 3 - Optimization2.ipynb
    Here, I used 43 target features(reverted to 9 bins for "APPLICATION_TYPE" and 6 bins for "CLASSIFICATION" features), 2 hidden layers, 20 and 15 neurons respectively, 2 primary activation functions - the rectified linear unit(ReLU) and sigmoid, and 80 epochs.  This resulted in 72.5% accuracy.
    
Model 4 - AlhabetSoupCharity_Optimization3.ipynb
    Here, I used 37 target features(dropped 3 additional columns, used 9 bins for "APPLICATION_TYPE" and 12 bins for "CLASSIFICATION" features), 2 hidden layers, 16 and 12 neurons respectively, 2 primary activation functions - the rectified linear unit(ReLU), Leaky ReLU, and sigmoid, and 110 epochs.  This resulted in 62.7% accuracy.
    
    
#### Summary
   In conclusion, the model that achieved closest to the target accuracy (>75%) was the original model using the aforementioned hyperparameters. From my observations, adding a 3rd layer negatively affected the model's accuracy and resulted in lower than the reported % acuuracy scores, and using more than one activation function did not prove to be beneficial. 
   Using the Keras Tuner library would have helped in taking the guess work out of model optimization, and let the tuner search for the best combination of hyperparameters to achieve greater accuracy.