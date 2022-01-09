# Neural_Network_Charity_Analysis

## Overview of the loan prediction risk analysis:

The purpose of this analysis was to develop a neural network to assist determining which organizations should be considered for funding from AlphabetSoupCharity.  Using previously obtained data of organizations that have been awarded or denied funding, the neural network is to be trained on multiple inputs to finally classify future organization requests for funding.

## Results:

#### Data Preprocessing
-  What variable(s) are considered the target(s) for your model?
    -  The target of IS_SUCCESSFUL is currently the only target for the model.

-  What variable(s) are considered to be the features for your model?
    -  APPLICATION_TYPE
    -  AFFILIATION
    -  CLASSIFICATION
    -  USE_CASE
    -  ORGANIZATION
    -  ASK_AMT
    -  STATUS
    -  INCOME_AMT
    -  SPECIAL_CONSIDERATIONS

-  What variable(s) are neither targets nor features, and should be removed from the input data?
    -  EIN
    -  NAME

#### Compiling, Training, and Evaluating the Model
-  How many neurons, layers, and activation functions did you select for your neural network model, and why?
For the initial attempt at model, two layers, with 80 and 30 neurons respectively (both "relu" type) were used.  The activation feature of "sigmoid" was used.  This was presented by the client as the starting point for model creation, allowing the analyst two further adjust in order to increase optimization.

-  Were you able to achieve the target model performance?
The model performance was set at 75%.  Unfortunately, the current model only achieved an accuracy rating of 74.09% on epochs 96 and 99.  An overall accuracy average of 72.98% was achieved.

-  What steps did you take to try and increase model performance?
In order to improve efficiency, multiple model attempts were performed.  The results of each attempt are listed below:

    -  Attempt 1:
        -  Dropped noisy data of ASK_AMT
        -  Hidden layer one: tanh type - 80 neurons
        -  Hidden layer two: relu type - 30 neurons
        -  Activation: sigmoid
        -  Highest accuracy/epoch: 74.08%, epoch 81 of 100
        -  Overall accuracy average: 72.79%
 
     -  Attempt 2:
        -  Dropped noisy data of ASK_AMT
        -  Hidden layer one: tanh type - 80 neurons
        -  Hidden layer two: relu type - 50 neurons
        -  Hidden layer three: sigmoid type - 30 neurons
        -  Activation: relu
        -  Highest accuracy/epoch: 74.00%, epoch 89 of 100
        -  Overall accuracy average: 73.04%

     -  Attempt 3:
        -  Dropped noisy data of ASK_AMT
        -  Hidden layer one: sigmoid type - 100 neurons
        -  Hidden layer two: sigmoid type - 75 neurons
        -  Hidden layer three: relu type - 50 neurons
        -  Hidden layer four: relu type - 25 neurons
        -  Activation: sigmoid
        -  Highest accuracy/epoch: 74.09%, epoch 99 of 100
        -  Overall accuracy average: 72.92%

     -  Attempt 4:
        -  Dropped noisy data of ASK_AMT
        -  Hidden layer one: sigmoid type - 60 neurons
        -  Hidden layer two: relu type - 30 neurons
        -  Hidden layer three: relu type - 15 neurons
        -  Activation: sigmoid
        -  Highest accuracy/epoch: 74.20%, epochs 155 and 162 of 200
        -  Overall accuracy average: 72.47%

## Summary:

As shown above, the initial setup for the model did not perform at the required level, coming in at 72.98%.  Through iterative design, the model was adjusted and obtained an increased rating of 73.04% on the second optimization attempt.  All other models had lower final accuracies than the initial model.  For this, it can be seen that changing the number of hidden layers and neurons had a negligible effect on increasing model accuracy.  Further adjustment may lead to an invalid model or one that overfits the dataset.

I would recommend a Random Forest classifier for an alternate model design.  This is due to Random Forest ability of performing binary classification, the ability to handle large datasets, and the reduction in code which can achieve comparable accuracy predictions.
