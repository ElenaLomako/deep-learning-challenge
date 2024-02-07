# deep-learning-challenge
Overview of the analysis: 

The objective of this analysis is to construct a deep learning model designed to forecast the likelihood of success for applicants seeking funding from Alphabet Soup. Our aim is to develop a model with an accuracy surpassing 75%, enabling the effective classification of applicants into successful and unsuccessful categories based on diverse input features.

From Alphabet Soup’s business team, you have received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization, such as:

EIN and NAME—Identification columns
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organization classification
USE_CASE—Use case for funding
ORGANIZATION—Organization type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special considerations for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively

Results:

Data Preprocessing

What variable(s) are the target(s) for your model?
The variable that is our target is "IS_SUCCESSFUL"

What variable(s) are the features for your model?
The rest of the variables are features besides the once we have dropped ("EIN", "NAME"). When I tried to keep "NAME" feature the model showed weird results where accuracy on the test data was very different from acuuracy on the train data, which indeed support the idea that this feature is not useful in our model.

What variable(s) should be removed from the input data because they are neither targets nor features?
EIN and NAME features should be removed as these features will not contribute to the model. I also removed "SPECIAL_CONSIDERATIONS" feature, which slightly helped with performance of the model.

Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?

In the first model I used 2 layers (RELU) with 12 and 8 neurons respectively. I tested out other activation functions and RELU performed the best, therefore I left it with both RELU layers. Also, I started with 6 and 2 neurons for each of the layers respectively and then kept increaing the number of neurons, added an additional layer, and played with activation type. However, I wasn't able to get the accuracy of the model above 75%.

The first model results:
![Model 1](/Users/elenalomako/Desktop/DataScience/HW/21- Deep learning/deep-learning-challenge/Challenge/Images/Model_1.png)

268/268 - 0s - loss: 0.5571 - accuracy: 0.7262 - 67ms/epoch - 250us/step
Loss: 0.557079017162323, Accuracy: 0.7261807322502136

The second model results:

![Model 1](/Users/elenalomako/Desktop/DataScience/HW/21- Deep learning/deep-learning-challenge/Challenge/Images/Model_2.png)
268/268 - 0s - loss: 0.5549 - accuracy: 0.7304 - 105ms/epoch - 393us/step
Loss: 0.554912805557251, Accuracy: 0.7303789854049683
In the second model I was able to achieve slitly better results on accuracy and loss.

The third model results:
![Model 3](/Users/elenalomako/Desktop/DataScience/HW/21- Deep learning/deep-learning-challenge/Challenge/Images/Model_3.png)
68/268 - 0s - loss: 0.5131 - accuracy: 0.7535 - 300ms/epoch - 1ms/step
Loss: 0.5131112933158875, Accuracy: 0.7534694075584412

Were you able to achieve the target model performance?
Yes

What steps did you take in your attempts to increase model performance?

Dropped additional features that, in my opinion are not helpful, which helped to get a better performing model (in model 2).
Added layer and changed type of activations.
Increased number of neurons.
Decreased epochs (higher number didnt help to get better performance).

In the third model( or second optimization model) I increased a number of neurons, slightly increased the number of epochs, and included "Name" feature. This led to better results. According to the analysis names are correlated with the probabilty of the applicant being succesful candidate or not.

Summary: 

Optimized model achieved better results with accuracy score of >73% and loss ratio of 0.55. It will be helpful to expolore different models or find the best performing models using keras and test those. Also, in light of the classification-centric nature of the challenge, investigating alternative models like Random Forests, Gradient Boosting Machines, or Support Vector Machines is prudent. These models might deliver superior performance in handling the classification task.