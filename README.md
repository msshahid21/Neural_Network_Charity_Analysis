# Neural Network Charity Analysis
## Overview
The purpose of this project is to use a deep learning model to help determine which organizations to support for charitable donations. This is done in order to help minimize the risk of misuse of funds.

## Results
### Data Processing
- What variable(s) are considered the target(s) for your model?
  - The target variable in this case is the IS_SUCCESSFUL variable, as it is a binary variable that classifies whether the money was used effectively or not. This is exactly in line with the purpose of the deep learning model.

- What variable(s) are considered to be the features for your model?
  - The following variables were used as features in the deep learning model: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPEACIAL_CONSIDERATIONS, and ASK_AMT

- What variable(s) are neither targets nor features, and should be removed from the input data?
  - Only two variables were not used as either a feature or a target variable, and those were the EIN and NAME variables. This is because both of those are unique identifiers for each row in the dataset, and would not provide any additional insight for the deep learning model.

### Compiling, Training, and Evaluating the model
- How many neurons, layers, and activation functions did you select for your neural network model, and why?
  - I chose to use two hidden layers, with 80 and 30 neurons each, and both were using the RELU activation functions, while using the SIGMOID function for the output layer. 80 and 30 neurons for two hidden layers was used because of the rule of thumb to choose between 2 and 3 times the amount of features for the number of neurons in the hidden layer. The number of features in this dataset, after the One Hot Encoding was 44, therefore using 80 as the number of neurons for the first layer. The second layer was chosen to be 30 so as to be around half of the number of neurons as the first hidden layer.

- Were you able to achieve the target model performance?
  - No, I was not able to achieve the target model performance, I was able to get as close as 73.18%

- What steps did you take to try and increase model performance?
  - I tried increasing the number of hidden layers to three for my first attempt, which yielded the highest accuracy out of the four models constructed. For the second attempt at optimization, I decided to try using the tanh activation function which did not improve the accuracy, yielding 72.93%. While for the third and final attempt I added more nodes to the two hidden layers, which also did not improve the results and yielded a 72.9% accuracy score.

## Summary
Here is a summary of the results:
|                     | Accuracy Score |
|---------------------|----------------|
| Original Model      | 73.11%         |
| Optimized Attempt 1 | 73.18%         |
| Optimized Attempt 2 | 72.93%         |
| Optimized Attempt 3 | 72.90%         |

### Recommendation
A random forest model for this dataset could yield a better result perhaps, compared to the deep learning model. This is because when looking at the ASK_AMT variable as a box plot there were quite a few outliers, and a random forest model is less influenced by outliers than other algorithms. Additionally, because the Random Forest model creates a bunch of weak decision trees and uses them in conjunction with each other, less important features can also be fed into the model and it is possible to extract the best features of the dataset.
