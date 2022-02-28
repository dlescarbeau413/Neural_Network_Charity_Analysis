# Neural_Network_Charity_Analysis

Overview:
The purpose of this challenge was to create a binary classifier to predict which companies will be successful if Alphabet Soup help funds them.


Results:

Data preprocessing:
•	First step was to preprocess our data and narrowing down the categories in which we would test. We started by dropping columns that we knew had little impact and didn’t need as features. Those were the EIN and NAME columns. Next, we determined the number of unique values for each column remaining. The first column we looked at for binning was the “Application type column”. We decided to the application types that had less than 500 applications into the “other category”. Next, we looked at “Classification” column to see what we could bin. We decided to classify any classification less that 1500 into the “other category”. After we finished binning our data, we merged the new columns to the final dataframe that we would be running our model on. The final dataframe looks like the following.  
•	The variable that we considered our target variable was the “IS_SUCCESSFUL” column.
•	The variables we considered our features the first test, was every column but the “IS_SUCCESSFUL” column. 
•	Each of the following attempts were used with 50 epochs for training. 
Compiling, training and evaluating:
•	With this one column dropped, we reached an accuracy of 72.6% with two hidden layers. Hidden layer 1 had 100 neurons and the second hidden layer had 30 neurons. This model was ran with the “relu” activation function. 
![]()
![]()
![]()

Next, we tested the model three more times adding layers and dropping other columns to try to get closer to the 75% accuracy threshold. 
Attempt 1:
•	The first attempt to optimize our model was to add another hidden layer. We kept the same columns as in the first attempt as features but instead of 100 neurons in hidden layer 1, we increased it to 120 neurons. The second hidden layer also saw an increase of neurons with 50 neurons. The third layer, which was added, had 30 neurons. Each layer was used with the “relu” activation function. This attempt yielded an accuracy of 72.5% a small decrease in accuracy. 

![]()
![]()
![]()

Attempt 2:
•	The second attempt only had two hidden layers. With layer 1 having 100 neurons and layer 2 having 30 neurons along with the same activation. However, I looked at the value counts for some of the categories to figure out which columns had outliers. Looking at the value counts, I dropped the following columns:


o	'IS_SUCCESSFUL','APPLICATION_TYPE_T3','CLASSIFICATION_C1000','AFFILIATION_Other','INCOME_AMT_5M - 10M','INCOME_AMT_50M+','SPECIAL_CONSIDERATIONS_N', 'SPECIAL_CONSIDERATIONS_Y','INCOME_AMT_0', 'ORGANIZATION_Trust'
 	
While dropping these columns I reached an accuracy of 72.4% which was worse than my original test and my first optimization test. 
![]()
![]()
![]()



Attempt 3:
•	In my third attempt to try and optimize my model I kept the same number of layers. The first hidden layer had 100 neurons and the second hidden layer had 50 neurons also the same activation as my previous attempts. As in my previous attempt when selecting columns, I added a few more columns to drop from the dataframe to test from my previous attempt. The columns that I dropped are the following columns:

o	'IS_SUCCESSFUL','APPLICATION_TYPE_T3','CLASSIFICATION_C1000','AFFILIATION_Other','INCOME_AMT_5M-10M','INCOME_AMT_50M+','SPECIAL_CONSIDERATIONS_N', 'SPECIAL_CONSIDERATIONS_Y','INCOME_AMT_0', 'ORGANIZATION_Corporation','ORGANIZATION_Co-operative','USE_CASE_Heathcare','USE_CASE_Other'



The results were not as promising as I hoped with only reaching an accuracy of 72.57%. This was the same as my first and second test as far as accuracy score goes. 
![]()
![]()
![]()

Summary:
While I did not reach the intended target of 75% accuracy, I did however come close to the target reaching to about 73% accuracy. In order to reach the 75% threshold, I would recommend trying to find more outliers to drop from the dataset or work using a different activation function. Even in the preprocessing stage of our analysis, I would bin more of the columns so that the dataset isn’t as big as it is. Also, with the right combination of finding outliers and hidden layers and neurons the possibility of reaching the 75% accuracy threshold is possible. 

