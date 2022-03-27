# Neural_Network_Charity_Analysis - Project Overview
The purpose of the project was to help create a binary classifier that is capable of predicting whether applicants will be succcessful if funded by Alphabet Soup. A CSV containing more then 34,000 was used. The data included various columns that captured metadata about the organizations.

The data was reprocessed before having machine learning applied. After the data was transformed, it was fitted and scaled. It was then ran through a machine learning model. At first it was ran through ReLu and Sigmoid using two hidden layers. The model was then modified in an attempt to optimize it for 75% accuracy.

# Results
The below describes the data preprocessing that was applied to the data as well as how the model was compiled, trained and evaluation results.

## Data Preprocessing

 - **Variable(s) considered to be targets of model:**  IS_SUCCESSFUL
 - **Variable(s) considered to be features of model:**  APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT 
 - **Variable(s) considered to be neither targets nor featuers of model:** EIN, NAME (these values were dropped from the dataframe)

## Compiling, Training, and Evaluating the Model

 - The first model had two hidden layers. One layer had 80 neurons, the other layer had 30. ReLu was applied to the first and second hidden layer. Sigmoid was apllied to the outpt layer. This model's accuracy was 70.29%.

 - I was not able to acheive accuracy of 75% in either the first model, nor the three subseqent optimization attempts. 

 - The following steps were taken to attempt to increase model performance
   - Increase hidden layers from 2 to 3
     <br>
     I added a third hidden layer that used 15 neurons. I used the Relu and Sigmoid functions as was done in the original model. This only acheived accuracy of 72.77%.
     <br><br>
   - Use LeakyRelu instead of Relu and Sigmoid
     <br>
     For my second optimization attempt, I used the same third hidden layer as noted above but then changed the Relu and Sigmoid functions to LeakyRelu (for both the hidden and outpt layers). This model acheived an accuracy of 72.31%.
     <br><br>
   - Categorize the ASK_AMT field then apply LeakyRelu model with three hidden layers
     <br>
     Finally, I attempt to categorize the ASK_AMT field then applied the three hidden layer LeakyRelu model. This acheived an accuracy of 72.38%.



# Summary
