# deep-learning-challenge
Overview of the analysis: 

The nonprofit foundation Alphabet Soup wants a tool that can help it select the applicants for funding with the best chance of success in their ventures. With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

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

268/268 - 0s - loss: 0.5571 - accuracy: 0.7262 - 67ms/epoch - 250us/step
Loss: 0.557079017162323, Accuracy: 0.7261807322502136

The second model results:
268/268 - 0s - loss: 0.5549 - accuracy: 0.7304 - 105ms/epoch - 393us/step
Loss: 0.554912805557251, Accuracy: 0.7303789854049683
In the second model I was able to achieve slitly better results on accuracy and loss.

Were you able to achieve the target model performance?
No

What steps did you take in your attempts to increase model performance?

Dropped additional features that, in my opinion are not helpful, which helped to get a better performing model.
Added layer and changed type of activations.
Increased number of neurons.
Decreased epochs (higher number didnt help to get better performance).

Summary: 

Optimized model achieved better results with accuracy score of >73% and loss ratio of 0.55. It will be helpful to expolore different models or find the best performing models using keras and test those.