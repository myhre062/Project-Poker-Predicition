# Project4-Poker-Predicition

## Collaborators
Devan Cherne
Austin DeVore
Dan Kramer
Ezrelle Myhre-Hager

## Objective

The purpose of this project was to test a series of machine learning models to determine their efficacy in predicting a poker hand when given a 5-card hand. While the predictive power of this testing is not necessarily illuminating since there are a limited number of definitive answers when drawing a hand of cards from a standard 52-card poker deck, we wanted to investigate which type(s) of models may prove more successful at learning from the dataset, and in turn, achieve the highest accuracy. This may provide insight on which models could be best suited for similar, if tangential, applications.

## Data

The data was provided by the University of California Irvine Repository, and contains over one million combinations of cards drawn, along with the resulting poker hand.

Each playing card was separated into two features (rank and suit) that was represented numerically, resulting in 10 total features to consider. Finally, each hand of cards was assigned a "class" which acted as the target datapoint, since it defined which best hand could be played from the cards given. The classes were also given a numerical representation, from 0 (no playable hand) to 9 (royal flush, the best possible hand).

The structure of the dataset required machine learning models to consider 10 features, while also accounting for 10 possible outcomes.

## Methodology

We opted to test a number of different models and compare results, including the following:

- Linear Regression
- Logisitic Regression
- Decision Tree
- KNN
- Random Forest
- Deep Learning/Neural Network

It should be noted that due to the presence of multiple classes, and the inability of some models to properly account for this situation, we expected some models to not work properly before making any attempts.
