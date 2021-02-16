# Neural Network Charity Analysis

Using Neural Networks to analyze charitable organizations

## Overview of the Analysis

Using our knowledge of machine learning and neural networks, we were tasked with creating
a binary classifier that is capable of predicting whether charitable organizations applying
to receive money from Alphabet Soup will be successful if funded. 

## Results

- Data Preprocessing:
	
	- The target of our neural network analysis was the "IS_SUCCESSFUL" column. The purpose
of our analysis was to determine whether the organizations selected would ultimately be successful
if they were to receive funding. 

	- The features for our analysis were the "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION",
"USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", and "ASK_AMT" columns. 

	- The "EIN" and "NAME" columns were neither targets nor features, and were dropped during the 
preprocessing steps.

- Compiling, Training, and Evaluating the Model:

	- After initially using 80 neurons for the input layer, 30 for the hidden layer, and 1 for the 
output layer, I bumped that up to 90, 40 and 1, and then also added an additional hidden layer with 10
neurons. I used ReLU for the input and hidden layer activation functions, and sigmoid for the output layer,
with one attempt using tanh for the output layer with slightly diminished accuracy. 
	
	- The model was not able to achieve the target model performance, though it came close, usually 
achieving around 73% accuracy. 
![Neural Network Accuracy](https://github.com/greensleeves8/Neural_Network_Charity_Analysis/blob/main/Resources/Accuracy_results.png "Neural Network Accuracy")

	- To attempt to increase the model performance, the following steps were taken: the "INCOME_AMT"
was bucketed to move the companies with income above 5 million to above 50 million dollars into an other
category, the number of epochs were increased from 100 to 150, the neurons in the input and hidden layer
were increased, the output activation function was changed from sigmoid to tanh and back, and an additional
hidden layer was added, with negligible differences in performance. 

## Summary

Given the relatively low accuracy measure of the deep learning model, it seems that a simpler supervised machine
learning model with a logistic regression or Random Forest Classifier algorithm could have been used that 
would've required less data preprocessing and would be less resource intensive from a computational standpoint
than a deep learning model. It's also possible that additional data preprocessing could have yielded improved 
results. The "ASK_AMT" could've been used as a categorical variable, rather than a wide range of unique numbers, 
given that the vast majority of the ask amounts were for $5000. Changing that column to a categorical variable 
with "Under $5000", "$5000", and over "$5000" may be a way to generate better results. It also may have improved
the accuracy to include further data scaling. 