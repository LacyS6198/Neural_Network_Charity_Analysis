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
 
 ![1](https://user-images.githubusercontent.com/93630042/160306238-de16c376-813f-4492-8b5a-603498c2cee0.png)

![2](https://user-images.githubusercontent.com/93630042/160306244-8b0ff354-51bf-4fcd-9363-6f51250488ee.png)


 - I was not able to acheive accuracy of 75% in either the first model, nor the three subseqent optimization attempts. 

 - The following steps were taken to attempt to increase model performance
   - **Increase hidden layers from 2 to 3**
     <br>
     I added a third hidden layer that used 15 neurons. I used the Relu and Sigmoid functions as was done in the original model. This only acheived accuracy of 72.77%.
     ![3](https://user-images.githubusercontent.com/93630042/160306253-ca240d4d-cc42-4aad-948c-d9233c8cc664.png)

     <br><br>
   - **Use LeakyRelu instead of Relu and Sigmoid**
     <br>
     For my second optimization attempt, I used the same third hidden layer as noted above but then changed the Relu and Sigmoid functions to LeakyRelu (for both the hidden and outpt layers). This model acheived an accuracy of 72.31%.
     ![4](https://user-images.githubusercontent.com/93630042/160306258-cf85ada7-7118-4248-b3bc-a18966a13763.png)

     <br><br>
   - **Categorize the ASK_AMT field then apply LeakyRelu model with three hidden layers**
     <br>
     Finally, I attempt to categorize the ASK_AMT field then applied the three hidden layer LeakyRelu model. This acheived an accuracy of 72.38%.
     ![5](https://user-images.githubusercontent.com/93630042/160306263-a3b47876-b585-4abe-b3f8-e5c6bc57285d.png)
     
     ![6](https://user-images.githubusercontent.com/93630042/160306316-48a5efe8-a6ff-4212-92ed-93bbb65e88e6.png)

# Summary
Overall, I was not able to acheive the desired accuracy of at least 75%. The initial attempt resulted in an accracy of 70.29%. Subsequent optimization attempts were able to ultimately lead to 72.38% accuracy but still failed to meet the 75% goal.

Recommendations of models or techniques to try:
 - Different categorization of the ASK_AMT field - this field had a lot of various values. Better categorization of the values may improve the model accuracy. The current categorization when coupled wtih the LeakyRelu function resulted in a 72.31% accuracy. Refinement of the categories may be enough to improve to 75%.
 - After modifying the ASK_AMT classification, the model may need to have the number of hidden layers and neurons adjusted to acheive the 75% accuracy. The third optimization attempt was close so by recategorizing the ASK_AMT field and modifying the model slightly, optimum accuracy may be acheivable. 

