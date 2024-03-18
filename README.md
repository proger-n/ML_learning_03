# Model quality estimation

Summary: This project is about different validation techniques; we will discuss how to measure models quality correctly and avoid leaks. Also, we consider a few ways for model hyperparameters optimization and various methods for feature selection.


## Task

We will continue our practice with a problem from Kaggle.com. 
In this chapter we will implement all the validation’s schemes, few methods for hyperparameters tune and 
feature selection methods that were described upstairs. Measure quality metrics on train and test samples. 
Will detect overfitted models and regularize these. And dive more deeply with native model estimation and comparison.
1. Answer to the questions from introduction
   1. What is leave-one-out? Provide limitations and strong sides
   2. How Grid Search, Randomized Grid Search and Bayesian optimization works?
   3. Explain the classification of feature selection methods. Explain how Pearson and Chi2 works. Explain how Lasso works. Explain what is permutation importance. Get acquainted with SHAP
2. Introduction  - make all preprocess staff from the previous lesson
   1. Read all data – data.csv.
   2. Preprocess “interest level” feature.
   3. Create features:  'Elevator', 'HardwoodFloors', 'CatsAllowed', 'DogsAllowed', 'Doorman', 'Dishwasher', 'NoFee', 'LaundryinBuilding', 'FitnessCenter', 'Pre-War', 'LaundryinUnit', 'RoofDeck', 'OutdoorSpace', 'DiningRoom', 'HighSpeedInternet', 'Balcony', 'SwimmingPool', 'LaundryInBuilding', 'NewConstruction', 'Terrace'
3. Implement next methods:
   1. Split data into 2 parts randomly with parameter test_size (ratio from 0 to 1), return train and test samples 
   2. Split data into 3 parts randomly with parameters validation_size and  test_size, return train, validation and test samples 
   3. Split data into 2 parts with parameter date_split, return train and test samples splitted by date_split param
   4. Split data into 3 parts with parameters validation_date and  test_date, return train, validation and test samples  splitted by input params
4. Implement next cross validation methods:
   1. K-fold, where k is input parameter, return list of train and indexes 
   2. Grouped K-fold, where k and group_field are input parameter, return list of train and indexes 
   3. Stratified K-fold, where k and stratify_field are input parameter, return list of train and indexes
   4. Time series split, where k and date_field are input parameter, return list of train and indexes 
5. Cross-validation comparison
   1. Apply all implemented validation methods from above to our dataset.
   2. Apply the corresponding methods from sklearn.
   3. Compare the resulting distributions of features for the training part of the dataset between sklearn and your own implementation.
   4. Compare all validation schemes. Choose the best one. Explain your choice.
6. Feature selection
   1. Fit lasso regression model with normalized features. Use your method for split samples into 3 parts by field created with ratio 60/20/20 – train/validation/test.
   2. Sort features by weight coefficients from model, refit model on top 10 features and compare quality.
   3. Implement method for simple feature selection by nan ration in feature and correlation. Apply this method for the feature set and take top 10 features, refit model and measure quality.
   4. Implement permutation importance method and take top 10 features, refit model and measure quality.
   5. Import shap and also refit model on top 10 features
   6. Compare the quality of these methods for different sides – speed, metrics and stability.
7. Hyperparameters optimization
   1. Implement grid search and random search methods for alpha and l1_ratio for ElasticNet model from sklearn.
   2. Find the best combination for the model hyperparameters.
   3. Fit resulted model.
   4. Import optuna and configure the same experiment with ElasticNet.
   5. Estimate metrics and compare these approaches.
   6. Run optuna on one of the cross validation schemes

### Submission

Save your code in python JupyterNotebook.
