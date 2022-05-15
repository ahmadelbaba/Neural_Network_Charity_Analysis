# Neural_Network_Charity_Analysis

## **Overview**

We're using neural networks to create a binary classifier that is capable of predicting whether charity applicants will be successful if funded by Alphabet Soup. Alphabet Soup’s business team provided us with a a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as the following:

-EIN and NAME—Identification columns
-APPLICATION_TYPE—Alphabet Soup application type
-AFFILIATION—Affiliated sector of industry
-CLASSIFICATION—Government organization classification
-USE_CASE—Use case for funding
-ORGANIZATION—Organization type
-STATUS—Active status
-INCOME_AMT—Income classification
-SPECIAL_CONSIDERATIONS—Special consideration for application
-ASK_AMT—Funding amount requested
-IS_SUCCESSFUL—Was the money used effectively


In this project we will:

- Preprocess Data for a Neural Network Model
- Compile, Train, and Evaluate the Model
- Optimize the Model
- Assess the results

## **Results**

### Data  Preprocessing:
  - Target for this model: IS_SUCCESSFUL
  - Features for the model: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT
  - Variables to remove: EIN, NAME

### Compiling, Training, and Evaluating the Model:

The initial model achieved an accuracy of 0.51 with the following structure:
- Number of layers: 2
- Number of neurons in layer 1: 80
- Number of neurons in layer 2: 30
- Activiation function: Relu

First optimiziation attempt achieved an accuracy of 0.63 with the following structure:
- Removed addtional variables: AFFILIATION, STATUS, SPECIAL_CONSIDERATIONS
- Number of layers: 2
- Number of neurons in layer 1: 80
- Number of neurons in layer 2: 30
- Activiation function: Relu

Second optimiziation attempt achieved an accuracy of 0.49 with the following structure:
- Removed addtional variables: AFFILIATION, STATUS, SPECIAL_CONSIDERATIONS
- Number of layers: 2
- Number of neurons in layer 1: 80
- Number of neurons in layer 2: 30
- Activiation function: Tanh

Third optimiziation attempt achieved an accuracy of 0.53 with the following structure:
- Removed addtional variables: AFFILIATION, STATUS, SPECIAL_CONSIDERATIONS
- Number of layers: 3
- Number of neurons in layer 1: 160
- Number of neurons in layer 2: 60
- Number of neurons in layer 3: 30
- Activiation function: Relu

None of our attempts was able to achieve the target model performance of 75% accuracy

## **Summary**

Removing noisy variables resulted in the highest performance boost from 0.51 to 0.63. We then attemped a different activitation model (Tanh vs Relu) however that dropped accuracy further to 0.49. 

In our third attempt we reverted to Relu and added a third hidden layer as well as increased the number of neurons in each layer. The model's performance improved slightly however still far from our target of 75%. 

In a binary classification situation, a neural network model might be an overkill. A supervised machine learning model such as the Random Forest Classifier could be used.  In such a model, we can combine the output of multiple weak learners to predict a correct outcome. 

