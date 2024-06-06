# Project4-Poker-Predicition

## Collaborators
[Austin DeVore](https://github.com/adevore33) <br>
[Dan Kramer](https://github.com/d6kramer) <br>
[Devan Cherne](https://github.com/IAmTheGam3) <br>
[Ezrelle Myhre-Hager](https://github.com/myhre062)

## Objective

The purpose of this project was to test a series of machine learning models to determine their efficacy in predicting a poker hand when given a 5-card hand. While the predictive power of this testing is not necessarily illuminating since there are a limited number of definitive answers when drawing a hand of cards from a standard 52-card poker deck, we wanted to investigate which type(s) of models may prove more successful at learning from the dataset, and in turn, achieve the highest accuracy. This may provide insight on which models could be best suited for similar, if tangential, applications.

## Data

The data was provided by the University of California Irvine Repository, and contains over one million combinations of cards drawn, along with the resulting poker hand.

Each playing card was separated into two features (rank and suit) that was represented numerically, resulting in 10 total features to consider. Finally, each hand of cards was assigned a "class" which acted as the target datapoint, since it defined which best hand could be played from the cards given. The classes were also given a numerical representation, from 0 (no playable hand) to 9 (royal flush, the best possible hand).

The structure of the dataset required machine learning models to consider 10 features, while also accounting for 10 possible outcomes.

## Methodology

We opted to test a number of different models and compare results, including the following:

- Support Vector Classifier ('ovr' multi-class strategy)
- Logistic Regression ('lbfgs' multi-class solver)
- Decision Tree
- KNN (ravel target data to represent correct number of targets)
- Random Forest
- Deep Learning/Neural Network (10 unit output layer, softmax activation)

One thing that needed to be accounted for in all of the models was the multi-class nature of the problem. Since the model would need to predict one of ten possible "hand" outcomes, it was important to adjust the data so that the models would properly train, and predict on one of ten possible "hand" outcomes, rather than inadvertently asking the models to predict from a binary choice. We have included some of the multi-class adjustments above for reference.

## Results

The headline performance metric to compare all of the models was overall accuracy. Throughout the models, we used different techniques to measure performance, including classification reports, confusion matrices, tracking loss, and tuning models to determine the best model structures. Since these different techniques were not universally applied, we revert to accuracy as the main comparison point. The model's performance are as follows, from best to worst:

- Deep Learning/Neural Network - 99.81% Accuracy
- Random Forest - 76.06% Accuracy
- Decision Tree - 63.21% Accuracy
- KNN - 57% Accuracy
- Logistic Regression - 50.12% Accuracy
- Support Vector Classifier - 49.96% Accuracy

## The Models

Below are brief remarks on how each model was compiled and utilized:

# Support Vector Classifier

# Logistic Regression

# Decision Tree

# KNN

# Random Forest

# Deep Learning
