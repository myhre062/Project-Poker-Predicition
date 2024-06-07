# Project4-Poker-Prediction

## Collaborators
[Austin DeVore](https://github.com/adevore33) <br>
[Dan Kramer](https://github.com/d6kramer) <br>
[Devan Cherne](https://github.com/IAmTheGam3) <br>
[Ezrelle Myhre-Hager](https://github.com/myhre062)

## Objective

The purpose of this project was to test a series of machine learning models to determine their efficacy in predicting a poker hand when given a 5-card hand. While the predictive power of this testing is not necessarily illuminating since there are a limited number of definitive answers when drawing a hand of cards from a standard 52-card poker deck, we wanted to investigate which type(s) of models may prove more successful at learning from the dataset, and in turn, achieve the highest accuracy. This may provide insight on which models could be best suited for similar, if tangential, applications.

## Data

The data was provided by the University of California Irvine Repository, and contains over one million combinations of cards drawn, along with the resulting poker hand.

This dataset can be found here: https://archive.ics.uci.edu/static/public/158/data.csv

Each playing card was separated into two features (rank and suit) that was represented numerically, resulting in 10 total features to consider. Finally, each hand of cards was assigned a "class" which acted as the target datapoint, since it defined which "best hand" could be played from the cards given. The classes were also given a numerical representation, from 0 (no playable hand) to 9 (royal flush, the best possible hand).

![poker_hand_targets](https://github.com/myhre062/Project4-Poker-Prediction/assets/147351952/d4192d72-4c79-4fe4-b479-4d6ba6a13772)

The structure of the dataset required machine learning models to consider 10 features, while also accounting for 10 possible outcomes.

## Methodology

We opted to test a number of different models and compare results, including the following:

- Support Vector Classifier ('ovr' multi-class strategy)
- Logistic Regression ('lbfgs' multi-class solver)
- Decision Tree
- KNN (ravel target data to represent correct number of targets)
- Random Forest
- Deep Learning/Neural Network (10-unit output layer, softmax activation)

One thing that needed to be accounted for in all of the models was the multi-class nature of the problem. Since the model would need to predict one of ten possible "hand" outcomes, it was important to adjust the data so that the models would properly train, and predict on one of ten possible "hand" outcomes, rather than inadvertently asking the models to predict from a binary choice. We have included some of the multi-class adjustments above for reference.

## Results

The headline performance metric to compare all of the models was overall accuracy. Throughout the models, we used different techniques to measure performance, including classification reports, confusion matrices, tracking loss, and tuning models to determine the best model structures. Since these different techniques were not universally applied, we revert to accuracy as the main comparison point. The model's performance are as follows, from best to worst:

- Deep Learning/Neural Network - 99.81% Accuracy
- Random Forest - 76.06% Accuracy
- Decision Tree - 63.21% Accuracy
- KNN - 57% Accuracy
- Logistic Regression - 50.12% Accuracy
- Support Vector Classifier - 49.96% Accuracy

# The Models

Below are brief remarks on how each model was compiled and utilized:

## Support Vector Classifier

## Logistic Regression
I created the Logistic Regression Model using 30000 iterations.  I just did a random testing of iterations to see what number would end up working and 30000 was what had worked.  When I trained the data, I also had to ravel function the y data in order to capture all possibilities.  The accuracy was pretty much as expected in not being too good with a score of .50117.

## Decision Tree
I started with the decision tree model splitting the data into training and testing sets.  Then I created and fit the scaler.  Followed by creating the decision tree classifier to make our predictions.  Finally, I made a confusion matrix to show the results.  The accuracy score was a .63 which isn't too bad but still not up to our .75 we are looking.

## KNN
Upon loading the data in I reshaped the data with "ravel". Then I split the dataset and trained it. Then I fit a standard scalar and trained the data. I did a k test to find out which values of k would be most effective. Upon discovering that those values were 6 and 16 I instantiated my model with them. After that, I created my predictions and confusion matrices. I then printed my classification report and concluded that k=16 had the best accuracy at .65.

## Random Forest

## Deep Learning
In order to expedite and automate the process of finding an optimal model, we utilized the Keras Tuner utility to build and test a variety of models, and give us the top three options for evaluation. The size of the dataset contributed to relatively long testing times, so we ran comparatively short epochs, and gave the tuner utility a moderate step count between intervals when selecting the number of neurons per layer. 

![DNN_kerastuner](https://github.com/myhre062/Project4-Poker-Prediction/assets/147351952/1cf181f2-4b07-492a-b7ad-4e44d7312a04)


We also changed some key characteristics of the model tuner to ensure the models built were capable of multi-classification, rather than a binary decision model. We found a balanced set of instructions for the tuner that yielded a model that gave an impressive result of 98.81% Accuracy with a loss value of 0.0132 during evaluation that only required a little over 2 hours of search time.

![DNN_top_models](https://github.com/myhre062/Project4-Poker-Prediction/assets/147351952/11514350-2c82-44e1-a6a0-6c16c8740b27)

![DNN_top3_eval](https://github.com/myhre062/Project4-Poker-Prediction/assets/147351952/4ed098ae-8ff9-427b-b8cf-d584f295b7b4)
