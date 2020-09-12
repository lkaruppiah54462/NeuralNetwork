# NeuralNetwork

## A.Background

Use NN/DNN to model Alphabet soup funding and resulting success.

## B. Method

1. Clean and categorize the data.

a. In this case NAME/EIN have no direct impact on outcome , so columns dropped

b. Using value_counts, density plot, the object field/columns unique attributes were 
classified to make a reasonable list for each of the categorical columns.
The columns redistrubuted were AFFILIATION,INCOME_AMT,APPLICATION_TYPE 
and CLASSIFICATION

c. Looked at STATUS and SPECIAL_CONSIDERATIONS columns as majority of the data belong 
to one category for each. Initially dropped these columns , but it did affect accuracy , 
so they were re-instated.

d. OneHotEncoder used to fit and transform these columns.

e. Merged with original dataframe and dropped the inital columns that were encoded.

f. Created train/test arrays and scaled using standard scaler.

g. MODELS (we have 32 features i.e input dimension)
	i).Tried 2 hidden layers with 20 and 10 neurons each
	
	ii) Tried 3 hidden layers with 30,15  and 5 neurons each

	iii) Tried 4 hidden layers with 20,15,10 and 5  neurons each
		
	iv) Also tested 'tanh' activation function 

	v) also reduced epochs to 20 to see if the overfitting can be reduced.

## C. Results

a. Accuracy for all models was around 72 to 73%.

b. Accuracy dropped to 54% when STATUS and SPECIAL_CONSIDERATIONS columns were dropped.

c. Accuracy did not improve with additional hidden layers or more neurons
Our categoriztion and grouping may have contributed to some loss in accuracy.

d. Probaly logistic regression model would have helped. Tried, also got ~72%

## D. Discussion

a. We achieved 73%, reasonable but did not hit the target of 75%. Tried
various models , including logistics regression and still mangaed only to achieve 72%

b. The data categorization can be further refined, especially in the encoding
process. The more fields we have the netter for convergence on the results.

c. Recommend resmapling and setting different threshold for 'other' category and 
tesing the model

## E. Summary

For our model we selected 3 hidden layers for a 32 feature input. The hidden layers 
had 30,15,5 neurons respectively . relu activation fucntion was used for most layers 
and sigmoid for output layer. This model gave us 73% accuracy on the test data.
