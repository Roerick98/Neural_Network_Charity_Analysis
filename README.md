# Neural Network Charity Analysis
## Overview
Using Machine Learning and Neural Networks for this project, I used the features in the dataset to create a binary classifier that will help to predict if the applicants that will be funded by a Charitable organization called Alphabet Soup will be successful. For this analysis we had a dataset containing various measures on 34,000 organizations that have been funded by Alphabet Soup. This project compromised of the following 3 steps:
- Preprocessing the data 
- Compile, train, and execute the model
- Attempt to optimize the model

## Results
### Data Preprocessing
- Target variable used for prediction: IS_SUCCESFUL column of the inputted dataframe
- Independent variables used for train and test splits: Every column other than the IS_SUCCESSFUL column of the inputted dataframe
- Variables dropped: EIN and NAME columns were dropped due to their small impact on the predication outcome.
### Compiling, Training, and Executing the Model
Inspecting our scaled and processed dataframe, it is clear that our model has 44 input features, and thus we constructed the first model with 2 hidden layers, the first containing 80 neurons and the second containing 30 neurons. Both of the hidden layers utilized the "relu" (Rectified Linear Unit) activation function. The output layer, was constructed with 1 neuron and utilized the "Sigmoid" activation function to compute probability values.
![Deliv2](https://user-images.githubusercontent.com/35403433/141020730-f168d2a0-ccd7-4bb5-8c01-c67f1528b922.png) <br />
I then compiled the model, assigning each neuron to evalute the input data with the "Adam" optimizer algorithm and specified the loss function as "binary_crossentropy". After fitting the model with the scaled data and 100 epochs, it output a model with about 72% accuracy. Thus, this model is able to predict whether certain organizations would make successful investments about 72% of the time.
Although this model can be considered to be optimal, it did not reach the targeted 75% accuracy rate. Measures were taken to try and increase this accuracy rate, such as increasing the number of neurons in each hidden layer, adding an additional hidden layer, and changing the activation functions.
### Attempt 1
Attempt 1 consisted of adding an additional hidden layer to increase a higher level of forward propogation between neurons. 
![Attempt 1](https://user-images.githubusercontent.com/35403433/141022619-3e6b5db2-633b-463d-ace6-a51bf9643c96.png)<br />
Unfortunately this did not result in an increase in accuracy and only would result in an increase in time and decrease in proficiency. 
![Attempt1_result](https://user-images.githubusercontent.com/35403433/141022644-ae89c548-8f73-4cc2-992c-e2701c3ab916.png)<br />
Results of this model show that it achieved a 72.45% accuracy rate, which is still lower than desired.
<br />
### Attempt 2
Attempt 2 consisted of changing the activations functions in an effort to affect propogation. The second layer was constructed and called with the LeakyReLU activation function, a slightly more leanient version of the relu function that allows for small negative values. 
![Attempt2](https://user-images.githubusercontent.com/35403433/141023102-b1f6421b-e2d1-4665-9a23-0cd01886818e.png)<br />
Results show a slight increase in the rate of accuracy, however still did not reach 75%.
![Attempt2_result](https://user-images.githubusercontent.com/35403433/141023262-fe51c78e-2aa9-443b-a646-fba85b1d025b.png)<br />
<br />
### Attempt 3
Attempt 3 consisted of adding additional neurons to each of the hidden layers. We only increased the neuron count in each layer by 10 so that it wouldn't present a large possibillity of overfitting.
![Attempt3](https://user-images.githubusercontent.com/35403433/141023545-0830eecb-f7c5-425d-8552-887f3565aa7a.png)<br />
Results show about the same accuracy rate as the other modifications at about 72.46%.
![Attempt3_result](https://user-images.githubusercontent.com/35403433/141023733-a91f3476-364e-4490-a758-84af50ce1111.png)<br />
<br />
## Summary
The model ended up with the highest accuracy rate of about 72.79% after changing the activation function for its second hidden layer. It is probable that adding additional layers or neurons to the model would only increase the time of training and provide the possibility of overfitting. Therefore, it is in my opinion that the only method for increasing this model's efficiency would be to increase the amount of data and its quality.

